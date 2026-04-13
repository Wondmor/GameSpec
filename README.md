<p align="center">
  <a href="https://github.com/Wondmor/GameSpec">
    <picture>
      <source srcset="assets/gamespec_logo.png">
      <img src="assets/gamespec_logo.png" alt="GameSpec logo" width="200">
    </picture>
  </a>
</p>

<h1 align="center">GameSpec</h1>

<p align="center">
  <strong>Spec-driven development for AI-assisted game development</strong>
</p>

<p align="center">
  <a href="https://github.com/Wondmor/GameSpec/actions/workflows/ci.yml"><img alt="CI" src="https://github.com/Wondmor/GameSpec/actions/workflows/ci.yml/badge.svg" /></a>
  <a href="./LICENSE"><img alt="License: MIT" src="https://img.shields.io/badge/License-MIT-blue.svg?style=flat-square" /></a>
</p>

## 🎮 What is GameSpec?

GameSpec is a **spec-driven development (SDD)** framework specifically designed for **AI-assisted game development**. It is based on [OpenSpec](https://github.com/Fission-AI/OpenSpec) and extends it with game development-specific features.

### Key Features

- 📝 **Spec-driven workflow** - Define what you want to build before coding
- 🤖 **AI-native** - Designed to work with Claude Code, Cursor, GitHub Copilot, and more
- 🎮 **Game engine presets** - Built-in support for Godot, Unity, Unreal Engine
- ✅ **Auto-validation** - Automatic code validation and error fixing
- 🔧 **Engine-specific best practices** - Built-in rules for GDScript, C#, C++

## 🚀 Quick Start

**Requires Node.js 20.19.0 or higher.**

Install GameSpec globally:

```bash
npm install -g gamespec
```

Then navigate to your game project directory and initialize:

```bash
cd your-game-project
gamespec init
```

Select your game engine (Godot/Unity/Unreal) and AI tool (Claude Code/Cursor/etc.).

### Start Your First Change

```bash
# Create a new change proposal
gamespec new "add player movement system"

# Or use slash commands in your AI tool
/gamespec:new "add player movement system"
```

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────┐
│                      GameSpec CLI                        │
├─────────────────────────────────────────────────────────┤
│  Init  │  New  │  Apply  │  Verify  │  Archive          │
├─────────────────────────────────────────────────────────┤
│              Engine Presets (Godot/Unity/Unreal)         │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐               │
│  │ GDScript │  │    C#    │  │   C++    │               │
│  │  Rules   │  │  Rules   │  │  Rules   │               │
│  └──────────┘  └──────────┘  └──────────┘               │
├─────────────────────────────────────────────────────────┤
│              Auto-Validation System                      │
│  ┌─────────┐  ┌─────────┐  ┌─────────┐                  │
│  │  gdlint │  │ godot   │  │ AI Fix  │                  │
│  │  check  │  │ --check │  │  Loop   │                  │
│  └─────────┘  └─────────┘  └─────────┘                  │
└─────────────────────────────────────────────────────────┘
```

## 🛠️ Supported Game Engines

| Engine | Status | Language | Validation |
|--------|--------|----------|------------|
| **Godot 4.x** | ✅ Ready | GDScript | gdlint + godot --check-only |
| **Unity** | 🚧 Planned | C# | dotnet build |
| **Unreal Engine** | 🚧 Planned | C++ | clang-tidy |

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guide](CONTRIBUTING.md) for details.

### Development Setup

```bash
# Clone the repository
git clone https://github.com/Wondmor/GameSpec.git
cd GameSpec

# Install dependencies
pnpm install

# Build
pnpm build

# Run tests
pnpm test
```

## 📚 Documentation

- [Getting Started Guide](docs/getting-started.md)
- [Engine Presets](docs/engine-presets.md)
- [Auto-Validation](docs/auto-validation.md)
- [API Reference](docs/api.md)

## 🙏 Acknowledgments

GameSpec is based on [OpenSpec](https://github.com/Fission-AI/OpenSpec) by Fission-AI. We are grateful for their excellent work on spec-driven development.

## 📄 License

MIT License - see [LICENSE](LICENSE) file for details.

Copyright (c) 2026 GameSpec Contributors

---

<p align="center">
  Made with ❤️ for game developers
</p>
