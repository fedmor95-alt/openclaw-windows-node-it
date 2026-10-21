---
name: hanselman-code-review
description: "Adversarial dual-model code review that runs two AI models in parallel, cross-references findings, and produces a consensus severity table with fix confidence ratings. Use when asked for a thorough code review, adversarial review, dual-model review, confidence-rated review, or 'Hanselman review'."
---

# Hanselman Adversarial Code Review Skill

Run a rigorous, adversarial code review using two AI models in parallel.
Cross-reference their findings to separate signal from noise, producing a
consensus severity table with fix confidence ratings.

## When to Use

Invoke this skill when the user asks for:

- A thorough or deep code review
- An adversarial review
- A dual-model review
- A "Hanselman review"
- A confidence-rated review
- Cross-model validation of code changes

## Philosophy

Single-model reviews have blind spots. Two models reviewing independently
surface different classes of issues: security, correctness, and edge cases.
Cross-reference their findings:

- **HIGH consensus** (both models flag it): strong evidence; verify the issue.
- **LOW consensus** (only one model flags it): may be noise; use judgment.
- **Disputed** (a model flags it but evidence contradicts it): investigate
  before acting.

## Review Workflow

### Step 1: Identify the Scope

Determine what code to review:

- If the user specifies files, use those.
- If the user says "review my changes", use `git diff` or `git diff --staged`.
- For a PR, use `gh pr view` and `gh pr diff`, pinning the exact head and base.
- For a branch, diff against the base branch.

For a repeat review, compare the current head with the previously reviewed
head. Review changed code, affected callers/tests, and unresolved or disputed
findings rather than automatically repeating the full review. If the code is
unchanged and only the models changed, focus both reviewers on those findings
and high-risk decisions. State the delta scope and retain missing runtime-proof
gates.

### Step 2: Launch Two Parallel Reviews

Inspect the current host's advertised tool schemas and roles before choosing a
launcher. Tool names, agent roles and model access vary by host.

| Host observation | Route |
|---|---|
| `task` advertises `rubber-duck` | Launch two bounded read-only reviews using that role, in parallel with different supported models. Use background mode when independent work remains. No standalone model CLI is required. |
| No `rubber-duck`, but an independent review role/tool is advertised | Use that actual supported role if it can review the same scope independently. Label the route as a fallback and record its tool, role, model and limitations. Do not claim a rubber-duck role ran. |
| No independent review tool, or two distinct models cannot be selected under host policy | Report the dual-model review blocked. Direct self-review or a single-model fallback may be useful, but is not a completed Hanselman review. |

Honor the host's model-selection policy. Do not force model/effort/context
overrides from a copied example when the tool requires explicit user selection.
Confirm the two actual model identities before calling the result dual-model.

Both agents receive the **exact same prompt** so findings are comparable.
Include the full file contents or diff, project context, exact revisions,
constraints, and the severity definitions below.

### Step 3: Wait for Both to Complete

When using this host's background `task` route, use the interval for independent
work. Wait for completion notifications, then read each known ID with
`read_agent`; do not poll. For another supported host, use its documented
completion mechanism. Reconcile both completed reviews before reporting a
consensus. Neither review grants GitHub publication authority.

### Step 4: Cross-Reference and Build the Consensus Table

Create a SQL table to track findings:

```sql
CREATE TABLE IF NOT EXISTS review_findings (
    id TEXT PRIMARY KEY,
    issue TEXT NOT NULL,
    reviewer_a_severity TEXT,
    reviewer_b_severity TEXT,
    consensus TEXT NOT NULL,
    fix_confidence INTEGER NOT NULL
);
```

Use SQL only if the host exposes a session database; otherwise keep the same
fields in a local review artifact. If the session already has a findings table,
inspect and reuse or migrate its schema without discarding earlier findings.
Record the actual tool, role, model ID, context tier and source scope for each
reviewer alongside the findings; do not relabel earlier findings as results
from a different model.

For each finding:

1. Check whether the other model found the same or a similar issue.
2. Assign consensus: both flagged it is `HIGH`; one flagged it is `LOW`;
   evidence contradicting a finding is `LOW (disputed)`.
3. Verify it against the actual code, dependency contract, and tests.
4. Assign fix confidence:
   - 99%: trivial fix, such as a wrong flag or missing null check.
   - 90-95%: straightforward fix requiring some design thought.
   - 70-80%: complex fix requiring research or trade-offs.
   - Below 70%: hard problem, intentional behavior, or architecture change.

### Step 5: Present the Results

**Both Models Agree: HIGH consensus**

| Issue | Reviewer A (actual model ID) | Reviewer B (actual model ID) | Fix Confidence |
|-------|----------|-------------|----------------|
| Description of issue | SEVERITY | SEVERITY | XX% |

**Only One Model Flagged: LOW consensus**

| Issue | Reviewer A (actual model ID) | Reviewer B (actual model ID) | Fix Confidence |
|-------|----------|-------------|----------------|
| Description of issue | SEVERITY or not flagged | SEVERITY or not flagged | XX% |

Use `not flagged` when a model did not identify the issue.

### Step 6: Act on Findings

- Ask which findings to fix unless the user has already authorized the fixes.
- Prioritize verified HIGH consensus issues.
- Explain one-model and disputed findings before acting.
- Do not broaden the task to satisfy a reviewer. Preserve the repository's
  scope and proof requirements.
- Fix confidence is the coordinator's assessment, not a model vote or a
  replacement for runtime proof.

## Review Instructions Template

Give both reviewers the same adapted prompt:

```text
Review the following code changes for [PROJECT NAME].
This is a [LANGUAGE/FRAMEWORK] project with these constraints: [CONSTRAINTS].
Exact head: [HEAD]. Base or previously reviewed head: [BASE].

Focus on bugs, security issues, race conditions, and correctness problems.
Ignore style and formatting.
Write every review comment in simplified technical English. Use short sentences
and common words, explain necessary technical terms, and avoid jargon or
unnecessary detail.

[FULL CODE OR DIFF HERE]

For each issue found, classify severity as:
- CRITICAL: will crash, corrupt data, or create a security vulnerability
- HIGH: likely bug that will manifest in real use
- MEDIUM: edge case that could bite in specific scenarios
- LOW: minor improvement, theoretical concern, or robustness enhancement

For each issue, include:
1. What the issue is
2. Where it is (file and line/region)
3. Why it matters (impact and reachability)
4. Suggested fix
```

## Model Selection

The preferred pairing, when selectable under the host's policy, is
**Claude Opus 5.5** (`claude-opus-5.5`) and
**GPT-6 Astra** (`gpt-6-astra`, `context_tier: "long_context"`), both with
`reasoning_effort: "high"`. Different model families provide independent
perspectives on the same evidence.

When explicit overrides are permitted and requested, use the tool's supported
`long_context` value, not an invented model name or suffix. Do not assume a
numeric context-window size. Otherwise retain host-resolved defaults and record
what actually ran, including unknown context/effort where not reported.

If a preferred model or context tier is unavailable, report the limitation and
use an available alternative only with the user's approval. Record the actual
model IDs and context tiers used; do not silently fall back to an older
generation.

## Important Notes

- Never skip cross-referencing. The value is in the comparison, not individual
  reviews.
- Log disputed findings and the reasoning for accepting or rejecting them.
- Do not fix LOW consensus issues without user authorization.
- A clean source review does not satisfy a missing Windows proof pool,
  current-head UI proof, or required CI check.
