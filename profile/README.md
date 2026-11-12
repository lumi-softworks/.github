<div align="center">

<img src="./assets/lumi-icon.png" alt="Lumi Softworks" width="96" height="96" />

# Lumi Softworks

**The Lumi family of software — one plugin-driven kernel, many macOS apps**

English · [简体中文](./README.zh.md)

[![Lumi](https://img.shields.io/badge/Lumi-AI%20Desktop%20Assistant-FF9F0A?style=flat-square&logo=swift&logoColor=white)](https://github.com/lumi-softworks/Lumi)
[![Wakey](https://img.shields.io/badge/Wakey-macOS%20Status%20Bar%20Assistant-0A84FF?style=flat-square&logo=swift&logoColor=white)](https://github.com/lumi-softworks/Wakey)
[![Swift](https://img.shields.io/badge/Swift-6.0+-orange.svg)](https://swift.org)
[![macOS](https://img.shields.io/badge/macOS-14.0+-blue.svg)](https://developer.apple.com/macos/)

</div>

---

## About Us

Lumi Softworks is an independent software team focused on **Apple platforms**. Around a self-built plugin kernel, we craft a family of macOS applications that collaborate with each other while remaining independently runnable.

Both our flagship **Lumi** (AI desktop assistant) and the lightweight **Wakey** (status bar companion) are built on the same kernel, Provider contracts and design system. This means **a single plugin can ship in multiple applications** — the Eye Care, Hydration and Stretch reminder plugins, for instance, share one implementation across Lumi and Wakey.

## Our Products

- 🧠 **[Lumi](https://github.com/lumi-softworks/Lumi)** — An AI-powered macOS desktop assistant: LLM chat, an agent with tool use, a code editor, a terminal, and a broad set of developer and system tools in one app.
- ⚡ **[Wakey](https://github.com/lumi-softworks/Wakey)** — A lightweight macOS status bar assistant with one-tap anti-sleep and timed Eye Care, Hydration and Stretch reminders.

> **In the pipeline** — more Lumi-family applications are in development and will move into this organization over time.

## Architecture Principles

```
        ┌──────────────┐   ┌──────────────┐
        │     Lumi     │   │    Wakey     │   ... more apps
        └──────┬───────┘   └──────┬───────┘
               │                  │
        ┌──────▼──────────────────▼───────┐
        │        LumiKernel kernel        │  Provider registry · plugin lifecycle
        └──────▲──────────────────▲───────┘
               │                  │
    ┌──────────┴───┐      ┌───────┴────────┐
    │ LumiProviders│      │    LumiUI      │  contracts · design system
    └──────────────┘      └────────────────┘
               ▲
    ┌──────────┴───────────────────────────┐
    │   shared plugins / kits (remote SPM)  │
    │  eye care · hydration · stretch · ... │
    └──────────────────────────────────────┘
```

- **Contracts first** — plugins never depend on concrete implementations; they talk to the host through `Provider*` contracts
- **One plugin, one package** — each plugin is a standalone Swift Package, independently versioned, published and consumed by multiple apps
- **A tiny kernel** — the kernel only handles registration, resolution and lifecycle; it knows nothing about any specific domain

## Contributing

Issues and pull requests are welcome.

- **Report a bug or propose a feature** → open an issue in the corresponding repository
- **Contribute code** → read the repository's `README` and `AGENTS.md` conventions first
- **Add a shared plugin** → follow the [plugin package structure guide](https://github.com/lumi-softworks/.github) to keep package layouts consistent

## Links

- 🏠 Website — <https://coffic.cn>
- 🐦 Contact — <https://github.com/nookery>

---

<div align="center">
  <sub>Built with Swift and ❤️ by <a href="https://github.com/lumi-softworks">Lumi Softworks</a></sub>
</div>
