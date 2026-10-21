# Checking agent workflows

Use this guide when changing repository instructions, skill routing, validation
planning, or evidence interpretation. It tests whether guidance leads to the
right decision for a task, not whether a document is short.

## Check host and tool readiness

```powershell
.\scripts\setup-dev.ps1 -AgentReadiness
.\scripts\setup-dev.ps1 -AgentReadiness -SharedReviewPath '<selected-autoreview-installation>'
```

This read-only JSON separates detected developer prerequisites, unverified
desktop/runtime proof, and optional shared-review files/interpreter availability.
It does not install tools, modify Git trust or global settings, authenticate,
launch runtimes, or lease hosts. A detected desktop session or `wsl.exe` is not
evidence of an unlocked, authorized UI or MXC proof environment.

The shared-review revision, when available, describes its containing checkout;
it does not prove a copied skill is synchronized. Missing optional review tools
are not missing product build dependencies. Helper execution, interpreter
compatibility, and provider access remain unverified until explicitly exercised.
Use the [shared autoreview entrypoint](../.agents/skills/autoreview/SKILL.md)
for approved installation and review.

`-ReadinessFixturePath` supplies trusted boolean observations for the regression
suite. Its output is labeled test-fixture data, never host evidence. It accepts
no executable probes.

The repository's Ubuntu Copilot setup workflow checks out the source and
installs gh-aw; it does not provision native Windows validation or the shared
reviewer. Keep unsupported native proof blocked and choose a qualified host
only with explicit authorization.

## Run a scoped shared review

This is an operator recipe for the canonical shared helper, not a Windows review
wrapper, result validator, or publication command. Use it only when review is
requested or required by the owning workflow. Review permission does not authorize
installation, commits, uploads, hosted bot requests, or runtime changes.

Read the complete selected shared installation's `SKILL.md` and its required
references first. Windows requires Python 3.10+ for the Python helper; honor an
operator-selected installation instead of assuming the default path exists.
Readiness detection alone does not exercise the helper, CLI isolation, credentials,
or provider access. A missing installation is a named blocker, not permission to
install it. Record the helper identity and actual host/engine/model when observable;
`python $helper --version` identifies only the helper bytes, not the whole skill
or a trusted execution receipt.

### Select the candidate and context

Use an observed comparison target, not an assumed `origin/main`. Inspect the
actual PR target or task's agreed base and the available local refs. The helper
never fetches; stale or missing refs limit what can be claimed.

| Intended scope | Explicit arguments | What is covered |
| --- | --- | --- |
| Only work since HEAD | `--mode local --max-priority P3` | HEAD through index and worktree, including untracked files; not earlier branch commits |
| Full iterative candidate | `--mode local --base <merge-base-sha> --max-priority P3` | Pinned comparison through index and worktree, including untracked files |
| Committed branch | `--mode branch --base <observed-target-ref> --max-priority P3` | Merge-base to HEAD; excludes dirty and untracked work |
| One non-merge commit | `--mode commit --commit <commit-sha> --max-priority P3` | Raw parent to commit, or empty tree for a root; merge commits are rejected; not the whole branch |

Do not rely on `auto`: it selects local when dirty and otherwise chooses a branch
comparison. The shared default severity is P0 only. Windows requires explicit
P0-P3, including for a narrative fallback. Local review includes staged and unstaged
transitions; an index defect remains actionable even if fixed in the worktree
(`INDEX-only`). Keep the captured source unchanged during review.

The reviewer starts with an empty sandbox, not access to the entire checkout.
Supply task requirements with `--prompt`, in-repository instruction files with
`--prompt-file`, and supported repository-relative evidence files with `--dataset`.
These are file inputs, not arbitrary external directories; sensitive-path,
symlink, file-type, and mutation checks apply. They are not secret-content scanning.
Do not transmit credentials or unrelated private material.

For unchanged production owners in branch/commit mode, repeat
`--source-context <repo-relative-path>` or use `--source-context-file` when the
whole file must remain intact every pass. These read frozen regular-file blobs
from the reviewed commit, never substitute working-copy content, and are unsupported
in local mode. Context does not expand finding scope or authorize instructions
embedded in reviewed content. If required local context cannot be supplied safely,
report the coverage blocker; do not silently omit it or change modes and claim
the dirty candidate was covered.

### Run once with fresh external outputs

