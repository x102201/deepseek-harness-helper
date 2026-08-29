# DSHHelper — Unlimited dsh instances on one desktop

[中文](README.md) · [User Guide](docs/user-guide.en.md) · [Releases](https://github.com/x102201/deepseek-harness-helper/releases)

**One desktop window. As many isolated DeepSeek Harness runtimes as you need. Each instance = a full, separate dsh.**

![Demo](docs/assets/video/dsh-helper-demo.gif)

[Download full demo (mp4)](docs/assets/video/dsh-helper-demo.mp4)

---

## 1. For yourself: one dsh cannot hold two jobs → one instance = one dsh

### Pain

You want WeChat sales, after-sales follow-up, and coding **all running at once**.

Out of the box you get one dsh (one `DSH_HOME`). Stuff every plugin into it and the tool list balloons — the model picks the wrong tools, and it gets **worse the more you add**. Agent presets do not save you: **only one mounts per session**, and switching after a turn is locked.

> Per DeepSeek Harness: [*Agent Presets and Personas*](https://deepseekdocs.com/en/docs/features/persona) · [architecture note *A session's agent is composed from a preset*](https://github.com/deepseek-ai/deepseek-harness/blob/master/.agents/notes/implemented/architecture/2026-08-03-per-session-agent-presets.md)

Two directed jobs in one workspace is not a tuning problem — **structurally, it does not fit**.

### Fix

Stop forcing everything into one dsh.  
**Each instance = one full, separate dsh** (own process, port, and `DSH_HOME`) — not a tab inside a single runtime.

Sales desk on the left, after-sales on the right, coding below — open as many as you need; plugins never mix.

![Quad-pane](docs/assets/en/screenshot-main-light.png)

---

## 2. For selling: days to make it work — then you still cannot ship or scale

You spent days getting WeChat auto sales talk working — plugins, presets, scripts, flow tuned piece by piece.

Then someone wants to buy it. What breaks is not “can they use it”, but that **every sale feels like rebuilding the project**:

1. **Cannot reproduce** — days later even you cannot say which plugins and which preset are “the product”; install for a customer drifts, another few days gone  
2. **Cannot hand off** — a README never installs cleanly; shipping the folder invites piracy / resale  
3. **Cannot sell to many** — customer two and three need the same remote grind; **delivery time dwarfs the time you spent building**, so you cannot scale sales

**`.dshpack`:** export that one tuned sales instance (one full dsh) as a file. They import and run. Bind machine code / password; forbid re-export — you sell a finished product, not install labor.

![Package flow](docs/assets/en/dshpack-flow.svg)

---

## User guide

1. [Concepts](docs/user-guide.en.md#concepts)
2. [Install](docs/user-guide.en.md#install)
3. [First run](docs/user-guide.en.md#first-run)
4. [Workspaces](docs/user-guide.en.md#workspaces)
5. [Packages (.dshpack)](docs/user-guide.en.md#packages-dshpack)
6. [Data, migrate, uninstall](docs/user-guide.en.md#data-migrate-uninstall)
7. [Settings reference](docs/user-guide.en.md#settings-reference)
8. [Troubleshooting](docs/user-guide.en.md#troubleshooting)
