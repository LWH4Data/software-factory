# Software Factory

A Codex plugin for specification agreement with the user, implementation, independent review, and completion reporting. Plugin name: `software-factory`; marketplace: `software-factory-local`; package version: `0.1.7`. Public source repository: [LWH4Data/software-factory](https://github.com/LWH4Data/software-factory).

These files are the 0.1.7 release source for the English canonical instructions. Publication and installation updates require target-specific authorization and review. Source availability alone does not establish deployment, installation, actual skill loading, or runtime verification. See the [한국어 사용 안내](README.ko.md) for Korean usage guidance. English instructions do not set the response language: outputs follow the user's explicit language preference, or otherwise the conversation's language.

## Two workflows and roles

1. The user and main agree on goals, scope, exclusions, completion criteria, write authority, the inside-project cycle-file path/identity and sole writer, specification version, and the cycle scope/completion boundary. Agree on an end date only when needed; no fixed cadence is assumed.
2. Under the approved specification, a worker develops allowed files and a reviewer other than the implementer reviews the fixed artifacts. Main compares the specification and evidence, then reports results.

Version 0.1.7 defaults to complementary compact views when drafting, substantively updating, or explaining specifications or major design: an overview of components/responsibilities/flow paired with a relevant UML-style class, sequence, or state view, using Mermaid where suitable. Keep both with the same canonical Markdown specification/version and consistent status; honor user format preferences and explain an omitted redundant view. See the [paired-view example](software-factory/skills/software-factory/references/operating-examples.md#specification-diagram-example) for source and verification limits. Instructions have been trimmed while retaining the two workflows, role/authority boundaries, and brief report sections; load only situational references needed for the task. Static source checks establish neither model behavior nor efficiency gains.

Main handles agreement, assignments, decision records, integrated assessment, and reporting; workers write product code, tests, and configuration. Only main creates additional agents; workers/reviewers must not delegate again or substitute a new Codex chat. If required multi-agent tools are unavailable, hold the affected implementation/review and report the limitation. Original project instructions take priority.

Installation alone does not authorize or start development. There is no automatic merging, resident service, or automatic reporting enforcement. Check authority for each target/action separately for external writes, tickets, commit/push, PR/merge, and installation.

A cycle can end when its approved work, required checks, independent review, and main's evidence assessment/report are complete. Missing required checks or reaching the project's approved retry/stop boundary leaves affected work waiting or unverified. A necessary retry/stop policy that is undefined requires a decision before retrying; these common instructions do not set retry numbers.

Read only the relevant [operating example](software-factory/skills/software-factory/references/operating-examples.md): [preparation](software-factory/skills/software-factory/references/operating-examples.md#preparation) when checking a recipe's present applicability and verification means; [current state](software-factory/skills/software-factory/references/operating-examples.md#current-state) for current canonical pointers; [bounded evidence](software-factory/skills/software-factory/references/operating-examples.md#bounded-evidence) for a focused lookup or path/field error; [failure and resumption](software-factory/skills/software-factory/references/operating-examples.md#failure-and-resumption) for failed stages or incomplete checks. These examples require neither a new index nor a full audit per task. Keep paths, commands, and proof capture details project-local.

Only after development ends and before the cycle's final completion report, read the [cycle close checklist](software-factory/skills/software-factory/references/cycle-close-checklist.md). Integrate context, repeated roles as candidates for harness inclusion, dependencies, file indexing, and code quality into existing independent review and main's evidence comparison. Do not repeat it at startup, during ordinary development, or at each task completion. Link results and the latest fixed target identifier to the completion report. Distinguish completion-blocking defects from next-cycle improvements; the operator decides adoption.

## Reports and records

Use one collaboration Markdown file per cycle inside the project, default `SOFTWARE_FACTORY.<cycle>.md`. Agree its relative path, cycle identity and sole writer (main by default); resolve the inside-project boundary and protect unrelated existing same-name files. Workers/reviewers read relevant current state and return facts for main integration; serialize record ownership. Conflicting/unknown path or authority holds affected work, with no external-root fallback or unapproved overwrite. Original project instructions still take priority.

Main updates current spec/approval/decisions, ten-field assignments, checkpoints, fixed-target commands/outcomes/evidence/limits and completion assessments in this file, rather than accumulating per-role reports, duplicate full histories, archives, secondary indices/logs or permanent all-cycle state. Keep unresolved decisions/blockers, failed/unrun mandatory checks, relevant failure totals, retry/STOP/restart constraints and decisive contrary/QA evidence until user acceptance. Existing safe evidence/logs may be referenced; insufficient raw proof stays unverified. Existing external history is neither migrated nor deleted.

After approved implementation, mandatory verification, different independent review and main comparison resolve blocking matters, submit the completed cycle/fixed target and limits to the user. Only explicit acceptance of that completed cycle/target permits removal of the agreed literal cycle file after a fresh identity/inside-project path check, within applicable permissions/STOP policy. Internal PASS, initial spec approval, silence, unrelated acknowledgment, partial or unclear acceptance keeps the file. No directory/glob, product/log/history cleanup, archive/migration, Git or installation authority follows; report cleanup failure without automatic destructive retries. See the [current-state example](software-factory/skills/software-factory/references/operating-examples.md#current-state) for lightweight collaboration and serialized handoff.

The current completion assessment and user report include results, spec version, changed files, verification limits, unresolved questions, next action, ownership, and these brief sections, with equivalent headings in the chosen output language:

- **Needs and friction:** Main consolidates tasks, evidence, impact, and optional improvements; the user decides adoption. Only actual blockers hold the affected work.
- **Harness:** Report observed gaps, conflicts, failures, or update needs in instructions, skills, tools, verification, and environments actually used.
- **Agent memory management:** Report context selection/repeated loading, summary loss, stale decisions, and handoff/checkpoint issues. Do not read personal memory or authentication information for reporting, or infer automatic memory's state, use, or effects.

Distinguish observed, inferred, and unverified findings. Use `unverified` when evidence is absent and `none (not observed)` when no problem was observed; equivalent labels in the report language are allowed. Reporting or adopting improvements does not authorize subsequent implementation.

## Distribution source isolation

This repository root contains plugin distribution source separate from the product repository. The Git allowlist contains only these ten files; distribution source itself does not authorize Git writes or publication:

```text
.agents/plugins/marketplace.json
software-factory/plugin.json
software-factory/skills/software-factory/SKILL.md
software-factory/skills/software-factory/references/cycle-close-checklist.md
software-factory/skills/software-factory/references/operating-examples.md
README.md
README.ko.md
requirements-dev.txt
.gitignore
.gitattributes
```

Exclude project operational records, development artifacts, virtual environments, authentication material, secrets, environment files, and temporary files. `.gitignore` allows only the files above; inspect forced additions and already tracked files separately. `.gitattributes` disables text line-ending conversion for the five package files. The agreed cycle file stays inside its project and outside this separate distribution root/allowlist; installation caches are not collaboration-file locations.

## Install from a reviewed commit

Codex CLI is required. Reading the published public source does not assume private GitHub repository access. Public instructions do not substitute for installation/source-transition authorization. Do not store authentication information in distribution source.

First inspect existing sources:

```sh
codex plugin marketplace list --json
codex plugin list --json
```

If a marketplace named `software-factory-local` already exists, verify its `marketplaceSource` and the target plugin's source against the intended reviewed source. Reuse a verified matching registration under existing target/action authority; do not repeat registration. A different or unclear source requires a separately authorized transition before installation. Do not automatically overwrite a marketplace with the same name or delete it using `remove`.

For an authorized new registration with no name collision, use a published, reviewed commit. Replace `<reviewed-commit-sha>` below with the full SHA of the reviewed commit provided to you. Do not insert this README's own commit hash into it.

```sh
codex plugin marketplace add LWH4Data/software-factory --ref <reviewed-commit-sha>
```

After source verification and target installation/update authority are established, install or refresh only the target plugin. For an existing local source, first confirm its distribution checkout matches the published, reviewed commit and fixed package hashes.

```sh
codex plugin add software-factory@software-factory-local --json
```

After installation, use the inspection commands above to check source, version, and installed/enabled values, and compare installed package bytes/hashes with the reviewed source. Distinguish installation verification from actual skill loading and workflow compliance in a conversation.

Example request: `Use $software-factory to draft this project's development goals and specification with me.` For resumption/completion reports, also ask it to check the approved specification and latest checkpoint.

Official references for commands and marketplace format: [Package your plugin](https://developers.openai.com/plugins/build/plugins), [Developer commands](https://learn.chatgpt.com/docs/developer-commands).

## Development validation environment

`requirements-dev.txt` pins development-only validation dependencies (`PyYAML==6.0.3`; Python 3.8 or later). These are not runtime requirements for ordinary plugin installation. Use a separate virtual environment outside the distribution/product repositories. Do not change global Python, PATH, pip configuration, or an installed plugin.

From this distribution root, replace `<external-validation-dir>` with your chosen external validation directory and `<skill-creator-dir>` with the Skill Creator directory in your own Codex installation. Its `scripts/quick_validate.py` is a built-in helper, not a script shipped by this package. This PowerShell example avoids activation and shared pip cache writes:

```powershell
python -B -X utf8 -m venv "<external-validation-dir>/.venv"
$validationPython = "<external-validation-dir>/.venv/Scripts/python.exe"
& $validationPython -B -X utf8 -m pip --isolated install --no-cache-dir --only-binary=:all: -r ./requirements-dev.txt
& $validationPython -B -X utf8 "<skill-creator-dir>/scripts/quick_validate.py" ./software-factory/skills/software-factory
```

On POSIX systems, use the virtual environment's `bin/python` with the same requirements file and `-B -X utf8` validator arguments. `-B` suppresses bytecode writes; `-X utf8` selects UTF-8 mode. Record the interpreter, imported dependency provenance, fixed source hashes, and actual validator exit/output.

The automatic validator checks frontmatter, naming, and unfinished scaffold placeholders. It does not establish translation fidelity, sound decisions, product behavior, actual skill selection/loading, or GUI/accessibility results. Source freeze precedes validation; independent semantic review and main's evidence comparison remain necessary. Source validation alone does not establish publication, an installed-copy update, or runtime behavior.
