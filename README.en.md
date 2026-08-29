# DSHHelper — One task, one instance for DeepSeek Harness

[中文](README.md) · [User Guide](docs/user-guide.en.md) · [Releases](https://github.com/x102201/deepseek-harness-helper/releases)

**One directed task per instance, with a fixed plugin set; open several side by side when you need parallel work.**

<video controls poster="docs/assets/en/screenshot-main-light.png" width="720">
  <source src="docs/assets/video/dsh-helper-demo.mp4" type="video/mp4" />
</video>

[▶ Watch the demo](docs/assets/video/dsh-helper-demo.mp4)

---

## What happens when one workspace collects too many plugins

In DeepSeek Harness (dsh), a workspace can keep installing plugins. You can also use **Agent presets** to name “this composition” of tools and persona. Stack both habits in one home, and you often trap yourself.

![dsh default model](docs/assets/en/dsh-model.svg)

### Official model (source notes)

- An **Agent preset is the full capability composition** for that agent (tools, persona, prompt sections), carried as one `agent.cordis.yml`.
- **Only one preset mounts per session**; sibling presets stay deaf to each other.
- After a turn has run, switching presets is locked (`agent-preset-locked`) — two compositions must not register the same tool names into one layer.

Sources: [Agent Presets and Personas](https://deepseekdocs.com/en/docs/features/persona) · [per-session agent-presets design note](https://github.com/deepseek-ai/deepseek-harness/blob/master/.agents/notes/implemented/architecture/2026-08-03-per-session-agent-presets.md)

### What that felt like in practice

Plugins land in **this workspace**. Too many of them, and the tool list explodes — the model picks the wrong ones, and ability drops. A preset only switches “this conversation’s composition”; it does not clean the pile already in the workspace, and it cannot run “WeChat auto-reply” and “shopping helper” as two directed flows **at the same time without interfering**.

---

## How DSHHelper solves it

Split directed tasks into separate instances: one task per instance, fixed plugin set per instance. Need parallel work? Open them side by side.

![DSHHelper model](docs/assets/en/helper-model.svg)

![Quad-pane screenshot](docs/assets/en/screenshot-main-light.png)

---

## Shipping a tuned environment to someone else

I wired dsh to WeChat auto-reply and shopping help — an automation flow that already worked. Someone wanted to buy that capability. The workspace had so many plugins that even I could not say which plugins, which preset, and which config made “this flow”; delivering it meant days of reconstruction.

With **`.dshpack` packages**, you export that **already-tuned instance** as one file. The importer gets an interactive workspace, not a README. You can bind a machine code, set a password, and forbid re-export.

![Package flow](docs/assets/en/dshpack-flow.svg)

---

## User guide

Install, wizard, multi-instance, packages, and troubleshooting by chapter:

1. [Concepts](docs/user-guide.en.md#concepts)
2. [Install](docs/user-guide.en.md#install)
3. [First run](docs/user-guide.en.md#first-run)
4. [Workspaces](docs/user-guide.en.md#workspaces)
5. [Packages (.dshpack)](docs/user-guide.en.md#packages-dshpack)
6. [Data, migrate, uninstall](docs/user-guide.en.md#data-migrate-uninstall)
7. [Settings reference](docs/user-guide.en.md#settings-reference)
8. [Troubleshooting](docs/user-guide.en.md#troubleshooting)
