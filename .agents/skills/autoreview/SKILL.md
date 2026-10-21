---
name: autoreview
description: Structured code review through the shared OpenClaw agent-skills installation.
---

# Auto Review

Use the canonical [autoreview skill](https://github.com/openclaw/agent-skills/tree/main/skills/autoreview).
Read the complete installed `~/.agents/skills/autoreview/SKILL.md` and the references
it requires before reviewing. If installed at another operator-selected location,
use that installation. This repository entrypoint contains no review implementation.

If the skill is missing, report it. Installation requires separate authorization:
reuse or clone `https://github.com/openclaw/agent-skills` and run
`python3 scripts/install-skills autoreview` from that checkout. On Windows, use
`python`; `--mode copy` is available when symlinks are unavailable.

Prefer the shared `scripts/autoreview` helper with Python from the repository being
reviewed, preserving its working directory. Follow the
[Windows invocation and result-reading recipe](../../../docs/AGENT_WORKFLOWS.md#run-a-scoped-shared-review)
before launch: explicitly select mode/base, use `--max-priority P3`, supply the
needed unchanged-owner context through supported inputs, and allocate distinct,
fresh output paths outside the repository. Default local mode does not include
earlier branch commits; branch mode excludes dirty work.

Read the final JSON and status together with the process outcome and coverage.
Exit zero, `report_produced: true`, `filtered`, or an old clean report is not a
complete P0-P3 clean assessment. Missing or inconsistent final outputs, incomplete
coverage, or a failed later pass must not inherit an earlier clean result.
Optional committed-branch preflight is advisory, not approval or runtime proof;
missing export alone does not require another model run.

If Codex CLI is unavailable, follow the canonical skill's independent Copilot
subagent fallback: prefer an accessible Codex model, or use a comparable available
model, honoring explicit choices. Model access through Copilot does not require
a separate Codex CLI installation. Supply the full selected scope, required
context, and P0-P3 severity; report actual host/model (or identity unverified),
coverage, and limitations as a narrative assessment. Never fabricate native
helper JSON/status, isolation, or frozen-input guarantees from fallback prose.
Missing context or unfinished assessment is incomplete. Do not switch routes
after launch to bypass failures, safety/isolation checks, or unfavorable findings.
Follow all other canonical and repository review requirements.

Keep shared fixes and instructions upstream in `openclaw/agent-skills`. Update
the shared checkout once for all symlinked consumers; reinstall copy-mode skills
after updating their source. Do not add repository-local helpers or test copies.
