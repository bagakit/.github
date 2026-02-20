# bagakit

`bagakit` 是一个 AI 编程 skill 组织，目标是把“个人经验”沉淀成“团队可复制的规模化提效机制”。

我们提供可组合、可审计、可恢复的 skill 组件，帮助团队把 agent 协作流程产品化，而不是停留在一次性提示词。

## Core Repositories

| Repository | Role | Key Capability |
| --- | --- | --- |
| [skills](https://github.com/bagakit/skills) | 发行与编排层 | submodule 统一版本、catalog、update/validate/release、安装入口 |
| [bagakit-living-docs](https://github.com/bagakit/bagakit-living-docs) | 规则与记忆层 | `docs/must-*.md`、inbox/memory、项目约束持续演进 |
| [bagakit-feat-task-harness](https://github.com/bagakit/bagakit-feat-task-harness) | 变更编排层 | feat/task 双层模型、worktree 隔离、task 小提交协议 |
| [bagakit-long-run](https://github.com/bagakit/bagakit-long-run) | 执行循环层 | 长会话执行表、门禁驱动推进、可恢复 loop |
| [bagakit-brainstorm](https://github.com/bagakit/bagakit-brainstorm) | 方案规划层 | 从 Markdown 上下文生成可执行方案、输出路由与归档闭环 |
| [bagakit-skill-maker](https://github.com/bagakit/bagakit-skill-maker) | 技能工程层 | skill 设计约束、payload 边界、validate 与重构方法 |

## What You Get

1. 以状态机和工件为中心的执行过程，而不是口头约定。
2. task 级可审计提交，便于 review、回溯和指标化治理。
3. 可中断恢复的长跑流程，支持跨会话持续推进。
4. 规则驱动联动（非硬编码耦合），可扩展到 OpenSpec、Bagakit F/T Harness 等多种 spec 系统。

## Install Skills In One Command

使用 `bagakit/skills` 仓库内脚本可自动检索并安装 skills：

```bash
curl -fsSL https://raw.githubusercontent.com/bagakit/skills/main/scripts/install-bagakit-skills.sh \
  | bash -s -- --dest ~/.codex/skills
```

默认会安装三件套：

- `bagakit-living-docs`
- `bagakit-feat-task-harness`
- `bagakit-long-run`

可按需追加：

- `bagakit-brainstorm`
- `bagakit-skill-maker`

常用参数：

```bash
# 仅检索可安装 skills
bash install-bagakit-skills.sh --list

# 安装组织下所有可检索到的 skills（包含 SKILL.md 的仓库）
bash install-bagakit-skills.sh --dest ~/.codex/skills --all

# 按需安装指定 skills
bash install-bagakit-skills.sh --dest ~/.codex/skills \
  --skill bagakit-living-docs \
  --skill bagakit-long-run
```

## Principles

- Rule-driven, not name-driven.
- Deterministic, not implicit.
- Small commits, explicit gates.
- Optional coupling, strong standalone behavior.
- Cross-skill signals via optional schema contracts; no direct required flow-calls.

## Collaborate

欢迎 issue / PR / 方案讨论。  
如果你在做 AI 编程流程化建设，欢迎一起共建可复制的工程能力。
