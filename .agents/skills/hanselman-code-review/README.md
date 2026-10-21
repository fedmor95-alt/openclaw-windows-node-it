# Hanselman Code Review Skill

Repository-owned copy of the
[Hanselman adversarial review skill](https://github.com/shanselman/hanselman-code-review-skill).
The preferred pairing, when selectable under the host's policy, is
**GPT-6 Astra** (`gpt-6-astra`) and **Claude Opus 5.5** (`claude-opus-5.5`),
with high reasoning effort and Astra's supported `long_context` tier.
These are preferences, not guaranteed runtime settings. Follow the host's
selection policy and record the actual models and observable configuration;
unknown values remain unknown. Do not assume a numeric context-window size.

## Usage

Ask for a "Hanselman review", "adversarial review", or "dual-model review".
Follow [SKILL.md](SKILL.md) for exact scope, identical reviewer prompts, model
selection, consensus tables, and fix-confidence assessment. Neither a Codex
CLI nor a Claude CLI is required.

Repeat reviews can target changed code and unresolved findings. Always record
the actual model IDs used. If a model is unavailable, request approval for an
alternative rather than silently falling back to an older model.

This repository copy follows the existing OpenClaw proof and scope gates.
Source-review agreement does not replace runtime evidence.

## License

[MIT](LICENSE.md), copyright Scott Hanselman.
