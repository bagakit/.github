# bagakit

> 把 AI 编程经验升级为可复用、可审计、可回归的工程系统。

[![skills-validate](https://github.com/bagakit/skills/actions/workflows/validate.yml/badge.svg)](https://github.com/bagakit/skills/actions/workflows/validate.yml)
[![blog-pages](https://github.com/bagakit/skills/actions/workflows/blog-pages.yml/badge.svg)](https://github.com/bagakit/skills/actions/workflows/blog-pages.yml)

## Navigation

- Skills Catalog: https://github.com/bagakit/skills
- Engineering Blog: https://bagakit.github.io/skills/
- Blog Sources: https://github.com/bagakit/skills/tree/main/blogs

## Architecture

| Layer | Repository | Core Value |
| --- | --- | --- |
| Distribution & Orchestration | [skills](https://github.com/bagakit/skills) | submodule versioning, catalog, validation/release, install entry |
| Rules & Memory | [bagakit-living-docs](https://github.com/bagakit/bagakit-living-docs) | `docs/must-*.md`, inbox/memory contracts, evolving project constraints |
| Change Harness | [bagakit-feat-task-harness](https://github.com/bagakit/bagakit-feat-task-harness) | feat/task model, worktree isolation, small-commit protocol |
| Long-Run Execution | [bagakit-long-run](https://github.com/bagakit/bagakit-long-run) | resumable loop, gate-driven progression, long-session control |
| Skill Engineering | [bagakit-skill-maker](https://github.com/bagakit/bagakit-skill-maker) | portable skill design, standalone-first contracts, profile overlays |

## Why Teams Use Bagakit

1. **Artifact-first execution**：从“对话驱动”升级为“状态机 + 工件驱动”。
2. **Reviewable delivery**：task 级提交与门禁可追踪，回归成本低。
3. **Resumable operations**：长会话可中断恢复，跨轮次持续推进。
4. **Rule-driven coupling**：跨 skill 联动走 contract/signal，不走硬编码流程耦合。

## Install

```bash
curl -fsSL https://raw.githubusercontent.com/bagakit/skills/main/scripts/install-bagakit-skills.sh \
  | bash -s -- --dest ~/.codex/skills
```

默认安装：

- `bagakit-living-docs`
- `bagakit-feat-task-harness`
- `bagakit-long-run`

## Bootstrap-First (Recommended)

推荐用 `bagakit-bootstrap` 作为统一入口：

1. `skills`：先看远端 catalog 有哪些技能。
2. 如果本地已有技能源码，优先 `--source local-link`（SSOT，始终最新）。
3. 如果本地没有源码，再用 `--source remote` 拉取。
4. 执行前可先跑 `status --json` 查看目标目录状态和版本上下文。

## Design Principles

- Standalone-first, optional adapters.
- Rule-driven, not name-driven.
- Deterministic gates, not implicit conventions.
- Completion = action handoff + memory handoff + archive evidence.
- Prefer guidance packs first; promote to hard gates only when failure patterns prove it.

## Collaborate

欢迎 issue / PR / 方案讨论。  
如果你在建设 AI coding 流程化基建，欢迎一起共建可复制的工程能力。
