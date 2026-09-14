# Fincept Terminal (Open Source Edition)

<div align="center">

[![License: AGPL-3.0](https://img.shields.io/badge/license-AGPL--3.0-C06524)](https://github.com/Fincept-Corporation/FinceptTerminal/blob/main/LICENSE)
[![C++20](https://img.shields.io/badge/C%2B%2B-20-00599C?logo=cplusplus)](https://isocpp.org/)
[![Qt6](https://img.shields.io/badge/Qt-6-41CD52?logo=qt&logoColor=white)](https://www.qt.io/)
[![Python](https://img.shields.io/badge/Python-3.11+-3776AB?logo=python&logoColor=white)](https://www.python.org/)

**A native C++20 / Qt6 desktop terminal for financial research — 100+ data connectors, embedded Python analytics, AI research agents, and paper trading, in a single binary.**

</div>

---

## About this fork

This is [ladariusjackson1](https://github.com/ladariusjackson1)'s fork of the upstream [Fincept-Corporation/FinceptTerminal](https://github.com/Fincept-Corporation/FinceptTerminal) repository — the free, AGPL-3.0 open-source edition of Fincept Terminal.

The upstream project also sells a separate, closed-source **Enterprise** edition with proprietary datasets and live broker execution. That product isn't part of this codebase and never was — the upstream repository already ships only the open-source edition. This fork removes the in-app **Enterprise upsell UI** (the toolbar "UPGRADE" button, the startup promo dialog, and the pricing-screen banner that link out to the paid product), so the terminal only surfaces what actually runs in this build. No functional capability was removed — every connector, screen, and analytics module from upstream is unchanged.

All credit for the underlying application goes to [Fincept Corporation](https://fincept.in). See [LICENSE](LICENSE) for the AGPL-3.0-or-later terms this code is distributed under, and the [upstream README](https://github.com/Fincept-Corporation/FinceptTerminal#readme) for the canonical project description, releases, and support channels.

---

## What's included (free / open-source)

- **Analytics** — DCF, portfolio optimisation, VaR/Sharpe, derivatives pricing, fixed income, alternatives, plus an 18-module QuantLib suite
- **AI** — 37 trader/investor, economic and geopolitics agents; bring your own LLM key (OpenAI, Anthropic, Gemini, Groq, DeepSeek, OpenRouter, Ollama)
- **Data** — 100+ connectors: FRED, IMF, World Bank, DBnomics, AkShare, Polygon, Kraken, Yahoo Finance, government APIs
- **Trading** — crypto and equity feeds, paper-trading engine, 16 broker integrations
- **Automation** — visual node editor, MCP tools, AI Quant Lab (ML, factor discovery, RL)
- **Global intelligence** — maritime tracking, geopolitical analysis, relationship mapping

Native C++20 · Qt6 · embedded Python 3.11 · single binary · no Node.js, no browser runtime.

Cost: free. You bring your own API keys for data sources and your own LLM key for the AI agents — there is no subscription or credit system required to use this build.

---

## Build from source

Pinned toolchain: **CMake 3.27+ · Qt 6.8.3 · Python 3.11.x · C++20 compiler** (Apple Clang 15+ / GCC 12.3+ / MSVC 19.40+).

**Linux / macOS:**
```bash
git clone https://github.com/ladariusjackson1/FinceptTerminal.git
cd FinceptTerminal
./setup.sh
```

`setup.sh` installs the required build tools via your system package manager (or Homebrew on macOS), fetches the exact pinned Qt 6.8.3 build via `aqtinstall` into an isolated `.qt/` folder, configures the project, and compiles it.

**Windows** and manual/advanced builds: see [docs/GETTING_STARTED.md](docs/GETTING_STARTED.md).

Once built, launch:
- macOS: `./fincept-qt/build/macos-release/FinceptTerminal.app/Contents/MacOS/FinceptTerminal`
- Linux: `./fincept-qt/build/linux-release/FinceptTerminal`
- Windows: `.\build\win-release\FinceptTerminal.exe`

Click **"Continue as Guest"** on first launch — no registration required.

---

## Project structure

```
FinceptTerminal/
├── fincept-qt/          Main Qt6/C++20 application
│   ├── src/              C++ source (app, ui, network, storage, auth, trading, screens, ...)
│   ├── scripts/          Embedded Python analytics scripts
│   └── CMakeLists.txt    Build configuration
└── docs/                 Architecture and contributor guides
```

See [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md) and [docs/GETTING_STARTED.md](docs/GETTING_STARTED.md) for a full tour of the codebase.

---

## License

**AGPL-3.0-or-later**, inherited unchanged from upstream — see [LICENSE](LICENSE).

This is strong copyleft: if you distribute a modified build of this code, or run one as a network service others can reach, you must publish your changes under the same license. Personal, non-distributed use carries no obligations.

"Fincept", "Fincept Terminal" and the Fincept logo are trademarks of Fincept Corporation. This fork is an unmodified-functionality, UI-trimmed derivative shared under the terms of the AGPL-3.0 license; it is not affiliated with or endorsed by Fincept Corporation beyond that license grant.
