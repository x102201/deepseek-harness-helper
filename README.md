# DSHHelper — 一台电脑，无限多开 dsh

[English](README.en.md) · [用户指南](docs/user-guide.zh-CN.md) · [Releases](https://github.com/x102201/deepseek-harness-helper/releases)

![演示](docs/assets/video/dsh-helper-demo.gif)

[下载完整演示视频（mp4）](docs/assets/video/dsh-helper-demo.mp4)

我这边常年几套活同时转。默认只有一套 dsh，硬塞进去会越装越废——所以做成了这个：
**一个桌面窗口里，同时跑任意多个互不干扰的 DeepSeek Harness。每个实例 = 一整套独立的 dsh。**

---

## 一、隔离：一套 dsh 装不下两套活

### 痛点

我这边常年三条线并行：一边是客户消息，一边是代码，一边是测试和报告。

默认只有一套 dsh（一份 `DSH_HOME`）。插件全往同一个工作空间里塞，工具列表一长，AI 就开始挑错——不是我不会配，是三套完全不搭边的能力硬塞进一套预设，**结构上就装不下**。

Agent 预设想「切能力」也救不了：**一次会话只能挂一套**，开过一轮再换还会被锁。

> 依据 DeepSeek Harness：[《Agent Presets and Personas》](https://deepseekdocs.com/en/docs/features/persona) · [架构说明《A session's agent is composed from a preset》](https://github.com/deepseek-ai/deepseek-harness/blob/master/.agents/notes/implemented/architecture/2026-08-03-per-session-agent-presets.md)

### 解法

不要在一个 dsh 里硬塞。
**每个实例 = 一整套独立的 dsh**（独立进程、独立端口、独立 `DSH_HOME`），不是同一个窗口里的标签页。

左边客服接待、右边写代码、下面跑测试——要几套就开几套，插件互不踩。

![分屏实机](docs/assets/zh-CN/screenshot-main-light.png)

> 隔离干净了，各自为战确实省心。但真实工作从来不是三条互不相交的线——
> 客户那句话终究要传到开发这边。这是第二节要讲的。

---

## 二、协作：分开之后，还要一起把活做完

客服、开发、测试可以各开一套 dsh，但交付物往往是同一份：同一个项目、同一版要发出去的东西。

做法很直接：**三个实例共用同一个项目目录**；插件分开，文件共享。人在分屏里当调度——左边改完一段，右边立刻对着同一份文件改说明，下面按清单验收。

这不是三个互不相干的窗口并排开，是一个窗口里三条流水线磨**同一版**。

目前实例之间不会自动传话，调度还是人来做。

---

## 三、变现：调好几个，就导出几个包

花了好几天，才把客服、开发、测试这三套一起跑顺——插件、预设、话术、谁盯谁，一点点调对。

然后有人要买。真正卡住的不是「会不会用」，而是**每次卖都像再做一遍工程**：

1. **复原不了** — 过几天连自己都说不清哪几个插件、哪份预设才是「这一套」；给客户装，装完对不上，又耗掉几天
2. **交不出去** — 写说明书客户装不全；把目录打包又怕白嫖转卖
3. **卖不了多个** — 第二个、第三个客户还要再远程折腾一遍，**交付时间远大于调功能的时间**，规模化卖不出去

**`.dshpack`：** 把已经调好的那一个实例（一整套 dsh）打成文件。客户导入即用；可绑机器码 / 密码，可禁止再导出——你卖的是成品，不是陪装服务。

调好几个角色，就导出几个包。一份 `.dshpack` 仍是一份 dsh；买家导入后出现在侧栏，分屏自己再拖。

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
