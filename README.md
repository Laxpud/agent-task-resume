# Agent Task Resume

[简体中文](docs/README.cn.md)

Explicitly invoked guidance for resuming authorized work after short-term or weekly quota recovery, with execution tracking and permission-bound reset credits.

This repository contains the standalone plugin named `agent-task-resume`. Deployment migration and live continuation validation remain pending. See [remaining migration work](MIGRATION.md).

## Skills

- [quota-resume](skills/quota-resume/SKILL.md)

Execution guidance currently covers Codex and Linux systemd. Installing the plugin starts no scheduler. See [controller operations](skills/quota-resume/references/controller-usage.md).

## Installation

Install from `Laxpud/agent-task-resume` using the commands below. If the repository address changes, update publisher.homepage and publisher.repository in plugin-catalog.json and both README files, then regenerate metadata with --write.

Codex, in a terminal:

~~~bash
codex plugin marketplace add Laxpud/agent-task-resume
~~~

Then open the plugin picker and install `agent-task-resume`:

~~~text
/plugins
~~~

Claude Code, in the client input area:

~~~text
/plugin marketplace add Laxpud/agent-task-resume
/plugin install agent-task-resume@laxpud-agent-task-resume
~~~

Start a new task or session after installation. Example prompt:

~~~text
Use $agent-task-resume:quota-resume to schedule this authorized task to resume after its five-hour quota recovers, track execution, and stop on completion or required user action.
~~~

## Maintenance

plugin-catalog.json is the metadata source. Generated manifests and local authoring marketplaces point to this repository root. Run these commands from this directory:

~~~bash
python3 scripts/sync_plugin_metadata.py --write
python3 scripts/sync_plugin_metadata.py
python3 scripts/check_codex_install.py --all
python3 scripts/check_markdown_links.py
~~~

These checks verify local metadata and files; they do not prove installation or execution in either client. To check the GitHub copy, run `python3 scripts/check_codex_install.py --remote --ref main --all`. Deployment migration, client installation, live continuation validation and a versioned release remain pending in MIGRATION.md. Direct npx skills distribution is not verified.

## License

[MIT](LICENSE)