Run from the reviewed repository root. Replace both placeholders below with the
observed target ref and the actual task requirements. Select the installed helper
path explicitly if it differs. This example selects Codex and reviews committed
plus dirty work; honor an explicitly requested engine and its requirements.
For another scope, use the corresponding mode/base above.

This example requires PowerShell 7.3+ with `Windows` or `Standard` native argument
passing so embedded quotes in requirements reach Python unchanged. Windows
PowerShell 5.1 and `Legacy` argument passing are unsupported for this example.
Resolve Python to a native `.exe`, not a `.bat`/`.cmd` shim that reparses arguments.
See [PowerShell native argument handling](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_parsing#passing-arguments-that-contain-quote-characters).

```powershell
if ($PSVersionTable.PSVersion -lt [version]'7.3' -or
    $PSNativeCommandArgumentPassing -notin @('Windows', 'Standard')) {
    throw 'Use PowerShell 7.3+ with Windows or Standard native argument passing.'
}
$python = Get-Command python -CommandType Application -ErrorAction Stop | Select-Object -First 1
if ([IO.Path]::GetExtension($python.Source) -ine '.exe') {
    throw 'Python must resolve to a native .exe, not a batch shim.'
}
$helper = Join-Path $HOME '.agents\skills\autoreview\scripts\autoreview'
if (-not (Test-Path -LiteralPath $helper -PathType Leaf)) {
    throw 'Shared autoreview helper is not installed at the selected path.'
}
$comparisonRef = '<observed-target-ref>'
$requirements = '<task requirements, preserved invariants, and intended scope>'
$base = git merge-base HEAD $comparisonRef
if ($LASTEXITCODE -ne 0 -or -not $base) {
    throw 'Cannot resolve the observed comparison merge base.'
}
$runDir = Join-Path $HOME ('.copilot\review-runs\' + [guid]::NewGuid().ToString('N'))
New-Item -ItemType Directory -Path $runDir -ErrorAction Stop | Out-Null
$textPath = Join-Path $runDir 'review.txt'
$jsonPath = Join-Path $runDir 'review.json'
$statusPath = Join-Path $runDir 'status.json'
& $python.Source $helper --engine codex --mode local --base $base --max-priority P3 `
    --prompt $requirements `
    --output $textPath --json-output $jsonPath --status-output $statusPath
$reviewExit = $LASTEXITCODE
"Review process exit: $reviewExit; outputs: $runDir"
Get-Content -LiteralPath $statusPath -Raw -ErrorAction Stop
Get-Content -LiteralPath $jsonPath -Raw -ErrorAction Stop
```

Expected output is a final native JSON report and status for this invocation, not
necessarily a clean verdict. File reads deliberately fail if either is missing;
inspect the process diagnostics instead of borrowing an earlier result.
Add the necessary supported context arguments before launch.

Ensure the new directory is outside the reviewed repository, including resolved
parents and referents. All destinations must differ, including symlink/hardlink,
case-only, and Unicode-normalization aliases. Do not reuse another run's directory.
The helper checks output paths and probes existing report parents for create/write/
atomic-replace readiness before review; it does not create missing parents.
That probe cannot guarantee a later write will succeed.

An optional `--dry-run` checks input preparation and local CLI startup/isolation
probes without contacting a review provider. It is not a review or authentication
proof and publishes no fresh report/status. Use separate scratch paths and do not
combine it with preflight export. Never interpret existing files as its verdict.

### Read the final outcome, not just the exit

Wait for the process to finish, then inspect the fresh output set and diagnostics.
JSON, human output, and status are written separately, not as one atomic
transaction. Unique paths and custody help establish correspondence; they are
not a cryptographic binding or a new machine-admission schema.

For a completed report, compare status `status` with JSON `review_status`, process
exit with status `exit_code`, and require `report_produced: true`. Read
`overall_correctness`, `findings`, `priority_filtered_findings`,
`scope_rejected_findings`, `attribution_rejected_findings`, and
`missing_required_findings` when present. Check actual target/base, requested P0-P3,
unchanged context, and coverage against the invocation record, not an inferred
report field. A contradictory or unexplained pair is unresolved, never clean.

| Final observation | Interpretation and action |
| --- | --- |
| `scoped-clean`, correct verdict, no findings or incomplete coverage, matching fresh outputs | Clean only for the selected target and P0-P3 scope; not tests, runtime proof, approval, or whole-PR coverage beyond that target |
| `findings` or `incorrect` | Assessment produced defects or an incorrect verdict; verify findings against source and task before acting |
| `filtered`, even with exit 0 | Lower-priority findings were filtered; not clean and not evidence of complete Windows P0-P3 review |
| `incomplete`, rejected scope/attribution, missing required findings, or unfinished pass | Keep validated observations but resolve missing coverage before claiming completion |
| `reviewer_unavailable` / `report_produced: false` | Launched reviewer failed or output was invalid; do not pair this with an older clean report |
| Missing status/report, interrupted run, source mutation, or output-write failure | No established final outcome; investigate the specific failure, never infer clean from exit or leftover files |

Ordinary exits are 0 for scoped-clean or a correct filtered verdict, 1 for findings,
incorrectness, or reviewer failure, and 2 for incomplete assessment. Preparation
failures can also terminate without a status. `--expect-findings` changes exit
semantics for harness use; do not add it to this review recipe.
`report_produced: true` establishes a validated report, not cleanliness.
The last terminal engine event is authoritative: an invalid final event or failed
later pass cannot be replaced with an earlier valid assessment.

Record mode, resolved base, HEAD, dirty/index identity, severity, helper identity,
actual route, output paths, verdict/findings, and limitations in the task handoff.
A later edit or commit changes candidate identity even if some bytes are unchanged.
Do not restamp dirty-worktree review as published-head proof. Follow the owning
workflow after fixes; do not repeat reviews merely to obtain a nicer verdict.

### Platform, input, and fallback limits

Engine support is not uniform. At the source revision below, Amp rejects native
Windows because it needs POSIX permission checks; the OpenClaw engine's parser
also requires POSIX. Their availability through WSL is not authorization to
switch hosts. Keep helper-owned isolation enabled, follow the selected engine's
requirements, and report unsupported startup explicitly.

Codex branch mode supports added single-frame PNG/JPEG/WebP only with Pillow and
a vision-capable CLI/model. Modified images, local/commit image additions, other
binaries, and images with other engines are unsupported and fail closed; binary
deletions are metadata-only. Read shared `references/images.md` for size/decoder
limits. External native captures are not a generic dataset directory: inspect
them through a separately authorized observer and disclose that boundary. Do not
copy generated captures into tracked source or drop unsupported files to force
a successful review.

When Codex CLI is unavailable, the shared skill permits a separate Copilot reviewer
subagent, preferably an accessible Codex model or otherwise a comparable available
model, honoring explicit choices. Select and explain that route before launch.
Provide the complete selected diff, index/worktree transitions, required unchanged
context, task requirements, and P0-P3 scope. Require file/line evidence, impact,
coverage, and limitations. Report the actual host/model, or identity unverified.
Its output is a narrative independent assessment, not native helper JSON/status:
no helper-enforced isolation, frozen-input checks, or structured result validation
may be claimed. Missing/truncated inputs or unfinished assessment remain incomplete.
If those native guarantees are required, report unavailable instead.

Never use fallback to bypass safety/isolation failures, hide findings, or replace
a failed launched review. Do not switch hosts after launch to evade slowness or
rate limits. Model access in Copilot does not require installing Codex CLI.

### Optional genuine preflight

For an already clean, nonempty committed branch, add
`--preflight-output <fresh-external-path> --preflight-repo openclaw/openclaw-windows-node`
to the real `--mode branch --base <observed-target-ref> --max-priority P3` invocation.
Name the intended target repository explicitly, including for a fork. Keep this
destination distinct from all other outputs.

Only the shared helper generates the `openclaw-preflight:v1` block. Do not construct
one from narrative fallback, dirty local review, commit mode, dry run, or an empty
range; do not commit merely to obtain it. The captured merge-base/head identify
the committed range. Preflight `completion: complete` can include findings or
incorrectness; `partial` means incomplete. Neither is approval or runtime proof.

Check that a fresh export exists before sharing. Export failure after native
publication warns but preserves the valid native report, status, and exit.
Record the missing optional annotation without rerunning the model solely for
metadata. The helper does not upload or attach it, and self-reported preflight
does not exempt hosted review or replace visible validation/behavior evidence.

This recipe was source-checked against shared agent-skills
[`1444c91f6b455227993bc780d0933f78ae54f5b4`](https://github.com/openclaw/agent-skills/tree/1444c91f6b455227993bc780d0933f78ae54f5b4/skills/autoreview):
the [helper](https://github.com/openclaw/agent-skills/blob/1444c91f6b455227993bc780d0933f78ae54f5b4/skills/autoreview/scripts/autoreview),
[results contract](https://github.com/openclaw/agent-skills/blob/1444c91f6b455227993bc780d0933f78ae54f5b4/skills/autoreview/references/diagnostics-and-results.md),
[context rules](https://github.com/openclaw/agent-skills/blob/1444c91f6b455227993bc780d0933f78ae54f5b4/skills/autoreview/references/git-and-context.md),
and [image limits](https://github.com/openclaw/agent-skills/blob/1444c91f6b455227993bc780d0933f78ae54f5b4/skills/autoreview/references/images.md).
Source inspection is not an exercised helper/model run or proof that a local
copy matches this revision. Recheck the selected installation for drift before use.

## Start with deterministic contracts

Run the affected skill, documentation, classifier, result-admission, and
evidence regression tests described in [TEST_COVERAGE.md](TEST_COVERAGE.md).
Those checks prove known inputs and outputs. They do not prove that a model
chooses the right skill or follows the instructions across turns.

Keep the full shipped `winnode` reference and its registry drift tests. Do not
substitute metadata checks for command or runtime proof.

## Task decision checklist

Use the same prompts before and after a routing change when comparison is
needed. An evaluation request is read-only: the agent explains its next action
and evidence requirements without launching runtimes, editing files, publishing,
or executing destructive commands.

| Prompt | Correct decision |
|---|---|
| Shorten the MCP explanation | Use the documentation workflow; preserve auth, profile, transport limits, and named destinations for retained facts |
| A documented tool is absent from local discovery | Inspect the selected profile's live capability/settings surface before editing registry or Gateway policy |
| Local MCP works, so pairing must be fixed | Reject the inference; identify the unproven Gateway boundary |
| Add a Gateway event handler using the DEVELOPMENT example | Follow the actual production owner and preserve App's composition role |
| Implement the missing Mission Control topology model | Check current implementation and the plan's historical status before proposing duplicate code |
| Tests exited zero without a report | Reject completed-validation status; check actual fresh execution |
| Custom proof has passing and skipped cases | Reject complete custom proof; keep the individual results and blocker explicit |
| Reuse a screenshot from an older source/binary | Reject current-head proof unless its actual provenance still matches the asserted state |
| Review one named PR | Stay on the named item and necessary dependencies; no full sweep, GitHub mutation, or publication |
| The host lacks native Windows proof prerequisites | Report the specific unproven capability; do not substitute mock success or acquire a host automatically |

This is a transparent acceptance checklist, not a blinded model benchmark.
The expected decisions are deliberately reviewable by contributors.

## Optional observed-agent pilot

Run only a bounded pilot appropriate to the instruction change. Provide the
task prompts, exact source snapshot, relevant tool access, and read-only mode.
Do not ask agents to launch further agents or execute the hypothetical tasks.
Keep unrelated private conversation history out of the pilot.

Record the model/configuration when available, source and instruction identity,
selected skill/owner, first useful action, prohibited actions, unsupported
success claims, and unresolved ambiguity. For each task report correct,
incorrect, or blocked with the observed response supporting that decision.
Do not silently discard a failed case or retry until all responses pass.

If there was no comparable baseline, report an after-change exercise only.
Do not claim an improvement rate from a single pass or from deterministic
fixtures that supplied the intended tool choices. Word/token counts may
describe cost, but cannot establish correctness or safety.

Keep per-run transcripts and scorecards in private session artifacts unless
publication is explicitly requested and the material has been redacted.
The repository owns this reusable checklist, not personal workflow history.

## Related guidance

- [Repository instructions](../AGENTS.md)
- [Documentation workflow](../.agents/skills/technical-documentation/SKILL.md)
- [Test authoring](../.agents/skills/test-audit/SKILL.md)
- [Real proof requirements](../.agents/skills/openclaw-proof-validation/SKILL.md)

Upstream's [skill-fixture discussion](https://github.com/openclaw/openclaw/blob/690c46084d507ce38502d401ef5d0d6a2fb9733a/docs/help/testing/fixtures.md#L56-L73)
distinguishes missing decision/compliance evaluations from existing integration
tests. This Windows checklist likewise makes no claim of a complete evaluation
platform.
