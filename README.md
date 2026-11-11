# Lumi Softworks

**The Lumi family of software — one plugin-driven kernel, many macOS applications.**

English · [简体中文](./profile/README.zh.md)

This repository hosts the [organization profile](https://github.com/lumi-softworks) for **Lumi Softworks**.

## About

Lumi Softworks is an independent software team focused on **Apple platforms**. We build a family of macOS applications that collaborate with each other while remaining independently runnable, all sharing a single in-house plugin kernel.

Both our flagship **Lumi** (AI desktop assistant) and the lightweight **Wakey** (status bar companion) are built on the same kernel, Provider contracts and design system. This means **a single plugin can ship in multiple applications** — the Eye Care, Hydration and Stretch reminder plugins, for instance, share one implementation across Lumi and Wakey.

## Products

- **[Lumi](https://github.com/lumi-softworks/Lumi)** — An AI-powered macOS desktop assistant combining LLM chat, a tool-using agent, a code editor, a terminal, and a broad set of system and developer utilities.
- **[Wakey](https://github.com/lumi-softworks/Wakey)** — A lightweight macOS status bar assistant for anti-sleep control and Eye Care / Hydration / Stretch reminders.

> More Lumi-family applications are in development and will move into this organization over time.

## Shared Packages

The ecosystem is built on reusable Swift Packages consumed as remote SPM dependencies.

- **Core** — [`LumiKernel`](https://github.com/lumi-softworks/LumiKernel), [`LumiProviders`](https://github.com/lumi-softworks/LumiProviders), [`LumiUI`](https://github.com/lumi-softworks/LumiUI)
- **Kits** — [`LumiKitReminder`](https://github.com/lumi-softworks/LumiKitReminder), [`LumiThemePack`](https://github.com/lumi-softworks/LumiThemePack), [`LumiSettings`](https://github.com/lumi-softworks/LumiSettings), [`LumiLocalization`](https://github.com/lumi-softworks/LumiLocalization), [`LumiLogging`](https://github.com/lumi-softworks/LumiLogging), [`LumiStoreKit`](https://github.com/lumi-softworks/LumiStoreKit), [`LumiIllustrations`](https://github.com/lumi-softworks/LumiIllustrations)
- **Plugins** — the `LumiPlugin*` and `LumiBookletMaker` family, shared across host applications.

## License

Each repository carries its own license: **GPL-3.0** for Lumi, Wakey and LumiKernel; **MIT** for LumiUI, LumiSettings, LumiLogging, LumiStoreKit and LumiIllustrations. Refer to the `LICENSE` file in each repository.

## Links

- Website — <https://coffic.cn>
