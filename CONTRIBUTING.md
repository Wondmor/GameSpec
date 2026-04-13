# Contributing to GameSpec

Thank you for your interest in contributing to GameSpec! This document provides guidelines and instructions for contributing.

## 🚀 Quick Start

1. Fork the repository
2. Clone your fork: `git clone https://github.com/YOUR_USERNAME/GameSpec.git`
3. Create a branch: `git checkout -b feature/your-feature`
4. Make your changes
5. Test your changes
6. Commit: `git commit -m "Add feature: description"`
7. Push: `git push origin feature/your-feature`
8. Open a Pull Request

## 📋 Development Setup

### Prerequisites

- Node.js 20.19.0 or higher
- pnpm (recommended) or npm

### Installation

```bash
# Clone the repository
git clone https://github.com/Wondmor/GameSpec.git
cd GameSpec

# Install dependencies
pnpm install

# Build the project
pnpm build

# Run tests
pnpm test
```

## 🏗️ Project Structure

```
gamespec/
├── bin/              # CLI entry point
├── src/              # Source code
│   ├── cli/          # CLI commands
│   ├── commands/     # Command implementations
│   ├── core/         # Core logic
│   └── ...
├── docs/             # Documentation
├── test/             # Test files
└── ...
```

## 🎯 Areas for Contribution

### High Priority

- [ ] **Godot Engine Support**: Improve GDScript validation rules
- [ ] **Unity Support**: Add C# validation and project structure
- [ ] **Auto-Validation**: Implement automatic code checking and fixing
- [ ] **Documentation**: Improve user guides and API docs

### Medium Priority

- [ ] **New Engine Presets**: Unreal Engine, Godot 3.x
- [ ] **CI/CD Integration**: GitHub Actions, GitLab CI
- [ ] **IDE Plugins**: VS Code extension
- [ ] **Testing**: Increase test coverage

### Low Priority

- [ ] **Internationalization**: Multi-language support
- [ ] **Analytics**: Usage statistics (opt-in)
- [ ] **Website**: Project website and docs

## 📝 Commit Guidelines

We follow [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>(<scope>): <subject>

<body>

<footer>
```

Types:
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting)
- `refactor`: Code refactoring
- `test`: Test changes
- `chore`: Build process or auxiliary tool changes

Examples:
```
feat(godot): add GDScript validation rules
fix(cli): resolve init command error
docs(readme): update installation guide
```

## 🧪 Testing

```bash
# Run all tests
pnpm test

# Run tests in watch mode
pnpm test:watch

# Run tests with coverage
pnpm test:coverage
```

## 📄 License

By contributing, you agree that your contributions will be licensed under the MIT License.

## 🙏 Thank You

Thank you for contributing to GameSpec! Your efforts help make game development better for everyone.

---

For questions or discussions, please open an issue or join our discussions.
