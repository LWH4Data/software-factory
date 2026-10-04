# Cycle close checklist

Read only after development ends and before the cycle's final completion report. Integrate this checklist into implementation, independent review, and main's completion report within the existing two workflows. Do not create a separate audit workflow, repeat it at startup/during ordinary development/at each task completion, or run continuous exhaustive audits.

Ongoing role policy is supplied by the applicable AGENTS.md.

## Fixed target and review

- Confirm the approved spec version/completion criteria, this cycle's changed files and directly related areas, the final fixed artifact hash or revision, and verification evidence/limits. Use existing packets/checkpoints/diffs and only necessary raw material. State the review scope, unreviewed areas, and unverified matters.
- A critical reviewer other than the implementer reviews that fixed final version. Do not require five separate agents, one per checklist item. If necessary tools are unavailable, hold only the affected review and report the limitation.
- Do not steer the initial review with the implementer's self-assessment/thought process or other independent reviewers' conclusions. The reviewer directly compares the approved specification, fixed artifacts, and verification evidence. If the target changes, refresh affected reviews against the latest hash or revision; do not carry forward an earlier pass.
- Main compares reviewer opinions with the specification/fixed evidence and consolidates duplicates, impact, and priorities. The user, as operator, decides which improvements to adopt and resolves necessary decisions.

## Five items

Review all five items, starting with areas directly related to this change. For each, distinguish observed, inferred, and unverified findings; use equivalent labels in the chosen report language. Length, call count, or dependency depth alone does not establish a defect. Use `none (not observed)` when no problem was observed; when evidence is insufficient or material is absent, state that scope and `unverified`. Do not invent problems to fill the checklist.

| Item | Assessment and evidence |
| --- | --- |
| Context | Assess how unnecessary repeated loading, stale decisions/specs, unrelated references, and separable materials affected actual work. Check the instructions/reference sections and checkpoints used. Identify candidates for keeping essential information in the body and situational detail in references. |
| Repeated roles as candidates for harness inclusion | Check each repeated role's source task, inputs/outputs, and evidence of actual value/cost. Do not decide inclusion from repetition count alone; propose reusable instructions/skills/materials with reasons. Do not direct automatic inclusion or construction of new runners/hooks. |
| Dependencies | Compare depth, cycles, unnecessary coupling, change propagation, and bottlenecks in code/package/task dependencies with related files, deps, and verification evidence. Assess whether depth is justified by required functionality and its actual impact; do not expand into an unrelated repository-wide investigation. |
| File indexing | Check relevant files/canonical sources, entrypoint/reference discoverability and freshness, and how broken links or stale paths affected handoff/resumption. Use existing files, documents, and search tools; do not direct creation of a new search database or a fully manual inventory of every file. |
| Code quality | Examine violations of the approved specification, error handling, duplication, excessive abstraction, insufficient verification, and failure handling in this change, directly related code, and verification evidence. If original code and a test variant were compared, check the worker's pre-comparison source/build settings/executable or artifact provenance, evidence of necessary build directory separation, and verification limits. Without code or an actual UI, state the limits and do not claim functional, visual, or accessibility verification was performed. |

## Findings and completion assessment

For each finding, record `item / observed·inferred·unverified / source task·file / evidence / impact / priority / optional improvement·required decision / affected task`. Use safe file/section references rather than lengthy raw material.

- **Completion-blocking defect:** Link actual defects against previously agreed completion criteria, or missing required verification, to the criteria, evidence, and affected tasks. Main compares the evidence and hands corrective work to the responsible worker within the approved scope. After correction, refresh affected independent reviews against the latest fixed version.
- **User decision needed / unverified:** If criteria are not agreed or evidence is insufficient for a conclusion, state the limit and let main request the necessary user decision. Distinguish this from missing agreed mandatory verification; do not arbitrarily promote it into a pass or failure. Identify affected work and work that can continue independently.
- **Next-cycle improvement:** General improvements do not block closure indefinitely. Main consolidates duplicates, impact, and priority; the user decides adoption. Adoption does not authorize implementation, harness inclusion, installation, external writes, or automatic memory activation. Do not modify automatically without a subsequent specification, write set, worker, independent review, and authority for each action.

## Connect to the completion report

Connect checklist results to the cycle, spec version, latest fixed target identifier, review scope/evidence/unreviewed and unverified areas for all five items, completion-blocking defects and next-cycle improvements, the independent reviewer's target/limits, main's evidence comparison, and operator decisions or unresolved decisions. Detailed evidence follows the agreed record root outside the repository and allowed write set. If the record location is not agreed, leave it in the conversation rather than creating files arbitrarily.

Integrate results into the existing required brief sections: `Needs and friction`, `Harness`, and `Agent memory management`, using the user's explicit preferred output language or otherwise the conversation's language. Do not require three additional detailed reports. Do not collect personal memory/authentication files, full prompts, secrets, raw personal information, individual rankings, or hidden thought processes. Use only safe source references for persistent memory whose actual use is confirmed; do not infer automatic memory's state, use, or effects.

Do not present document drafting or procedural checking as execution evidence for actual cycle checks, product tests, automatic skill loading, or automatic enforcement. Completing this checklist does not constitute user acceptance, Issue closure, or authorization for commit/push/PR/merge or installation.
