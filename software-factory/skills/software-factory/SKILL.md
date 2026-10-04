---
name: software-factory
description: Agree on a project specification with the user at development start or resumption, then coordinate authorized worker implementation, independent review, and the main agent's completion report, including needs and friction, harness, and agent memory management.
---

# Software Factory

Use two workflows: user + main specification drafting; then worker implementation → a different reviewer's review → main's completion report under the approved specification. Operate within existing Codex access and the user's usage allowance. Installation alone does not start development, run a resident daemon, or automatically enforce reporting. Preserve the default automatic skill selection, while checking the current request's start, resumption, or close context and actual authority.

Use the user's explicit preferred output language; otherwise use the conversation's language. Report headings and evidence labels may use equivalent wording in that language.

## Shared boundaries and records

- Read and prioritize the original AGENTS/override instructions applicable to the current project. Ask main about conflicts and hold only the affected work. Preserve existing instructions, user files, and other workers' changes; do not change unrelated global settings.
- Main handles specification agreement, assignments, decision records, evidence comparison, integrated assessment, and reporting. Only workers write or modify product code, tests, and configuration. Main must not implement directly, hotfix, or act as an automatic fallback.
- Only main creates additional agents. Workers/reviewers must not delegate again or substitute a new Codex chat. If required multi_agent tools are unavailable, hold the affected implementation/review and report the tool limitation. Independent specification discussions and research may continue.
- Specification approval alone does not authorize external writes, Issue creation, Git commit/push/PR/merge, or installation. Check the target, action, and authority separately. Automatic merging is prohibited. Reporting or adopting an improvement does not authorize subsequent implementation, installation, or automatic memory activation.
- Keep the package separate from the original product repository. In the first specification, agree on a project-specific **absolute record root outside the repository**, record targets, and ownership. Resolve the actual repository and record root paths and confirm that records are outside the repository. Until agreed, drafts may remain in the conversation, but do not create operational files inside the repository. A plugin installation cache is not the project's record root.
- Once the record root is agreed, record specifications, decisions, packets, checkpoints, evidence, and project-specific needs/friction there within the approved scope. Distinguish product and operational record write sets. GitHub Issues is the authorized backlog destination; do not add automatic ticketing, synchronization, or Git batches.

## Workflow 1: Draft the specification with the user

Main reads only the needed portions of the current goal and existing decisions, then agrees on the following with the user. Record unresolved matters as questions with affected tasks/deps. Do not promote proposals, assumptions, or review opinions into approvals.

| Specification item | Agreement needed |
| --- | --- |
| Goal, scope, exclusions | Problem to solve, current targets, and exclusions |
| Completion criteria | Observable acceptance criteria, required verification, and its limits |
| Allowed writes | Target files and owners for product/operational records; separate authority for external actions |
| Record location | Project-specific absolute record root outside the repository; canonical documents and evidence locations |
| Version and change basis | Spec version, evidence of user approval, reasons for changes, and affected tasks/deps |
| Cycle | Current cycle scope and completion boundary agreed with the user; agree on an end date only when needed, without assuming a fixed cadence |

Keep drafts distinct from approved specifications. Develop only within a scope that has an approved specification, write set, worker, and independent reviewer assignment. Record specification changes with a new version and approval evidence, and hand them off to affected tasks.

A completion boundary can be the approved work, required checks, independent review, and main's evidence assessment/report. Missing required checks or reaching a retry/stop boundary is not successful completion; report affected work as waiting or unverified and seek direction under the project's approved policy.

