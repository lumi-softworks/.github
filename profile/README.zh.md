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

## 我们的产品

- 🧠 **[Lumi](https://github.com/lumi-softworks/Lumi)** —— AI 驱动的 macOS 桌面助手：LLM 对话、可调用工具的 Agent、代码编辑器、终端，以及丰富的开发与系统工具，集于一身。
- ⚡ **[Wakey](https://github.com/lumi-softworks/Wakey)** —— 轻量级 macOS 状态栏助理：一键防休眠，定时提醒护眼、喝水、拉伸。

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

## 链接

- 🏠 官方网站 —— <https://coffic.cn>
- 🐦 联系方式 —— <https://github.com/nookery>

---

<div align="center">
  <sub>由 <a href="https://github.com/lumi-softworks">Lumi Softworks</a> 用 Swift 与 ❤️ 构建</sub>
</div>
