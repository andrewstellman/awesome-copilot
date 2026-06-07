---
name: quality-playbook
description: "Run a complete quality engineering audit on any codebase. Derives behavioral requirements from the code, generates spec-traced functional tests, runs a three-pass code review with regression tests, executes a multi-model spec audit (Council of Three), and produces a consolidated bug report with TDD-verified patches. Finds the 35% of real defects that structural code review alone cannot catch. Works with any language. Trigger on 'quality playbook', 'spec audit', 'Council of Three', 'fitness-to-purpose', or 'coverage theater'."
license: Apache-2.0
compatibility: "Cross-platform. Requires Python 3.8+ and git. Install via `pip install quality-playbook` or `npx quality-playbook`."
metadata:
  version: "1.5.8"
  author: Andrew Stellman
  upstream: https://github.com/andrewstellman/quality-playbook
---

# Quality Playbook

Run a complete quality engineering audit on any codebase. Derives behavioral requirements from the code, generates spec-traced functional tests, runs a three-pass code review with regression tests, executes a multi-model spec audit (Council of Three), and produces a consolidated bug report with TDD-verified patches. Finds the 35% of real defects that structural code review alone cannot catch.

## Installation

This skill is distributed as a standalone toolkit because the full bundle
(seven phase-prompt directories, the citation verifier, the Council
runner, the bundled references, and the cross-platform install scripts)
exceeds the typical in-repo skill footprint. The canonical install is
one command:

```bash
pip install quality-playbook
# or
npx quality-playbook
```

After installation, run:

```bash
qpb install --into /path/to/your/repo
```

That copies the skill files (`SKILL.md`, `quality_gate.py`,
`references/`, `phase_prompts/`, `agents/`, `bin/citation_verifier.py`)
into the right place for your AI coding agent (Claude Code, Cursor,
GitHub Copilot CLI, etc.) — auto-detecting `.claude/`, `.github/`,
`.cursor/`, `.continue/`, `.codex/`, `.windsurf/`, `.cline/`, or
`.aider/`.

## What it does

When you (or your AI coding agent) say one of the trigger phrases —
"quality playbook", "spec audit", "Council of Three", "fitness-to-purpose",
or "coverage theater" — this skill drives the following workflow:

1. **Phase 1 (Explore)** — Documentation intake + three-stage codebase
   exploration. Writes `quality/EXPLORATION.md`.
2. **Phase 2 (Generate)** — Produces requirements, constitution,
   functional tests, code-review protocol, integration tests, spec-audit
   protocol, TDD protocol.
3. **Phase 3 (Code Review)** — Three-pass code review against HEAD;
   regression tests for every confirmed bug; patches.
4. **Phase 4 (Spec Audit)** — Three independent AI auditors review the
   code against requirements. Council-of-Three triage with verification
   probes. Layer-2 semantic citation check.
5. **Phase 5 (Consolidate)** — Combined bug report with TDD-verified
   patches.
6. **Phase 6 (Ship)** — Final ship-readiness verdict + AGENTS.md
   regeneration.

The trigger language is intentional: this is an opt-in heavy workflow
(it can take 30-90 minutes on a large codebase), not a always-on hook.

## License

Apache 2.0. Full terms in
[LICENSE.txt](https://github.com/andrewstellman/quality-playbook/blob/main/LICENSE.txt) in the canonical
repository.

## Canonical source

This skill is maintained at https://github.com/andrewstellman/quality-playbook. File issues and PRs there.
