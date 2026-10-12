# Agent Task Resume 迁移后待办

- [x] 独立源码已位于当前目录并保留隐藏文件，本地 Git 已初始化，默认分支为 `main`。
- [x] 已创建公开 GitHub 仓库 `Laxpud/agent-task-resume`，核对仓库地址、双端 manifest 与安装说明；市场支持仍覆盖 Codex 和 Claude Code，执行适配目前只覆盖 Codex 与 Linux systemd。
- [ ] 验证 Codex 与 Claude Code 客户端的实际安装。
- [ ] systemd 模板已改用稳定安装目录，按 `skills/quota-resume/references/controller-usage.md` 部署后再切换旧调度。
- [ ] 切换既有调度时保留私有配置、回执和日志，确保同一目标只有一个投递者。
- [ ] 验证真实续跑、去重与停止行为，确定发布版本后再切换 Vibekits 的市场来源。
