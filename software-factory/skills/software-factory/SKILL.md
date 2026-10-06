---
name: software-factory
description: Agree on a project specification with the user at development start or resumption, then coordinate authorized worker implementation, independent review, and the main agent's completion report, including needs and friction, harness, and agent memory management.
---

# Software Factory

Use two workflows: user + main specification agreement; then worker implementation → a different reviewer's review → main's completion report. Check the current start, resumption, or close context and authority. Preserve automatic skill selection; installation alone starts no development, daemon, or reporting enforcement. Use the user's preferred language, otherwise the conversation's language.

## Shared boundaries and records

- Prioritize the project's original AGENTS/override instructions. Refer conflicts to main and hold only affected work. Preserve user files, other workers' changes, and unrelated global settings.
- Main agrees specifications, assigns work, records decisions, compares evidence, and reports. Workers alone modify product code, tests, and configuration; main must not implement, hotfix, or act as fallback. Only main creates agents; workers/reviewers must not redelegate or substitute new chats. Missing required multi_agent tools holds affected implementation/review; independent discussion/research may continue.
- Require explicit scope, write set, and action authority. Spec approval alone authorizes no external writes, Issues, Git commit/push/PR/merge, or installation; automatic merge is prohibited. Improvement adoption authorizes no subsequent implementation, installation, or memory activation.
- Keep the package separate from the product repository. Use one collaboration Markdown file per cycle inside the project, default `SOFTWARE_FACTORY.<cycle>.md`. Agree its relative path, cycle identity, sole writer (main by default), and product/record write rights; resolve its actual location inside the project boundary and protect unrelated existing same-name files. Workers/reviewers read the latest cycle file and return facts for its sole writer to integrate; no concurrent record writers. Unknown or conflicting location/ownership holds only affected work for main; keep pending drafts in conversation, with no external-root fallback or unapproved overwrite. Backlog destinations and external actions still require project agreement.
- Before replacing current sections, the sole writer reads the latest version and ownership. Keep the current approved Markdown spec/approval/decisions, ten-field assignments, checkpoint, fixed target, decisive execution commands/outcomes/evidence/limits, and needs/friction/harness/memory assessment in this cycle file. Do not accumulate per-role logs, duplicate full histories, dated archives, second indices/logs, or permanent all-cycle state files. Preserve unresolved decisions/blockers, failed/unrun mandatory checks, relevant failure totals, retry/STOP/restart constraints, fixed identities, and decisive contrary/QA evidence until user acceptance. Reference existing safe evidence/logs or retain sufficient relevant raw passages here; missing critical proof leaves affected acceptance unverified. Existing external history is not deleted or migrated.
- Stable technical completion requires approved implementation, mandatory checks, different independent review and main's evidence comparison, with blocking matters resolved. Then submit the completed cycle/fixed target and limits to the user for review. Delete only the agreed literal cycle file after the user's explicit acceptance of that completed cycle/target and a fresh identity/path check confirming it remains inside the project, within applicable permissions/STOP policy. Internal reviewer/main PASS, initial spec approval, silence, unrelated acknowledgment, partial or unclear acceptance never authorizes deletion; retain the file and unresolved review state. This grants no directory/glob, product/log/history cleanup, archive/migration, Git or installation authority. Report cleanup failure without automatic destructive retries or broader cleanup.

## Workflow 1: Draft the specification with the user

Main maintains canonical Markdown requirements, constraints, acceptance criteria, and decisions in that cycle's file. Agree the items below; keep drafts/proposals distinct from approval and record unresolved questions with affected tasks/deps.

| Item | Agreement |
| --- | --- |
| Goal and scope | Behavior, targets, exclusions, representative success/failure cases |
| Completion | Observable criteria, required checks, evidence limits |
| Writes and records | Product write set, inside-project relative cycle-file path/identity and sole writer, separate external action authority |
| Version | Spec version, user approval evidence, change reasons, affected tasks/deps |
| Cycle | Scope and completion boundary; end date when needed, no fixed cadence |
| Retry policy | Applicable work/failure gates, limit, counting unit/increment point, preparation/partial/interrupted failures and unrun review, stop/resumption conditions and authority, evidence for policy changes |

Before development, require an approved spec/write set, worker, and different reviewer assignment. Version substantive specification changes with approval evidence and hand them to affected tasks. Missing required checks or a reached stop boundary leaves affected work waiting/unverified, not complete.

