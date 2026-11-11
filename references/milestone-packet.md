# Milestone packet and handoffs

Use the repository's equivalent records where available. For a standalone workflow, one short Markdown packet and a compact status record are sufficient. Trim fields whose answers are already clear from the inherited contract.

## Packet to freeze before implementation

```text
Milestone and revision
User outcome and exit criteria:
Baseline and exact review target convention:
Owned scope and explicitly excluded work:
Applicable project instructions and integration rules:
Ordered tasks (ID, ready/parked, owner, files/resources, prerequisites):
Prerequisite evidence needed (implemented, verified, reviewed, or user action):
Invariants and consequential edge cases:
Checks (command/action, expected behavior, environment, evidence location):
Decisions already made and safe defaults:
Authorization and human/external gates:
Retry boundary, escalation triggers, and stopping point:
```

Pick an exit condition the lead can verify at the actual entry point. Define what to observe for high-risk claims and what would falsify them. A new material requirement changes the packet revision with a reason and affected checks. Keep evidence from earlier revisions labelled with the corresponding contract and candidate.

## Portable state

```text
Milestone / packet revision:
Current stage (ready, executing, ready for review, reviewing, accepted, blocked, or complete):
Baseline / current candidate (commit or artifact hash):
Executor / reviewer (platform, session ID or URL, workspace, last cursor if available):
Completed work / compact evidence:
Next action and who owns it:
Open gate, reason, and next evidence needed:
```

Update when a candidate, decision, or blocker changes. Record an unavailable capability as such. When the platform needs manual transport, the same state keeps work resumable after the current chat ends.

## Dispatch packet

Use an existing authorized route when available. Otherwise give the user one file or message to paste into the target chat. Include the skill folder or its relevant files when the target cannot discover them. Keep secrets and unrelated history out of the packet.

```text
You are the executor for <milestone>. Read the applicable project instructions
and <packet or full packet text>. Work from <baseline> in <workspace>.
Own <scope>; start <first ready task>. Continue through the ordered ready
tasks when each stated prerequisite is met. Use the packet's defaults and
authorization. Fix and verify failures within scope.
Return the pinned candidate, delivered outcome, commands and results,
evidence paths, and any unresolved gate. Escalate only a concrete decision
that cannot be made within the packet.
```

Give a fresh reviewer the same acceptance criteria and baseline plus the actual candidate and compact diff. Ask for an independent verdict with check outputs and a consolidated list of defects. Do not rely on the executor's implementation narrative as proof. When review cannot be performed, report the completed checks and the open independent-review gate.

## Executor and reviewer handoffs

```text
Executor
Outcome delivered:
Exact baseline and candidate:
Owned changes:
Checks and evidence (include failure and retry provenance):
Required checks that failed or remain unverified:
Specific blocker or request, if any:

Reviewer
Exact candidate and contract revision:
Checks independently verified and evidence:
Findings (impact, reproduction, affected criterion, required correction):
Verdict and remaining gates:
```

If an Owner action is required, preflight the real handoff first. Give the Owner the minimum exact actions, the expected completion signal, and a way to stop. Store progress incrementally. For a partial run, report which actions actually completed and leave the cause unknown when evidence cannot establish it.

## 可直接复制的中文用法

> 使用 $supervised-delivery。目标是把「填写可验收结果」交付成一个固定候选。请由 lead 定范围、验收条件和关键决策，执行会话负责细化、连续完成已就绪任务并整理证据，最后请独立 reviewer 复核。沿用仓库现有合同和授权，常规步骤自行推进。只有需要我决定或亲自验证时才汇总来问。
