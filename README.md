# bagakit/.github

bagakit 组织主页与公共安装入口仓库。

## Contents

- `profile/README.md`: GitHub Organization Profile 页面内容。
- `scripts/install-bagakit-skills.sh`: bagakit skills 检索与一键安装脚本。
- `docs/skill-development.md`: BAGAKIT skill 开发规范（独立性、payload、运行/开发文件边界、AGENTS 驱动指令约定、跨 skill 的“可选且规则驱动”数据契约原则）。

## Core Principle (Cross-Skill)

- 每个 skill 必须 standalone。
- 跨 skill 只通过**可选**且**基于规则（schema/字段语义）**的数据契约交换信号。
- 不允许在默认流程里直接互相调用对方流程脚本作为前置条件。

Skill 设计基线参考：
- 官方 skill-creator 骨架/流程
- "The Complete Guide to Building Skills for Claude"

## Quick Start

```bash
curl -fsSL https://raw.githubusercontent.com/bagakit/.github/main/scripts/install-bagakit-skills.sh \
  | bash -s -- --dest ~/.codex/skills
```

安装脚本默认只安装 skill 运行载荷，不会把仓库开发/自举（dogfooding）文件（如 `docs/`、`Makefile`、`dist/`、`.codex/`）带进 skills 目录。

建议每个 skill 仓库在根目录提供 `SKILL_PAYLOAD.json` 来声明“哪些是正式安装载荷”（例如仅 `SKILL.md`、`references/`、`scripts/`，可选 `agents/` 等）。安装脚本会优先按该清单安装；若缺失则回退到安全默认规则。

更多参数：

```bash
bash scripts/install-bagakit-skills.sh --help
```
