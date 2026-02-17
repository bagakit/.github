# BAGAKIT Skill Development Guide

This guide defines the baseline rules for developing and maintaining skills in BAGAKIT repositories.

## 1) Standalone-First Skills (No Hard External Dependency)

Skills MUST be independently usable without requiring external ecosystems (for example OpenSpec or any other non-BAGAKIT system).

Required policy:
- Core workflow must run with only the skill's own runtime payload.
- External integrations must be optional and explicit (adapters, optional manifests, import/export helpers).
- Do not hardcode mandatory cross-repo or remote URL dependencies into default gates.

Recommended checks:
- Add repository tests that fail if default profiles reintroduce required external dependencies.
- Keep compatibility profiles separate from core/default profiles.

## 2) Runtime vs Development Files

Skill repositories MUST clearly separate runtime payload from development/dogfooding files.

Required layout intent:
- `scripts/` => runtime scripts used by installed skills.
- `scripts_dev/` => development-only scripts (self-tests, local validation helpers, release checks).
- `docs/`, `Makefile`, `.codex/`, `dist/`, etc. => repository development assets, not skill runtime payload by default.

## 3) `SKILL_PAYLOAD.json` Is Required

Each skill repository MUST provide `SKILL_PAYLOAD.json` at repo root.

Purpose:
- Explicitly declare installable runtime payload.
- Prevent accidental installation of non-runtime repository files.
- Allow installer tooling to be deterministic and auditable.

Minimum example:

```json
{
  "version": 1,
  "include": [
    "SKILL.md",
    "README.md",
    "references",
    "scripts"
  ]
}
```

Notes:
- All `include` paths must be relative.
- `SKILL.md` must always be included.
- `scripts_dev/` should not be included unless intentionally shipped as runtime.

## 4) AGENTS Driving Instructions (`[[BAGAKIT]]` Footer Contract)

When a skill needs explicit execution-driving outputs, encode that in AGENTS managed instructions.

Required style:
- Use `[[BAGAKIT]]` as the footer block anchor.
- Add skill-specific driving lines as peers under the same block.
- Keep `- LivingDoc: ...` and skill-specific lines parallel, not nested under each other.

Example:

```md
[[BAGAKIT]]
- LivingDoc: Updated docs/must-sop.md for this change.
- LongRun: Item=EXEC::foo; Status=in_progress; Evidence=tests passed; Next=run doctor.
```

## 5) Repository Self-Gates

Each skill repository SHOULD enforce these rules via self-tests:
- docs policy assertions (policy text exists in canonical docs);
- payload assertions (`SKILL_PAYLOAD.json` correctness);
- manifest/profile assertions (core profile has no hard external dependency);
- end-to-end sanity tests for runtime scripts.

Development tests should run from `scripts_dev/` and must not be part of installed runtime payload by default.

