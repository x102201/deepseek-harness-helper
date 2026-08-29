# DSHHelper — 一台电脑，无限多开 dsh

[English](README.en.md) · [用户指南](docs/user-guide.zh-CN.md) · [Releases](https://github.com/x102201/deepseek-harness-helper/releases)

**一个桌面窗口里，同时跑任意多个互不干扰的 DeepSeek Harness。每个实例 = 一整套独立的 dsh。**

<video controls autoplay muted loop playsinline poster="docs/assets/zh-CN/screenshot-main-light.png" width="720">
  <source src="docs/assets/video/dsh-helper-demo.mp4" type="video/mp4" />
</video>

[▶ 观看演示（若上方未自动播放）](docs/assets/video/dsh-helper-demo.mp4)

---

## 一、自己用：一套 dsh 装不下两套活 → 一实例一套 dsh

### 痛点

| 你想做的 | 现实 |
|----------|------|
| 微信卖货接待 + 售后跟单 + 写代码，**同时跑** | 默认只有 **一套** 工作空间（一份 `DSH_HOME`） |
| 每套活只用自己的插件 | 插件全堆进同一套 → 工具膨胀 → AI 选错工具 → **越装越废** |
| 用 Agent 预设切换「当前能力」 | **一次会话只能挂一套**预设；开过一轮再换会被锁 |

![痛点](docs/assets/zh-CN/dsh-model.svg)

依据：[Agent 预设说明](https://deepseekdocs.com/en/docs/features/persona) · [设计原文](https://github.com/deepseek-ai/deepseek-harness/blob/master/.agents/notes/implemented/architecture/2026-08-03-per-session-agent-presets.md)

**要并行多套定向能力，就要并行多套 dsh——不是在一个 dsh 里硬塞。**

### 解法

DSHHelper 在同一窗口里管理多个实例。  
**实例 ≠ 标签页。实例 = 独立进程 + 独立端口 + 独立 `DSH_HOME` = 完整的一套 dsh。**

![解法](docs/assets/zh-CN/helper-model.svg)

![四分屏实机](docs/assets/zh-CN/screenshot-main-light.png)

左边微信卖货接待、右边售后跟单、下面写代码——三套 dsh 并排跑，插件互不污染。

---

## 二、拿去卖：辛苦跑通了，却交不出去、卖不出去

花了好几天，才把微信自动沟通卖货跑通——插件、预设、话术、流程一点点调对。

然后有人要买。真正卡住的不是「会不会用」，而是**每次卖都像再做一遍工程**：

1. **复原不了** — 过几天连自己都说不清哪几个插件、哪份预设才是「这一套」；给客户装，装完对不上，又耗掉几天  
2. **交不出去** — 写说明书客户装不全；把目录打包又怕白嫖转卖  
3. **卖不了多个** — 第二个、第三个客户还要再远程折腾一遍，**交付时间远大于调功能的时间**，规模化卖不出去

**`.dshpack`：** 把已经调好的那一个卖货实例（一整套 dsh）打成文件。客户导入即用；可绑机器码 / 密码，可禁止再导出——你卖的是成品，不是陪装服务。

![制品流程](docs/assets/zh-CN/dshpack-flow.svg)

---

## 用户指南

1. [概念](docs/user-guide.zh-CN.md#概念)
2. [安装](docs/user-guide.zh-CN.md#安装)
3. [第一次启动](docs/user-guide.zh-CN.md#第一次启动)
4. [工作间](docs/user-guide.zh-CN.md#工作间)
5. [制品（.dshpack）](docs/user-guide.zh-CN.md#制品dshpack)
6. [数据、迁移与卸载](docs/user-guide.zh-CN.md#数据迁移与卸载)
7. [设置参考](docs/user-guide.zh-CN.md#设置参考)
8. [排错](docs/user-guide.zh-CN.md#排错)
