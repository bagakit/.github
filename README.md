# bagakit/.github

bagakit 组织主页与公共安装入口仓库。

## Contents

- `profile/README.md`: GitHub Organization Profile 页面内容。
- `scripts/install-bagakit-skills.sh`: bagakit skills 检索与一键安装脚本。

## Quick Start

```bash
curl -fsSL https://raw.githubusercontent.com/bagakit/.github/main/scripts/install-bagakit-skills.sh \
  | bash -s -- --dest ~/.codex/skills
```

安装脚本默认只安装 skill 运行载荷（`SKILL.md`、`scripts/`、`references/`、可选 `agents/`/`assets/`/`README.md`），不会把仓库开发文件（如 `docs/`、`Makefile`、`dist/`、`.codex/`）带进 skills 目录。

更多参数：

```bash
bash scripts/install-bagakit-skills.sh --help
```