When assessing whether an existing recipe fits the current work, read the [preparation example](references/operating-examples.md#preparation). It does not require a full audit for every task.

## Workflow 2: Implement, review, and report completion

Main divides work into small packets and resolves overlapping file ownership. Hand off overlapping write sets sequentially, confirming that the previous owner has stopped writing. Include these ten fields in every packet:

`cycle`, `task`, `spec version`, `owner`, `allowed files`, `deps`, `acceptance`, `evidence`, `requested decisions`, `return limit`.

Workers/reviewers read original instructions → their own packet → relevant records/checkpoint → approved specification version and decisions → necessary files/evidence. Load only relevant files/sections of specifications, decisions, and evidence into context; do not repeatedly load entire conversations, AGENTS histories, or source collections. These fields define handoffs, not product APIs, databases, or Issue state models.

Read only the relevant [operating example](references/operating-examples.md): [current state](references/operating-examples.md#current-state) when locating or updating current canonical pointers; [bounded evidence](references/operating-examples.md#bounded-evidence) when narrowing a lookup or recovering from a path/field error; [failure and resumption](references/operating-examples.md#failure-and-resumption) when a stage fails or work resumes with incomplete checks.

- Workers change only allowed files and return verification evidence against acceptance criteria, including limits from checks not run. Link actual blockers to the task's questions, evidence, and affected deps; hold only that work. General needs/friction do not automatically stop development; report them at completion.
- Only when comparing original code with a test variant, workers must confirm before comparison: actual paths and revision or other identifiers for both sources, build settings, and which source/build produced each executable or artifact to be run. Leave brief, safe evidence references. If shared caches or intermediate artifacts risk mixing sources or settings, use separate build directories within the approved write set. If provenance or necessary separation cannot be confirmed, state the comparison's verification limits and do not report it as a confirmed pass; continue unrelated tasks. This does not require separate directories for every test/project or authorize deleting shared caches, changing global environments, or adding tools.
- Main gives a reviewer other than the implementer the approved spec, fixed diff/artifact version (hash or revision), verification evidence/limits, and only necessary raw material. Do not steer the initial review with the implementer's thought process/self-assessment or another reviewer's conclusions. Reviewers must finish their initial review before reading other independent reviewers' results.
- Reviewers examine specification compliance, patterns, product completeness and failure handling, structure/dependencies/interfaces, merge and handoff risks, harness updates, and needs to extract skills/materials. Main compares those opinions with the specification and fixed evidence. After artifacts change, refresh affected reviews against the new version; do not carry forward an earlier pass.
- A checkpoint contains at least completed artifacts, changed files, evidence, unresolved questions, next action, and current ownership. Identify the task/spec version and fixed target too. Resume from the latest checkpoint after checking current authority/version. Resolve uncertain external write outcomes by reading their state, rather than unconditionally retrying.
- Workers and reviewers each return their task, instructions/references used, problems/needs/friction, evidence, impact, optional improvements, changed files, and verification limits. Keep detailed evidence in the agreed record root and the brief handoff within the return limit. Distinguish factual reports, main's consolidation of duplicates/impact/priority, and the user's adoption decision/reason.
- Main reports verified results and unresolved matters. Do not let implementers approve their own completion or equate artifact creation with product completion, user acceptance, Issue closure, or merge authorization. After handoff, main closes or reuses agents; reuse requires a new packet confirming authority and ownership.

Read the [cycle close checklist](references/cycle-close-checklist.md) only after development ends and before the cycle's final completion report. Integrate it into existing independent review and main's evidence comparison. Do not repeat the detailed checklist at startup, during ordinary development, or at every individual task completion. Link its results and the latest fixed target identifier in the completion report.

## Required brief sections in completion reports

Report results, spec version, changed files, verification/limits, unresolved questions, next action, and ownership, always including the three brief sections below. Do not create three separate detailed reports each time.

### Needs and friction

Main compares workers'/reviewers' tasks, evidence, impact, and optional improvements against the specification/evidence, consolidating duplicates and priorities. Present adoption decisions and affected work to the user. Gather general improvements after completion; link only actual blockers to their tasks during work.

### Harness

Briefly report observed gaps, conflicts, failures, or update needs in instructions, skills, tools, tests/verification, and execution environments actually used, with evidence, impact, and optional improvements. Without code or an actual UI, do not claim functional, visual, or accessibility tests were performed.

### Agent memory management

Report context selection/repeated loading, summary loss, stale decisions/specs, and handoff/checkpoint/resumption issues using observed evidence. Record safe source references, validity, and sensitive-information risks for persistent memory only when its actual use is confirmed. Do not infer automatic memory's on/off state, creation, use, internal state, or effects.

Do not collect personal memory/authentication files, full prompts, secrets, raw personal information, hidden thought processes, or individual rankings/scores for reporting. Distinguish observed, inferred, and unverified findings. Use `unverified` when evidence is absent and `none (not observed)` when no problem was observed; distinguish both from `verified with no issues`. Prioritize evidence-backed key findings in the chosen output language, aiming for 5–8 without inventing findings or an endless list of future features.
