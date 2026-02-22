# bagakit/.github

这个仓库只保留组织展示内容：

- `profile/README.md`: GitHub Organization Profile 页面内容
- `README.md`: 仓库说明与跳转入口

Skill 的安装脚本、开发规范与编排能力已统一迁移到：

- [bagakit/skills](https://github.com/bagakit/skills)

推荐分发入口（SSOT）：

- 优先使用 `bagakit-bootstrap` 做技能发现与安装/更新（`skills/install/update/status`）。
- 若本地已有技能源码，优先 `--source local-link`，让项目 `.codex/skills` 始终指向最新源码。
- 若本地没有源码，再用 `--source remote` 远端拉取。
