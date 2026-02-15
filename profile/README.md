# bagakit

Reliable building blocks for long-running AI engineering workflows.

We build practical, composable tools that make agent work auditable, resumable, and easier to scale across sessions and teams.

## What We Build

| Repository | Focus | What You Get |
| --- | --- | --- |
| [bagakit-living-docs](https://github.com/bagakit/bagakit-living-docs) | Living documentation + project memory | `docs/must-*.md`, managed `AGENTS.md`, memory/inbox workflow, deterministic recall |
| [bagakit-feat-task-harness](https://github.com/bagakit/bagakit-feat-task-harness) | Feat/Task orchestration harness | OpenSpec-style change flow, per-feat worktree isolation, JSON SSOT state, task-level commit protocol |
| [bagakit-long-run](https://github.com/bagakit/bagakit-long-run) | Long-running coding loop | initializer/coding session loop, machine-readable feature state, repeatable health checks |
| [open-agent-avatars](https://github.com/bagakit/open-agent-avatars) | UI assets for agent products | production-ready animated SVG avatar packs for agent interfaces |

## Why This Stack

1. `living-docs` keeps project rules and memory continuously up to date.
2. `feat-task-harness` turns large goals into isolated, auditable feat/task execution.
3. `long-run` provides stable multi-session delivery loops for implementation work.
4. Combined, they form a full loop: **decide -> execute -> verify -> commit -> learn -> reuse**.

## Design Principles

- Deterministic over magical.
- Scriptable over manual.
- Small commits over large opaque diffs.
- State machines over ad-hoc progress tracking.
- Optional integrations, strong standalone behavior.

## Who This Is For

- Teams running agent-assisted software development.
- Builders shipping features across many sessions.
- Projects that need clear audit trails, recoverability, and repeatable workflows.

## Get Started

1. Install one or more skills from this org.
2. Bootstrap project docs/memory with `bagakit-living-docs`.
3. Start feature orchestration with `bagakit-feat-task-harness`.
4. Run long coding sessions with `bagakit-long-run`.
5. Keep every step validated, traceable, and reviewable.

## Status

Actively evolving. We optimize for real usage first, then abstraction.

## Contributing

Issues and PRs are welcome.  
If you are building long-running agent workflows, we’d like to collaborate.
