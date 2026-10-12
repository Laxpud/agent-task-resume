# Agent Task Resume

[English](../README.md)

本仓库包含独立插件 `agent-task-resume` 的源码；部署迁移与真实续跑验证仍待完成。剩余工作见[迁移后待办](../MIGRATION.md)。

## 技能

- [quota-resume](../skills/quota-resume/SKILL.md)

执行适配目前覆盖 Codex 与 Linux systemd；安装插件不会启动调度器。安装和运维见[控制器说明](../skills/quota-resume/references/controller-usage.md)。

## 安装

使用下方命令从 `Laxpud/agent-task-resume` 安装；若地址变更，同步修改 plugin-catalog.json 的 publisher.homepage、publisher.repository 和中英文安装命令，再重新生成元数据。

在终端添加 Codex marketplace：

~~~bash
codex plugin marketplace add Laxpud/agent-task-resume
~~~

在 Codex 输入区打开列表，安装 `agent-task-resume`：

~~~text
/plugins
~~~

在 Claude Code 输入区依次执行：

~~~text
/plugin marketplace add Laxpud/agent-task-resume
/plugin install agent-task-resume@laxpud-agent-task-resume
~~~

安装后新建任务或会话。最小提示词：

~~~text
Use $agent-task-resume:quota-resume to schedule this authorized task to resume after its five-hour quota recovers, track execution, and stop on completion or required user action.
~~~

## 维护

plugin-catalog.json 是元数据维护入口；两端 manifest 和用于独立调试的 marketplace 均由脚本生成，指向本仓库根目录。从本目录运行检查：

~~~bash
python3 scripts/sync_plugin_metadata.py --write
python3 scripts/sync_plugin_metadata.py
python3 scripts/check_codex_install.py --all
python3 scripts/check_markdown_links.py
~~~

以上只检查本地元数据和文件，不代表两端客户端安装或实际执行已通过。使用 `python3 scripts/check_codex_install.py --remote --ref main --all` 检查 GitHub 副本。部署迁移、客户端实际安装、真实续跑验证与版本发布仍保留为 MIGRATION.md 中的待办；npx skills 分发尚未验证。

## 许可证

[MIT](../LICENSE)
