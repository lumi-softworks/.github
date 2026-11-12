<div align="center">

<img src="./assets/lumi-icon.png" alt="Lumi Softworks" width="96" height="96" />

# Lumi Softworks

**Lumi 家族软件 —— 一套插件化内核，多款 macOS 应用**

[English](./README.md) · 简体中文

[![Lumi](https://img.shields.io/badge/Lumi-AI%20Desktop%20Assistant-FF9F0A?style=flat-square&logo=swift&logoColor=white)](https://github.com/lumi-softworks/Lumi)
[![Wakey](https://img.shields.io/badge/Wakey-macOS%20Status%20Bar%20Assistant-0A84FF?style=flat-square&logo=swift&logoColor=white)](https://github.com/lumi-softworks/Wakey)
[![Swift](https://img.shields.io/badge/Swift-6.0+-orange.svg)](https://swift.org)
[![macOS](https://img.shields.io/badge/macOS-14.0+-blue.svg)](https://developer.apple.com/macos/)

</div>

---

## 关于我们

Lumi Softworks 是一支专注于 **Apple 平台** 的独立软件团队。我们围绕一套自研的插件化内核，构建了一系列彼此协作、却又可独立运行的 macOS 应用。

无论是旗舰产品 **Lumi**（AI 桌面助手），还是轻量级的 **Wakey**（状态栏助理），都建立在同一套内核、Provider 契约与设计系统之上。这意味着**同一个插件可以同时出现在多个应用中** —— 例如护眼、喝水、拉伸三个提醒插件，在 Lumi 与 Wakey 中共享同一份实现。

<div align="center">
  <img src="./assets/lumi-hero.webp" alt="Lumi" width="88%" />
</div>

## 我们的产品

### 🧠 [Lumi](https://github.com/lumi-softworks/Lumi)

**AI 驱动的 macOS 桌面助手** —— 一个应用里装下 LLM 对话、可调用工具的 Agent、代码编辑器、终端，以及大量系统与开发者工具。

- **多模型对话** —— 内置 20+ 家 LLM 服务商接入（OpenAI、Anthropic、DeepSeek、智谱、MiniMax、Kimi Code、阿里云、StepFun、小米、OpenRouter，以及本地 MLX 模型）
- **Agent 工具调用** —— 读写文件、执行 Shell、联网搜索、浏览器与电脑控制、图像理解，并能在任务中主动向用户提问
- **内置代码编辑器** —— 项目文件树、语法高亮、模糊搜索、大纲、引用跳转、调用层级、问题面板、语言服务与 Markdown 预览
- **开发者工具** —— 原生终端、Git/GitHub 集成、SQLite/MySQL/PostgreSQL/Redis、Docker、Homebrew、端口与 hosts 管理
- **系统工具** —— 剪贴板历史、磁盘与网络监控、屏幕录制、OCR、显示器控制、防休眠、下载管理等
- **项目智能** —— 项目级规则、技能、记忆、文件检索，以及基于本地向量库的代码检索
- **主题与扩展** —— 100+ 默认插件、运行时开关、22 套内置主题
- **本地 HTTP API** —— 内置 Web 服务监听回环地址，聚合各插件注册的路由

<div align="center">
  <img src="./assets/wakey-hero.webp" alt="Wakey" width="88%" />
</div>

### ⚡ [Wakey](https://github.com/lumi-softworks/Wakey)

**轻量级 macOS 状态栏助理** —— 常驻菜单栏，一键防休眠，定时提醒你护眼、喝水、拉伸。

- **防休眠控制** —— 一键阻止系统休眠，支持多种模式与时长预设
- **休息提醒** —— 护眼 / 喝水 / 拉伸三类提醒，间隔可自定义，休息时在每块屏幕展示全屏遮罩
- **状态栏常驻** —— 无需切换窗口即可访问全部功能
- **插件化架构** —— 与 Lumi 共用同一套内核与共享插件包
- **低占用** —— 安静运行，几乎不打扰工作流

> **规划中** —— 更多 Lumi 家族应用正在开发中，将陆续迁入本组织。

## 架构理念

```
        ┌──────────────┐   ┌──────────────┐
        │     Lumi     │   │    Wakey     │   ... 更多应用
        └──────┬───────┘   └──────┬───────┘
               │                  │
        ┌──────▼──────────────────▼───────┐
        │        LumiKernel 内核          │  Provider 注册 · 插件生命周期
        └──────▲──────────────────▲───────┘
               │                  │
    ┌──────────┴───┐      ┌───────┴────────┐
    │ LumiProviders│      │   LumiUI       │  契约 · 设计系统
    └──────────────┘      └────────────────┘
               ▲
    ┌──────────┴───────────────────────────┐
    │      共享插件 / 套件（远程 SPM 包）    │
    │  护眼 · 喝水 · 拉伸 · 存储 · 主题 ...  │
    └──────────────────────────────────────┘
```

- **契约先行** —— 插件不直接依赖具体实现，而是通过 `Provider*` 契约与宿主交互
- **插件即包** —— 一个插件一个 Swift Package，可独立版本化、独立发布、独立被多个应用引用
- **内核极小** —— 内核只负责注册、解析与生命周期，不认识任何具体业务

## 参与共建

我们欢迎 Issues 与 Pull Requests。

- 报告问题、提出功能建议 → 请前往对应仓库的 Issues
- 贡献代码 → 请先阅读对应仓库的 `README` 与 `AGENTS.md` 约定
- 新增共享插件 → 请遵循[插件包目录结构规范](https://github.com/lumi-softworks/.github)，保持包目录结构一致

## 许可证

本组织下各仓库采用各自的开源许可证：

| 仓库 | 许可证 |
| :--- | :--- |
| [`Lumi`](https://github.com/lumi-softworks/Lumi) | GPL-3.0 |
| [`Wakey`](https://github.com/lumi-softworks/Wakey) | GPL-3.0 |
| [`LumiKernel`](https://github.com/lumi-softworks/LumiKernel) | GPL-3.0 |
| [`LumiUI`](https://github.com/lumi-softworks/LumiUI) | MIT |
| [`LumiSettings`](https://github.com/lumi-softworks/LumiSettings) | MIT |
| [`LumiLogging`](https://github.com/lumi-softworks/LumiLogging) | MIT |
| [`LumiStoreKit`](https://github.com/lumi-softworks/LumiStoreKit) | MIT |
| [`LumiIllustrations`](https://github.com/lumi-softworks/LumiIllustrations) | MIT |
| 其余共享包 | 以各仓库内的 `LICENSE` 文件为准 |

> 部分共享包尚未附带 `LICENSE` 文件，迁移后将统一补齐。

## 链接

- 🏠 官方网站 —— <https://coffic.cn>
- 🐦 联系方式 —— <https://github.com/nookery>

---

<div align="center">
  <sub>由 <a href="https://github.com/lumi-softworks">Lumi Softworks</a> 用 Swift 与 ❤️ 构建</sub>
</div>