When drafting, substantively updating, or explaining specifications or major design, default to paired compact overview and UML-style design views in the same cycle file and Markdown spec/version. Use Mermaid where suitable: overall components/responsibilities/flow plus relevant class, sequence, or state detail. Honor user format/no-diagram preferences and original instructions; explain omission when a view adds nothing useful. Read the [diagram example](references/operating-examples.md#specification-diagram-example) for consistent status, updates, and evidence limits. Progress messages, logs, and packets do not each need views.

## Workflow 2: Implement, review, and report completion

Main assigns cohesive work by ownership, dependencies, uncertainty, and verifiable acceptance. Splitting packets creates no new approval unit or action authority. Every packet has ten fields:

`cycle`, `task`, `spec version`, `owner`, `allowed files`, `deps`, `acceptance`, `evidence`, `requested decisions`, `return limit`.

- `owner` distinguishes responsible role from the observed tool-provided executor ID/unique handle; nicknames are display only. Main supplies the creation/assignment mapping. If no ID is exposed, record `not provided`, observable execution reference, and assignment basis; never invent identity. Refer unclear responsibility, overlap, or independence to main. Missing ID alone needs no new user approval; renaming an implementer cannot establish independent review.
- `acceptance` includes checks and the approved stop policy; `deps`/`evidence` link contracts, policies, fixed targets, execution status, and failure checkpoints. `requested decisions` contains only unresolved matters/additional authority, otherwise `none`.
- Read original instructions → own packet → latest cycle-file ownership/version, checkpoint and approved spec/decisions → necessary files/evidence. Use current canonical pointers and bounded excerpts, not repeated whole chats, histories, or source collections. Link accepted intent and choice rationale to assigned ownership, fixed changes, and actual validation in this cycle file.
- Workers modify only allowed files and return evidence/limits for the same fixed target. Ordinary implementation/preparation corrections stay within approved behavior/API, acceptance, write set, action authority, permissions, and retry limits. Contract/acceptance changes, outside writes, new external actions, or environment/tool changes needing approval go to the decision-maker. Never weaken an oracle/check to hide violations.
- Main gives a different actual executor the approved spec, fixed diff/artifact hash or revision, actual verification evidence/limits, and necessary raw sources. Do not steer initial review with author thought processes/self-assessment or another reviewer's conclusions. Reviewers finish initial assessment before reading other independent reviews.
- Review specification compliance, patterns, completeness/failure handling, structure/dependencies/interfaces, merge/handoff risks, harness updates, and skill/material extraction needs. Main compares opinions with fixed evidence; changed targets require refreshed affected reviews.
- Checkpoints include task/spec, fixed target, completed artifacts, changed files, evidence, unresolved questions, next action, and role/executor ownership. Before overlapping handoff, confirm the old owner's write and related execution STOP. Carry exact product/record rights, approval basis, completed/failed/unrun checks, accumulated failures, and applicable policy. Resume only after checking current authority/version; changing task, executor, backend, or route resets no failures or unverified gates and expands no authority.
- Follow the project's retry policy without a common count/formula. Undefined policy holds only the affected retry for main's decision. Read uncertain external-write state before retrying.
- Link actual blockers to task questions/evidence/deps and hold only affected work. General needs/friction go in the completion handoff. Workers/reviewers return changed files, decisive raw evidence/limits, instructions used, observed problems/impact, and optional improvements to main within their return limit; main integrates necessary receipts/references into current cycle-file sections, without separate reports.
- Main reports evidence-backed results and unresolved matters; authors cannot approve their own completion. Artifact creation is not product completion, user acceptance, Issue closure, or merge authority. Main closes/reuses agents after handoff; reuse requires a new packet confirming authority/ownership.

### Proportionate verification and review

Main and reviewer choose checks for approved acceptance, changed surfaces/dependencies, or a specific failure risk. Exclude unrelated or unjustified repository-wide audits and repeated checks without a stated reason; note exclusions briefly in existing evidence.

Reuse relevant valid evidence for the same fixed target and applicable environment. Changes to source/configuration/environment or inconsistent/insufficient evidence require refreshed affected checks. A different reviewer still independently assesses the fixed changes and decisive raw evidence, not the author's PASS. Main compares that assessment with acceptance/evidence instead of duplicating the audit unless a specific contradiction, stale target, or gap warrants further verification.

Omit deployment/cache checks unrelated to the approved change/action and unjustified whole-system audits; retain integration/system verification justified by approved acceptance, original project instructions, affected surfaces, or a specific risk, including for source-only edits. Separately authorized publication/installation retains required provenance, version, and installed-artifact checks. Preserve original project instructions, mandatory gates, independent executors, fixed-target validation, action/approval boundaries, retry/STOP policy, and accumulated failures. Never call failed or unrun mandatory checks unnecessary; record unclear applicability as unverified for main.

Read only the relevant [operating example](references/operating-examples.md):

- [Preparation](references/operating-examples.md#preparation): applying an existing recipe.
- [Current state](references/operating-examples.md#current-state) and [collaboration trace](references/operating-examples.md#collaboration-trace-and-methods): canonical pointers and intent-to-evidence handoff.
- [Bounded evidence](references/operating-examples.md#bounded-evidence): source/path/field lookup.
- [Project quality checks](references/operating-examples.md#project-quality-checks): local/CI/static checks, required unrun gates, or original/variant source and build provenance/isolation.
- [Human manual QA](references/operating-examples.md#human-manual-qa-handoff): approved user verification.
- [Failure and resumption](references/operating-examples.md#failure-and-resumption): failed stages or incomplete checks.

After development ends and before the cycle's final report, read the [cycle close checklist](references/cycle-close-checklist.md). Integrate its five items into existing independent review/main assessment and link results to the latest fixed target; do not repeat it at startup or every task.

## Required brief sections in completion reports

Main keeps the current completion assessment in the cycle file and reports results, spec, changed files, verification/limits, unresolved decisions, next action, and ownership to the user. Include these brief sections there, without separate detailed reports:

### Needs and friction

Workers/reviewers supply task-linked observations, evidence, impact, and optional improvements. Main consolidates duplicates/priorities against the spec/evidence; the user decides adoption and reasons. Keep reports, consolidation, and adoption distinct.

### Harness

Report observed gaps/conflicts/failures/update needs in instructions, skills, tools, checks, and environments actually used, with evidence/impact. Without code or actual UI, claim no functional, visual, or accessibility tests.

### Agent memory management

Report observed context selection/reloading, summary loss, stale specs/decisions, and checkpoint/handoff/resumption issues. Refer safely to persistent-memory sources, validity, and sensitive-information risks only when actual use is confirmed; do not infer automatic memory state, creation, use, or effects.

Do not collect personal memory/authentication files, full prompts, secrets, raw personal information, hidden thought processes, or individual rankings/scores for reports. Distinguish observed, inferred, and unverified findings; absent evidence is `unverified`, no observed problem is `none (not observed)`, neither means `verified with no issues`. Prioritize evidence-backed findings without quotas or invented future work.
