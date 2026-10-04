# Operating examples

Read only the situation relevant to the current work. Keep concrete paths, commands, and proof capture details in the project's agreed records.

## Preparation

A previously successful recipe looks suitable, but its assumptions may differ from the current contract or environment. Where the planned check depends on an existing interface, inspect the relevant actual definition/use and input/output assumptions, then confirm the recipe's current applicability, required tools, and available verification means. For example, a recipe expects a result field: confirm that field and its meaning in the current interface before using it as proof. Correct a mistaken invocation within existing authority; changing the contract or weakening the expected result requires the relevant decision. Past success is not proof of present compatibility. If a necessary means is missing, identify the affected work and verification limit, then continue independent work. This is a narrow contract/recipe check, not a full audit of all tests.

Reuse applicable existing recipes and native tools. A preparation error does not automatically justify a new collector, dependency, or tool/environment change. Put the verification plan and approved stop-policy reference in the packet's existing `acceptance`, with contracts, policies, and actual execution evidence linked through `deps`/`evidence`. Only missing decisions or additional authority belong in `requested decisions`. Prepared commands or authored artifacts do not establish that required checks ran.

## Current state

An index points to an older specification while a newer approved version exists. Check the canonical records before acting and update the existing suitable index or checkpoint with links to the latest canonical specification, approval, owner, checkpoint, and fixed artifact identifier. Identify who maintains those pointers. Keep histories, raw arrays, and logs in their source records rather than copying them into the index. If a pointer disagrees with its source, resolve that discrepancy against the canonical record; the index or a link cannot authorize work. No new index file is required.

A worker is being replaced while still writing. Main first confirms the old owner's write and related execution STOP, then hands off exact product and record file rights, approval/spec and fixed target, role/actual executor mapping, unresolved matters, completed/failed/unrun checks, accumulated failures and policy, and next action in the existing packet/checkpoint. Until STOP is confirmed, hold the overlapping work; independent work may continue. The replacement receives remaining authority and check history, not a fresh failure budget. Main may keep authorized preparation, implementation, verification, and freeze in one cohesive packet or split them where dependencies or independent acceptance warrant it.

If the tool provides no executor ID, record `not provided`, an observable execution reference, and main's assignment basis. Do not use a fabricated UUID or nickname as identity/independence evidence. Ask main only if responsibility, overlap, or independence remains unclear. A former implementer renamed or assigned the reviewer role still cannot independently review their own artifact.

## Bounded evidence

A lookup returns the wrong path or a field that is absent in the actual source. Discover the relevant source, inspect the necessary section or field, then cite its safe fixed identifier and location. On a path or field error, simplify the lookup and confirm the actual source before narrowing again. Preserve conditions that change the conclusion and relevant contrary evidence in the cited section. Short output alone does not establish correctness; a bounded excerpt that omits a decisive condition is insufficient. Use the project's source and evidence conventions without imposing common tool syntax or an output cap.

## Failure and resumption

A verification stage cannot run because its environment is unavailable, or runs and finds a product defect. Record the cause/category separately from check status: an environment/tool failure does not by itself establish a product failure, and partial verification leaves the remaining gates unverified. In the existing handoff or checkpoint, identify the failed and last completed stage, fixed target, evidence, checks not run or unverified, affected work, and conditions for restarting.

Follow the project's approved retry, stop, and authorization policy. Agree per project on applicable logical work/failure gates, limit, counting unit and increment point, treatment of preparation failures, partial/interrupted corrections and unrun review, stop conditions, who may resume and with which actions, and authority/evidence for changing counts or scope. There is no common count or formula. If a necessary policy is undefined, hold only the affected retry and refer that decision to main. Classifying a failure as environmental does not automatically exclude it from the count.

For example, a preparation stage fails before independent review runs. A replacement worker uses another backend or task name: retain the same logical failure, accumulated attempts, exact rights, fixed target, failed stage, and unrun review gate. A different route may fix the cause within authority, but does not erase checks or authorize a retry beyond policy. Record any authorized scope/count transition with its decision-maker and approval evidence; a new packet name or main's explanation alone is insufficient.

Counting a related feedback bundle → worker correction → independent re-review as one attempt is an **explicitly unapproved candidate**, not a default. Counting only completed bundles, or continually appending new errors, could hide repeated partial preparation failures. Do not adopt it until the project decides bundle boundaries, partial/interrupted failure and unrun-review treatment, and stop/resumption authority. Approval of this common skill does not change an existing project's policy.

Missing mandatory proof or a reached stopping condition cannot become a pass. Give the independent reviewer the fixed artifact and actual execution evidence/limits for that version; after a change, refresh affected review. Static document checks do not prove runtime or model behavior or efficiency gains. A cycle may close before a planned date when its agreed completion boundary is met; unresolved required checks still prevent completion. Do not continue merely to fill a calendar period.
