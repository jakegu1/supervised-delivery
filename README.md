# supervised-delivery

An instruction-only skill for delivering a bounded software milestone with a lead, an executor, and independent review. Give the executor a complete packet and room to finish ready work. Give the reviewer a fixed candidate, the original acceptance criteria, and evidence they can reproduce.

The core workflow is intentionally kept stable. Try it on one bounded milestone with the agent sessions, permissions, and repository rules you already use. Revisit the guidance when actual use exposes a defect, a privacy issue, or a platform change.

## When to use it

Use it when work needs sustained execution, clear ownership, or independent verification of a risky handoff. Keep a small, reversible edit in one session and run a proportionate check. Start with one executor. Add workers only when tasks have independent scope and the host has capacity.

| If you need | Consider |
| --- | --- |
| A fresh implementer and mandatory spec and quality verdicts for each task | [Superpowers subagent-driven development](https://github.com/obra/superpowers/blob/22f0b463e7a5e579904dd6211a520321035526f7/skills/subagent-driven-development/SKILL.md) |
| Dependency waves, phase tracking, and phase-level verification | [Get Shit Done phase execution](https://github.com/gsd-build/get-shit-done/blob/bdcaab2c752d9a33a1a1ca9acf3a3c81fb991815/get-shit-done/workflows/execute-phase.md) |
| A build workflow that develops a rough intent, or a review with several lenses | [BMad build](https://github.com/bmad-code-org/BMAD-METHOD/blob/a867e1604b365d48ea03cbd109da1066ba0c84bc/docs/build/build-a-change.md) and [BMad review](https://github.com/bmad-code-org/BMAD-METHOD/blob/a867e1604b365d48ea03cbd109da1066ba0c84bc/docs/build/review-a-change.md) |
| Change specifications and a check against implementation or scenario coverage | [OpenSpec commands](https://github.com/Fission-AI/OpenSpec/blob/a959be77cf045ea3156dc5089c9e2f1d6ce9ce70/docs/commands.md) and [OpenSpec verify](https://github.com/Fission-AI/OpenSpec/blob/a959be77cf045ea3156dc5089c9e2f1d6ce9ce70/src/core/templates/workflows/verify-change.ts) |
| A pre-implementation check of spec, plan, and task coverage | [GitHub Spec Kit analyze](https://github.com/github/spec-kit/blob/f29319d550d1f05404f7184b92e995600ca2293f/templates/commands/analyze.md) |

Supervised Delivery uses a short packet and a current-state record, and reuses the repository's existing rules. Its tradeoff is that the lead must define the contract, track real session and candidate identities, and organize the review through available tools.

## Set up the skill

1. Copy `SKILL.md`, `agents/openai.yaml`, and both files under `references/` into one `supervised-delivery` folder. Keep the relative paths and the [license notice](LICENSE).
2. In a Codex project, place the folder at `.agents/skills/supervised-delivery/`. Select it in the skills picker or mention `$supervised-delivery` where explicit invocation is supported. [Codex skill discovery](https://learn.chatgpt.com/docs/build-skills#where-codex-loads-local-skills)
3. In a Cursor project, place it at `.cursor/skills/supervised-delivery/`. Check that Agent discovers it in that workspace. Remote workers need access to the skill files in their own environment. [Cursor skill discovery](https://cursor.com/docs/skills)

If the host cannot discover skills, ask the agent to read [SKILL.md](SKILL.md) and the [handoff templates](references/milestone-packet.md) directly. Check the [platform adapters](references/platforms.md) for tool availability and a file-based fallback.

## Run a milestone

The **lead** freezes the outcome, baseline, owned files, acceptance checks, and stop conditions. The **executor** implements and verifies the ready sequence, then returns a fixed commit or artifact, check results, and gaps. A **reviewer** with fresh context independently checks that candidate against the same criteria. The lead makes the final judgment and records any remaining human or release action.

For example:

> Use $supervised-delivery to add a status filter to a community center's event list. Start at the agreed baseline and keep changes in the event list and its tests. Check the filter from the events page, verify that a shared filtered URL opens in the same state, and keep the default view showing all events. Return the candidate commit and evidence for independent review. The repository owner handles integration and release.

Stop at the agreed milestone boundary. Escalate a concrete decision, missing authorization, or an unresolved gap with the evidence needed to act. If observation of an existing job times out, check the same job and record the last confirmed state. If a human check remains open, report the completed checks and what still needs to happen.

## Validation and limits

Independent review exercised the core rules in four bounded scenarios: reusing an existing acceptance contract, handling a candidate with incomplete evidence, routing a one-word edit directly, and preserving the identity of a remote job after observation stopped. Dispatch and remote state were simulated. Local files and packaging were also checked. Live cross-platform agent execution, throughput, and cost savings remain unverified. Scheduling and enforcement stay with the host and repository. The workflow depends on the available tools, a clear acceptance contract, and effective independent review.

Workflow direction by [jakegu1](https://github.com/jakegu1). AI-assisted design, writing, and verification. Released under the [MIT License](LICENSE).
