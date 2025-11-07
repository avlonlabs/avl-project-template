# PyX Repository Structure - Industry Standard

**Repository:** https://github.com/avlonlabs/pyx  
**License:** Apache 2.0 ✅  
**Vision:** Top-tier open source project structure

---

## 📁 Complete Directory Structure

```
pyx/
├── .github/                          # GitHub specific files
│   ├── workflows/                    # CI/CD pipelines
│   │   ├── ci.yml                   # Main CI (tests, lint, build)
│   │   ├── release.yml              # Release automation
│   │   ├── docs.yml                 # Documentation deployment
│   │   └── security.yml             # Security scanning
│   ├── ISSUE_TEMPLATE/              # Issue templates
│   │   ├── bug_report.md
│   │   ├── feature_request.md
│   │   └── question.md
│   ├── PULL_REQUEST_TEMPLATE.md     # PR template
│   ├── CODEOWNERS                   # Code ownership
│   ├── FUNDING.yml                  # Sponsorship info
│   └── dependabot.yml               # Dependency updates
│
├── crates/                          # Rust workspace (monorepo style)
│   ├── pyx-engine/                  # Core Rust engine
│   │   ├── src/
│   │   │   ├── main.rs             # CLI entry point
│   │   │   ├── lib.rs              # Library exports
│   │   │   ├── server/             # HTTP server module
│   │   │   │   ├── mod.rs
│   │   │   │   ├── router.rs
│   │   │   │   └── middleware.rs
│   │   │   ├── python/             # Python bridge
│   │   │   │   ├── mod.rs
│   │   │   │   ├── runtime.rs
│   │   │   │   └── bridge.rs
│   │   │   ├── bundler/            # TypeScript bundling
│   │   │   │   ├── mod.rs
│   │   │   │   ├── swc.rs
│   │   │   │   └── resolver.rs
│   │   │   ├── watcher/            # Hot reload
│   │   │   │   ├── mod.rs
│   │   │   │   └── events.rs
│   │   │   └── cli/                # CLI commands
│   │   │       ├── mod.rs
│   │   │       ├── init.rs
│   │   │       ├── dev.rs
│   │   │       └── build.rs
│   │   ├── tests/                  # Integration tests
│   │   │   ├── test_router.rs
│   │   │   ├── test_python_bridge.rs
│   │   │   └── test_hot_reload.rs
│   │   ├── benches/                # Benchmarks
│   │   │   └── router_bench.rs
│   │   ├── Cargo.toml
│   │   └── README.md
│   │
│   ├── pyx-core/                    # Shared Rust types/utilities
│   │   ├── src/
│   │   │   ├── lib.rs
│   │   │   ├── config.rs
│   │   │   ├── error.rs
│   │   │   └── types.rs
│   │   ├── Cargo.toml
│   │   └── README.md
│   │
│   └── pyx-macros/                  # Rust macros (if needed)
│       ├── src/
│       │   └── lib.rs
│       └── Cargo.toml
│
├── python/                          # Python framework
│   ├── pyx/                         # Main package
│   │   ├── __init__.py
│   │   ├── route.py                # @AIRoute decorator
│   │   ├── ai/                     # AI module
│   │   │   ├── __init__.py
│   │   │   ├── model.py           # use_model()
│   │   │   ├── providers/
│   │   │   │   ├── __init__.py
│   │   │   │   ├── openai.py
│   │   │   │   ├── anthropic.py
│   │   │   │   └── base.py
│   │   │   └── streaming.py
│   │   ├── memory/                 # Memory module
│   │   │   ├── __init__.py
│   │   │   ├── manager.py         # auto_memory()
│   │   │   ├── backends/
│   │   │   │   ├── __init__.py
│   │   │   │   ├── inmemory.py
│   │   │   │   └── redis.py       # v1.1
│   │   │   └── types.py
│   │   ├── middleware/             # Middleware
│   │   │   ├── __init__.py
│   │   │   ├── cors.rs
│   │   │   └── rate_limit.py      # v1.1
│   │   ├── testing/                # Test utilities
│   │   │   ├── __init__.py
│   │   │   ├── client.py
│   │   │   └── mocks.py
│   │   ├── types.py                # Type definitions
│   │   ├── config.py               # Configuration
│   │   ├── exceptions.py           # Custom exceptions
│   │   └── py.typed                # PEP 561 marker
│   │
│   ├── tests/                      # Python tests
│   │   ├── unit/
│   │   │   ├── test_route.py
│   │   │   ├── test_ai.py
│   │   │   └── test_memory.py
│   │   ├── integration/
│   │   │   ├── test_streaming.py
│   │   │   └── test_context.py
│   │   └── conftest.py            # Pytest fixtures
│   │
│   ├── pyproject.toml              # Python project config
│   ├── setup.py                    # Setup script
│   ├── README.md
│   └── CHANGELOG.md
│
├── typescript/                      # TypeScript/React package
│   ├── packages/
│   │   ├── pyx-ui/                 # React components
│   │   │   ├── src/
│   │   │   │   ├── index.ts
│   │   │   │   ├── components/
│   │   │   │   │   ├── ChatBox.tsx
│   │   │   │   │   ├── MessageList.tsx
│   │   │   │   │   ├── MessageInput.tsx
│   │   │   │   │   └── index.ts
│   │   │   │   ├── hooks/
│   │   │   │   │   ├── useChat.ts
│   │   │   │   │   ├── useStream.ts
│   │   │   │   │   └── index.ts
│   │   │   │   ├── types/
│   │   │   │   │   └── index.ts
│   │   │   │   └── styles/
│   │   │   │       └── index.css
│   │   │   ├── package.json
│   │   │   ├── tsconfig.json
│   │   │   └── README.md
│   │   │
│   │   └── pyx-types/              # Shared TypeScript types
│   │       ├── src/
│   │       │   └── index.ts
│   │       ├── package.json
│   │       └── tsconfig.json
│   │
│   ├── pnpm-workspace.yaml         # Monorepo config
│   └── package.json                # Root package.json
│
├── cli/                            # CLI resources
│   ├── templates/                  # Project templates
│   │   ├── default/
│   │   │   ├── app/
│   │   │   │   └── page.tsx
│   │   │   ├── pyx.config.ts
│   │   │   ├── package.json
│   │   │   ├── requirements.txt
│   │   │   └── README.md
│   │   ├── chatbot/
│   │   │   ├── app/
│   │   │   │   ├── page.tsx
│   │   │   │   └── api/
│   │   │   │       └── chat/
│   │   │   │           └── route.py
│   │   │   ├── pyx.config.ts
│   │   │   └── README.md
│   │   ├── rag/
│   │   └── agent/
│   │
│   └── assets/                     # CLI assets (logos, etc.)
│
├── docs/                           # Documentation
│   ├── src/
│   │   ├── index.md               # Home page
│   │   ├── getting-started/
│   │   │   ├── installation.md
│   │   │   ├── quick-start.md
│   │   │   └── first-app.md
│   │   ├── guides/
│   │   │   ├── routing.md
│   │   │   ├── ai-integration.md
│   │   │   ├── memory-management.md
│   │   │   └── deployment.md
│   │   ├── api/
│   │   │   ├── python/
│   │   │   │   ├── route.md
│   │   │   │   ├── ai.md
│   │   │   │   └── memory.md
│   │   │   ├── typescript/
│   │   │   │   └── components.md
│   │   │   └── rust/
│   │   │       └── engine.md
│   │   ├── examples/
│   │   │   ├── chatbot.md
│   │   │   ├── rag-system.md
│   │   │   └── agent.md
│   │   └── architecture/
│   │       ├── overview.md
│   │       ├── rust-engine.md
│   │       ├── python-framework.md
│   │       └── typescript-ui.md
│   │
│   ├── .vitepress/                # VitePress config (or Docusaurus)
│   │   └── config.ts
│   ├── package.json
│   └── README.md
│
├── examples/                       # Example applications
│   ├── chatbot/                   # Basic chatbot
│   │   ├── app/
│   │   ├── pyx.config.ts
│   │   └── README.md
│   ├── rag-system/                # RAG implementation
│   ├── code-assistant/            # Code generation
│   ├── agent-demo/                # AI agent
│   └── README.md
│
├── benchmarks/                     # Performance benchmarks
│   ├── routing/
│   │   └── bench_file_router.rs
│   ├── streaming/
│   │   └── bench_llm_stream.py
│   └── README.md
│
├── scripts/                        # Development scripts
│   ├── setup.sh                   # Initial setup
│   ├── test.sh                    # Run all tests
│   ├── build.sh                   # Build everything
│   ├── release.sh                 # Create release
│   └── benchmark.sh               # Run benchmarks
│
├── website/                        # Marketing website (separate from docs)
│   ├── public/
│   ├── src/
│   │   ├── pages/
│   │   ├── components/
│   │   └── styles/
│   ├── package.json
│   └── README.md
│
├── tests/                          # End-to-end tests
│   ├── e2e/
│   │   ├── test_full_flow.spec.ts
│   │   └── playwright.config.ts
│   └── fixtures/
│
├── .devcontainer/                  # VS Code dev container
│   ├── devcontainer.json
│   └── Dockerfile
│
├── .vscode/                        # VS Code settings
│   ├── settings.json
│   ├── extensions.json
│   ├── launch.json
│   └── tasks.json
│
├── docker/                         # Docker configs
│   ├── Dockerfile                 # Production
│   ├── Dockerfile.dev             # Development
│   └── docker-compose.yml
│
├── .gitignore                      # Git ignore
├── .editorconfig                   # Editor config
├── .prettierrc                     # Prettier config
├── Cargo.toml                      # Rust workspace config
├── rust-toolchain.toml             # Rust version pinning
├── LICENSE                         # Apache 2.0 ✅
├── MANIFESTO.md                    # Vision & philosophy ✅
├── README.md                       # Main README
├── CONTRIBUTING.md                 # Contribution guide
├── CODE_OF_CONDUCT.md              # Code of conduct
├── SECURITY.md                     # Security policy
├── CHANGELOG.md                    # Version history
└── ARCHITECTURE.md                 # Technical architecture doc
```

---

## 📄 Essential Files to Create

### 1. Root README.md

```markdown
<div align="center">
  <h1>PyX</h1>
  <p><strong>The Next.js of AI Development</strong></p>
  <p>Full-stack framework for building AI-powered web applications</p>
  
  <p>
    <a href="https://github.com/avlonlabs/pyx/actions"><img src="https://github.com/avlonlabs/pyx/workflows/CI/badge.svg" alt="CI Status"></a>
    <a href="https://github.com/avlonlabs/pyx/releases"><img src="https://img.shields.io/github/v/release/avlonlabs/pyx" alt="Version"></a>
    <a href="https://github.com/avlonlabs/pyx/blob/main/LICENSE"><img src="https://img.shields.io/badge/license-Apache%202.0-blue.svg" alt="License"></a>
    <a href="https://discord.gg/pyx"><img src="https://img.shields.io/discord/XXXXX" alt="Discord"></a>
  </p>

  <p>
    <a href="https://pyx.dev">Website</a> •
    <a href="https://pyx.dev/docs">Documentation</a> •
    <a href="#quick-start">Quick Start</a> •
    <a href="#examples">Examples</a> •
    <a href="CONTRIBUTING.md">Contributing</a>
  </p>
</div>

---

## ✨ Features

- 🚀 **Blazing Fast** - Rust-powered engine, 100K+ req/sec
- 🐍 **Python for AI** - Use the entire Python AI/ML ecosystem
- ⚛️ **React for UI** - Modern, familiar frontend development
- 📁 **File-based Routing** - Next.js-style routing for both frontend and backend
- 🔄 **Streaming Built-in** - Native support for LLM streaming responses
- 🧠 **Memory Management** - Automatic conversation context handling
- 🔥 **Hot Reload** - Instant feedback on Python and TypeScript changes
- 🎯 **Zero Config** - Works out of the box, configure when you need to

## 🎯 Why PyX?

**Building AI applications today:**
- ❌ Separate FastAPI backend + React frontend
- ❌ Manual streaming implementation
- ❌ Complex deployment setup
- ❌ No built-in memory management
- ❌ Slow development iteration

**Building with PyX:**
- ✅ One unified framework
- ✅ Streaming by default
- ✅ One command to run: `pyx dev`
- ✅ Automatic memory handling
- ✅ Instant hot reload

## 🚀 Quick Start

### Installation

```bash
# Install PyX CLI
curl -fsSL https://pyx.dev/install.sh | sh

# Or with pip
pip install pyx-cli
```

### Create Your First AI App

```bash
# Create new project
pyx init my-ai-app --template chatbot

# Start development server
cd my-ai-app
pyx dev
```

### Write Your AI Route

```python
# app/api/chat/route.py
from pyx import AIRoute
from pyx.ai import use_model
from pyx.memory import auto_memory

@AIRoute.stream
async def POST(request):
    memory = auto_memory(request.session_id)
    model = use_model("gpt-4")
    
    async for chunk in model.stream(request.message, context=memory.get()):
        yield chunk
```

### Build Your UI

```typescript
// app/page.tsx
import { ChatBox } from '@pyx/ui'

export default function Home() {
  return <ChatBox endpoint="/api/chat" />
}
```

**That's it! You have a production-ready AI chatbot with memory.** 🎉

## 📚 Examples

- [Chatbot with Memory](./examples/chatbot) - Basic conversational AI
- [RAG System](./examples/rag-system) - Retrieval-augmented generation
- [Code Assistant](./examples/code-assistant) - AI code helper
- [Agent Demo](./examples/agent-demo) - Multi-step AI agent

## 🏗️ Architecture

```
┌─────────────────────────────────────────┐
│  Developer writes:                      │
│  - app/page.tsx (React)                 │
│  - app/api/chat/route.py (Python AI)    │
└─────────────────────────────────────────┘
              ↓
┌─────────────────────────────────────────┐
│  PyX Engine (Rust)                      │
│  - HTTP Server (Axum)                   │
│  - File Router                          │
│  - Python Bridge (PyO3)                 │
│  - TS Bundler (SWC)                     │
│  - Hot Reload                           │
└─────────────────────────────────────────┘
              ↓
┌─────────────────────────────────────────┐
│  External Services                      │
│  - OpenAI, Anthropic, etc.              │
│  - Vector DBs (optional)                │
│  - Redis (optional)                     │
└─────────────────────────────────────────┘
```

Read the full [Architecture Document](./ARCHITECTURE.md).

## 🤝 Contributing

We love contributions! Read our [Contributing Guide](./CONTRIBUTING.md) to get started.

- [Code of Conduct](./CODE_OF_CONDUCT.md)
- [Development Setup](./docs/src/guides/development.md)
- [Architecture Overview](./ARCHITECTURE.md)

## 📖 Documentation

- [Getting Started](https://pyx.dev/docs/getting-started)
- [API Reference](https://pyx.dev/docs/api)
- [Examples](https://pyx.dev/docs/examples)
- [Guides](https://pyx.dev/docs/guides)

## 🗺️ Roadmap

- [x] v1.0 - MVP (Dec 2025)
  - [x] File-based routing
  - [x] Streaming AI responses
  - [x] Memory management
  - [x] Hot reload
- [ ] v1.1 - Enhanced (Jan 2026)
  - [ ] Redis backend
  - [ ] Vector DB integration
  - [ ] Docker deployment
- [ ] v1.2 - Production (Feb 2026)
  - [ ] RAG pipeline
  - [ ] Agent framework
  - [ ] Monitoring
- [ ] v2.0 - Advanced (2026 H2)
  - [ ] SSR/SSG
  - [ ] Edge runtime

See [full roadmap](https://github.com/avlonlabs/pyx/issues).

## 📊 Status

| Component | Status | Coverage |
|-----------|--------|----------|
| Rust Engine | 🚧 In Development | - |
| Python Framework | 🚧 In Development | - |
| TypeScript UI | 🚧 In Development | - |
| Documentation | 📝 In Progress | - |

## 💬 Community

- [Discord](https://discord.gg/pyx) - Chat with the community
- [GitHub Discussions](https://github.com/avlonlabs/pyx/discussions) - Ask questions
- [Twitter](https://twitter.com/pyx_framework) - Follow updates
- [Blog](https://pyx.dev/blog) - Read articles

## 📝 License

Apache 2.0 - See [LICENSE](./LICENSE) for details.

## 🙏 Acknowledgments

PyX stands on the shoulders of giants:
- [Next.js](https://nextjs.org) - Inspiration for developer experience
- [Rust](https://rust-lang.org) - Performance foundation
- [FastAPI](https://fastapi.tiangolo.com) - Python patterns
- [React](https://react.dev) - UI library

---

<div align="center">
  <p>Made with ❤️ by <a href="https://avlonlabs.com">Avlon Labs</a></p>
  <p><strong>Star ⭐ this repo if you find it useful!</strong></p>
</div>
```

---

### 2. CONTRIBUTING.md

```markdown
# Contributing to PyX

First off, thank you for considering contributing to PyX! 🎉

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Development Setup](#development-setup)
- [Project Structure](#project-structure)
- [Coding Guidelines](#coding-guidelines)
- [Commit Messages](#commit-messages)
- [Pull Request Process](#pull-request-process)

## 📜 Code of Conduct

This project adheres to a [Code of Conduct](./CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code.

## 🤝 How Can I Contribute?

### Reporting Bugs

Use the [Bug Report template](.github/ISSUE_TEMPLATE/bug_report.md):
- Use a clear, descriptive title
- Describe the exact steps to reproduce
- Include system information (OS, versions, etc.)
- Provide code samples if applicable

### Suggesting Features

Use the [Feature Request template](.github/ISSUE_TEMPLATE/feature_request.md):
- Explain why this feature would be useful
- Provide examples of how it would work
- Consider implementation complexity

### Code Contributions

1. **Find an issue** - Look for issues tagged `good first issue` or `help wanted`
2. **Discuss first** - Comment on the issue to claim it
3. **Fork & branch** - Create a feature branch
4. **Code** - Follow our coding guidelines
5. **Test** - Add tests for your changes
6. **Document** - Update relevant documentation
7. **Submit PR** - Follow our PR template

## 🛠️ Development Setup

### Prerequisites

- Rust 1.75+
- Python 3.11+
- Node.js 20+
- pnpm 8+

### Setup Instructions

```bash
# Clone the repository
git clone https://github.com/avlonlabs/pyx.git
cd pyx

# Run setup script
./scripts/setup.sh

# Or manual setup:

# 1. Install Rust dependencies
cargo build

# 2. Install Python dependencies
cd python
pip install -e ".[dev]"
cd ..

# 3. Install TypeScript dependencies
cd typescript
pnpm install
cd ..

# 4. Run tests
./scripts/test.sh
```

### Running Tests

```bash
# All tests
./scripts/test.sh

# Rust only
cargo test --workspace

# Python only
cd python && pytest

# TypeScript only
cd typescript && pnpm test

# E2E tests
cd tests/e2e && pnpm test
```

### Running Locally

```bash
# Build the CLI
cargo build --release

# Run with a test project
./target/release/pyx init test-app
cd test-app
../target/release/pyx dev
```

## 📁 Project Structure

```
pyx/
├── crates/          # Rust code
│   ├── pyx-engine/  # Main engine
│   └── pyx-core/    # Shared utilities
├── python/          # Python framework
├── typescript/      # TypeScript packages
├── docs/            # Documentation
├── examples/        # Example apps
└── tests/           # E2E tests
```

See [ARCHITECTURE.md](./ARCHITECTURE.md) for detailed documentation.

## 📝 Coding Guidelines

### Rust

- Follow [Rust API Guidelines](https://rust-lang.github.io/api-guidelines/)
- Run `cargo fmt` before committing
- Run `cargo clippy` and fix warnings
- Add doc comments for public APIs
- Keep functions small and focused

```rust
/// Loads a Python route from a file path.
///
/// # Arguments
///
/// * `path` - Path to the Python file
///
/// # Returns
///
/// Returns the loaded route handler
///
/// # Errors
///
/// Returns error if file doesn't exist or Python code is invalid
pub fn load_route(path: &Path) -> Result<RouteHandler> {
    // Implementation
}
```

### Python

- Follow [PEP 8](https://peps.python.org/pep-0008/)
- Use type hints (PEP 484)
- Run `ruff format` before committing
- Run `ruff check` and fix issues
- Add docstrings for public APIs

```python
def use_model(model_name: str) -> ModelProvider:
    """
    Create a model provider for the specified model.
    
    Args:
        model_name: Name of the model (e.g., "gpt-4", "claude-3")
    
    Returns:
        ModelProvider instance
    
    Raises:
        ValueError: If model_name is not supported
    
    Example:
        >>> model = use_model("gpt-4")
        >>> async for chunk in model.stream("Hello"):
        ...     print(chunk)
    """
    # Implementation
```

### TypeScript

- Follow [TypeScript guidelines](https://typescript-lang.org/docs/handbook/declaration-files/do-s-and-don-ts.html)
- Run `prettier --write .` before committing
- Add JSDoc comments for exports
- Use strict mode

```typescript
/**
 * Custom hook for chat functionality
 * 
 * @param endpoint - API endpoint for chat
 * @returns Object with messages, sendMessage function, and streaming state
 * 
 * @example
 * ```tsx
 * const { messages, sendMessage } = useChat('/api/chat')
 * ```
 */
export function useChat(endpoint: string) {
  // Implementation
}
```

## 💬 Commit Messages

Follow [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>(<scope>): <subject>

<body>

<footer>
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style (formatting, etc.)
- `refactor`: Code refactoring
- `perf`: Performance improvements
- `test`: Adding tests
- `chore`: Build process, dependencies

**Examples:**

```
feat(engine): add hot reload support for Python files

Implements file watching using the notify crate. When Python files
change, the engine reloads only the affected module without restarting
the entire server.

Closes #123
```

```
fix(python): handle empty messages in AIRoute

Previously, empty messages would cause a panic. Now returns 400 Bad
Request with clear error message.

Fixes #456
```

## 🔄 Pull Request Process

1. **Update documentation** - If you change APIs, update docs
2. **Add tests** - Cover your changes with tests
3. **Update CHANGELOG.md** - Add entry under "Unreleased"
4. **Run tests locally** - Ensure all tests pass
5. **Create PR** - Fill out the PR template completely
6. **Respond to reviews** - Address feedback promptly
7. **Squash commits** - Clean up commit history before merge

### PR Checklist

- [ ] Tests added/updated
- [ ] Documentation updated
- [ ] CHANGELOG.md updated
- [ ] All tests passing
- [ ] No merge conflicts
- [ ] Follows coding guidelines
- [ ] Commit messages follow conventions

## 🎓 Learning Resources

- [Rust Book](https://doc.rust-lang.org/book/)
- [PyO3 Guide](https://pyo3.rs/)
- [FastAPI Tutorial](https://fastapi.tiangolo.com/tutorial/)
- [React Docs](https://react.dev/)

## ❓ Questions?

- [GitHub Discussions](https://github.com/avlonlabs/pyx/discussions)
- [Discord](https://discord.gg/pyx)
- [Twitter](https://twitter.com/pyx_framework)

---

Thank you for contributing to PyX! 🚀
```

---

### 3. CODE_OF_CONDUCT.md

Use the standard [Contributor Covenant](https://www.contributor-covenant.org/):

```markdown
# Contributor Covenant Code of Conduct

## Our Pledge

We as members, contributors, and leaders pledge to make participation in our
community a harassment-free experience for everyone, regardless of age, body
size, visible or invisible disability, ethnicity, sex characteristics, gender
identity and expression, level of experience, education, socio-economic status,
nationality, personal appearance, race, caste, color, religion, or sexual
identity and orientation.

We pledge to act and interact in ways that contribute to an open, welcoming,
diverse, inclusive, and healthy community.

[... rest of standard Contributor Covenant text]

## Enforcement

Instances of abusive, harassing, or otherwise unacceptable behavior may be
reported to the community leaders responsible for enforcement at
conduct@avlonlabs.com.

All complaints will be reviewed and investigated promptly and fairly.
```

---

### 4. SECURITY.md

```markdown
# Security Policy

## Supported Versions

| Version | Supported          |
| ------- | ------------------ |
| 1.0.x   | :white_check_mark: |
| < 1.0   | :x:                |

## Reporting a Vulnerability

**Please do not report security vulnerabilities through public GitHub issues.**

Instead, please report them via email to security@avlonlabs.com.

You should receive a response within 48 hours. If for some reason you do not,
please follow up via email to ensure we received your original message.

Please include the following information:

- Type of issue (e.g. buffer overflow, SQL injection, cross-site scripting)
- Full paths of source file(s) related to the manifestation of the issue
- The location of the affected source code (tag/branch/commit or direct URL)
- Any special configuration required to reproduce the issue
- Step-by-step instructions to reproduce the issue
- Proof-of-concept or exploit code (if possible)
- Impact of the issue, including how an attacker might exploit it

## Preferred Languages

We prefer all communications to be in English.

## Disclosure Policy

We follow the principle of [Coordinated Vulnerability Disclosure](https://vuls.cert.org/confluence/display/CVD).

When we receive a security bug report, we will:

1. Confirm the problem and determine affected versions
2. Audit code to find any similar problems
3. Prepare fixes for all supported versions
4. Release patches as soon as possible

## Security Updates

Security updates will be released as patch versions (e.g., 1.0.1, 1.0.2).

Subscribe to our [security announcements](https://github.com/avlonlabs/pyx/security/advisories).
```

---

### 5. CHANGELOG.md

```markdown
# Changelog

All notable changes to PyX will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- Initial project structure
- Apache 2.0 license
- Project manifesto

## [1.0.0] - 2025-12-XX (Target)

### Added
- File-based routing for Python and TypeScript
- Python bridge via PyO3
- TypeScript bundling via SWC
- Hot reload for development
- `@AIRoute` decorator for streaming responses
- `use_model()` function for OpenAI and Anthropic
- `auto_memory()` for conversation context
- `ChatBox` React component
- `useChat()` React hook
- CLI commands: `pyx init`, `pyx dev`, `pyx build`
- Project templates: default, chatbot, rag, agent
- Comprehensive documentation

### Technical
- Rust engine with Axum HTTP server
- Python framework with FastAPI patterns
- React UI library with Tailwind CSS
- Support for streaming LLM responses
- Automatic memory management

[Unreleased]: https://github.com/avlonlabs/pyx/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/avlonlabs/pyx/releases/tag/v1.0.0
```

---

### 6. .github/ISSUE_TEMPLATE/bug_report.md

```markdown
---
name: Bug Report
about: Create a report to help us improve PyX
title: '[BUG] '
labels: bug
assignees: ''
---

## 🐛 Bug Description

A clear and concise description of what the bug is.

## 🔄 Steps to Reproduce

1. Go to '...'
2. Run command '...'
3. See error

## ✅ Expected Behavior

What you expected to happen.

## ❌ Actual Behavior

What actually happened.

## 📋 Environment

- OS: [e.g., macOS 14.0, Ubuntu 22.04, Windows 11]
- PyX Version: [e.g., 1.0.0]
- Python Version: [e.g., 3.11.5]
- Rust Version: [e.g., 1.75.0]
- Node.js Version: [e.g., 20.11.0]

## 📸 Screenshots / Logs

If applicable, add screenshots or error logs.

```
Paste error logs here
```

## 📦 Code Sample

If applicable, provide a minimal reproducible example:

```python
# Your code here
```

## 🔗 Additional Context

Any other context about the problem.
```

---

### 7. .github/ISSUE_TEMPLATE/feature_request.md

```markdown
---
name: Feature Request
about: Suggest an idea for PyX
title: '[FEATURE] '
labels: enhancement
assignees: ''
---

## 🚀 Feature Description

A clear and concise description of the feature you'd like.

## 🎯 Problem Statement

What problem does this feature solve? Is your feature request related to a problem?

**Example:** "I'm frustrated when [...]"

## 💡 Proposed Solution

How would you like this feature to work?

```python
# Example API design
from pyx import NewFeature

feature = NewFeature()
feature.do_something()
```

## 🔄 Alternatives Considered

What alternatives have you considered?

## 📊 Use Cases

Who would benefit from this feature? Provide specific examples.

1. Use case 1: [...]
2. Use case 2: [...]

## ⚙️ Implementation Ideas

(Optional) Any ideas on how to implement this?

## 📝 Additional Context

Add any other context, screenshots, or examples.
```

---

### 8. .github/PULL_REQUEST_TEMPLATE.md

```markdown
## 📝 Description

Brief description of what this PR does.

Fixes #(issue)

## 🔄 Type of Change

- [ ] 🐛 Bug fix (non-breaking change which fixes an issue)
- [ ] ✨ New feature (non-breaking change which adds functionality)
- [ ] 💥 Breaking change (fix or feature that would cause existing functionality to not work as expected)
- [ ] 📚 Documentation update
- [ ] 🎨 Style update (formatting, renaming)
- [ ] ♻️ Code refactoring (no functional changes)
- [ ] ⚡ Performance improvement
- [ ] ✅ Test update

## 🧪 Testing

Describe the tests you ran and how to reproduce them.

- [ ] Existing tests pass (`./scripts/test.sh`)
- [ ] Added new tests for this change
- [ ] Manual testing performed

**Test Instructions:**
```bash
# How to test this PR
pyx init test-app
cd test-app
pyx dev
```

## 📸 Screenshots / Demos

If applicable, add screenshots or GIFs.

## ✅ Checklist

- [ ] My code follows the project's style guidelines
- [ ] I have performed a self-review of my code
- [ ] I have commented my code, particularly in hard-to-understand areas
- [ ] I have made corresponding changes to the documentation
- [ ] My changes generate no new warnings
- [ ] I have added tests that prove my fix is effective or that my feature works
- [ ] New and existing unit tests pass locally with my changes
- [ ] Any dependent changes have been merged and published
- [ ] I have updated the CHANGELOG.md

## 📚 Documentation

- [ ] README.md updated (if needed)
- [ ] API documentation updated (if needed)
- [ ] Examples updated (if needed)

## 🔗 Related Issues

- Closes #
- Related to #

## 💬 Additional Notes

Any additional information for reviewers.
```

---

### 9. .github/workflows/ci.yml

```yaml
name: CI

on:
  push:
    branches: [main, develop]
  pull_request:
    branches: [main, develop]

env:
  RUST_VERSION: 1.75.0
  PYTHON_VERSION: 3.11
  NODE_VERSION: 20

jobs:
  # Rust tests and checks
  rust:
    name: Rust Tests
    runs-on: ${{ matrix.os }}
    strategy:
      matrix:
        os: [ubuntu-latest, macos-latest, windows-latest]
    steps:
      - uses: actions/checkout@v4
      
      - name: Install Rust
        uses: dtolnay/rust-toolchain@master
        with:
          toolchain: ${{ env.RUST_VERSION }}
          components: rustfmt, clippy
      
      - name: Cache Rust
        uses: Swatinem/rust-cache@v2
      
      - name: Check formatting
        run: cargo fmt --all -- --check
      
      - name: Run Clippy
        run: cargo clippy --all-targets --all-features -- -D warnings
      
      - name: Run tests
        run: cargo test --workspace --all-features
      
      - name: Build release
        run: cargo build --release

  # Python tests and checks
  python:
    name: Python Tests
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      
      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: ${{ env.PYTHON_VERSION }}
      
      - name: Install dependencies
        run: |
          cd python
          pip install -e ".[dev]"
      
      - name: Check formatting (ruff)
        run: |
          cd python
          ruff format --check .
      
      - name: Lint (ruff)
        run: |
          cd python
          ruff check .
      
      - name: Type check (mypy)
        run: |
          cd python
          mypy pyx
      
      - name: Run tests
        run: |
          cd python
          pytest --cov=pyx --cov-report=xml
      
      - name: Upload coverage
        uses: codecov/codecov-action@v3
        with:
          file: ./python/coverage.xml
          flags: python

  # TypeScript tests and checks
  typescript:
    name: TypeScript Tests
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      
      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: ${{ env.NODE_VERSION }}
      
      - name: Install pnpm
        uses: pnpm/action-setup@v2
        with:
          version: 8
      
      - name: Install dependencies
        run: |
          cd typescript
          pnpm install
      
      - name: Check formatting (prettier)
        run: |
          cd typescript
          pnpm prettier --check .
      
      - name: Lint (eslint)
        run: |
          cd typescript
          pnpm eslint .
      
      - name: Type check
        run: |
          cd typescript
          pnpm tsc --noEmit
      
      - name: Run tests
        run: |
          cd typescript
          pnpm test --coverage
      
      - name: Build
        run: |
          cd typescript
          pnpm build

  # Integration tests
  integration:
    name: Integration Tests
    runs-on: ubuntu-latest
    needs: [rust, python, typescript]
    steps:
      - uses: actions/checkout@v4
      
      - name: Install Rust
        uses: dtolnay/rust-toolchain@master
        with:
          toolchain: ${{ env.RUST_VERSION }}
      
      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: ${{ env.PYTHON_VERSION }}
      
      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: ${{ env.NODE_VERSION }}
      
      - name: Build PyX
        run: cargo build --release
      
      - name: Install Python framework
        run: |
          cd python
          pip install -e .
      
      - name: Install Playwright
        run: |
          cd tests/e2e
          pnpm install
          pnpm playwright install --with-deps
      
      - name: Run E2E tests
        run: |
          cd tests/e2e
          pnpm test
      
      - name: Upload test results
        if: always()
        uses: actions/upload-artifact@v3
        with:
          name: playwright-report
          path: tests/e2e/playwright-report/

  # Check documentation builds
  docs:
    name: Documentation
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      
      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: ${{ env.NODE_VERSION }}
      
      - name: Install dependencies
        run: |
          cd docs
          npm install
      
      - name: Build docs
        run: |
          cd docs
          npm run build
```

---

### 10. .github/workflows/release.yml

```yaml
name: Release

on:
  push:
    tags:
      - 'v*'

env:
  RUST_VERSION: 1.75.0

jobs:
  create-release:
    name: Create Release
    runs-on: ubuntu-latest
    outputs:
      upload_url: ${{ steps.create_release.outputs.upload_url }}
    steps:
      - uses: actions/checkout@v4
      
      - name: Create Release
        id: create_release
        uses: actions/create-release@v1
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        with:
          tag_name: ${{ github.ref }}
          release_name: Release ${{ github.ref }}
          draft: false
          prerelease: false

  build-binaries:
    name: Build Binaries
    needs: create-release
    runs-on: ${{ matrix.os }}
    strategy:
      matrix:
        include:
          - os: ubuntu-latest
            target: x86_64-unknown-linux-gnu
            asset_name: pyx-linux-amd64
          - os: macos-latest
            target: x86_64-apple-darwin
            asset_name: pyx-macos-amd64
          - os: macos-latest
            target: aarch64-apple-darwin
            asset_name: pyx-macos-arm64
          - os: windows-latest
            target: x86_64-pc-windows-msvc
            asset_name: pyx-windows-amd64.exe
    
    steps:
      - uses: actions/checkout@v4
      
      - name: Install Rust
        uses: dtolnay/rust-toolchain@master
        with:
          toolchain: ${{ env.RUST_VERSION }}
          targets: ${{ matrix.target }}
      
      - name: Build release binary
        run: cargo build --release --target ${{ matrix.target }}
      
      - name: Upload Release Asset
        uses: actions/upload-release-asset@v1
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        with:
          upload_url: ${{ needs.create-release.outputs.upload_url }}
          asset_path: ./target/${{ matrix.target }}/release/pyx${{ matrix.os == 'windows-latest' && '.exe' || '' }}
          asset_name: ${{ matrix.asset_name }}
          asset_content_type: application/octet-stream

  publish-python:
    name: Publish Python Package
    needs: create-release
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      
      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: 3.11
      
      - name: Build package
        run: |
          cd python
          pip install build
          python -m build
      
      - name: Publish to PyPI
        uses: pypa/gh-action-pypi-publish@release/v1
        with:
          password: ${{ secrets.PYPI_API_TOKEN }}
          packages-dir: python/dist/

  publish-npm:
    name: Publish NPM Packages
    needs: create-release
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      
      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: 20
          registry-url: 'https://registry.npmjs.org'
      
      - name: Install pnpm
        uses: pnpm/action-setup@v2
        with:
          version: 8
      
      - name: Install dependencies
        run: |
          cd typescript
          pnpm install
      
      - name: Build packages
        run: |
          cd typescript
          pnpm build
      
      - name: Publish to NPM
        run: |
          cd typescript
          pnpm publish -r --access public
        env:
          NODE_AUTH_TOKEN: ${{ secrets.NPM_TOKEN }}
```

---

### 11. Cargo.toml (Workspace Root)

```toml
[workspace]
resolver = "2"
members = [
    "crates/pyx-engine",
    "crates/pyx-core",
    "crates/pyx-macros",
]

[workspace.package]
version = "1.0.0"
edition = "2021"
license = "Apache-2.0"
repository = "https://github.com/avlonlabs/pyx"
homepage = "https://pyx.dev"
documentation = "https://pyx.dev/docs"
authors = ["Avlon Labs <team@avlonlabs.com>"]

[workspace.dependencies]
# HTTP Server
axum = "0.7"
tokio = { version = "1.35", features = ["full"] }
tower = "0.4"
tower-http = { version = "0.5", features = ["fs", "cors"] }

# Python Bridge
pyo3 = { version = "0.20", features = ["auto-initialize"] }

# TypeScript Bundling
swc = "0.273"
swc_ecma_parser = "0.146"

# File System
walkdir = "2.4"
notify = "6.1"

# CLI
clap = { version = "4.4", features = ["derive"] }

# Serialization
serde = { version = "1.0", features = ["derive"] }
serde_json = "1.0"

# Error Handling
anyhow = "1.0"
thiserror = "1.0"

# Logging
tracing = "0.1"
tracing-subscriber = "0.3"

# Internal crates
pyx-core = { path = "crates/pyx-core" }
pyx-macros = { path = "crates/pyx-macros" }

[profile.release]
opt-level = 3
lto = true
codegen-units = 1
strip = true

[profile.dev]
opt-level = 0
debug = true
```

---

### 12. rust-toolchain.toml

```toml
[toolchain]
channel = "1.75.0"
components = ["rustfmt", "clippy"]
profile = "minimal"
```

---

### 13. .editorconfig

```ini
root = true

[*]
charset = utf-8
end_of_line = lf
insert_final_newline = true
trim_trailing_whitespace = true

[*.{rs,py,ts,tsx,js,jsx}]
indent_style = space
indent_size = 4

[*.{json,yml,yaml,toml,md}]
indent_style = space
indent_size = 2

[*.py]
indent_size = 4

[Makefile]
indent_style = tab
```

---

### 14. .prettierrc

```json
{
  "semi": false,
  "singleQuote": true,
  "tabWidth": 2,
  "trailingComma": "es5",
  "printWidth": 80,
  "arrowParens": "avoid"
}
```

---

### 15. .gitignore

```gitignore
# Rust
target/
Cargo.lock
*.pdb

# Python
__pycache__/
*.py[cod]
*$py.class
*.so
.Python
build/
develop-eggs/
dist/
downloads/
eggs/
.eggs/
lib/
lib64/
parts/
sdist/
var/
wheels/
*.egg-info/
.installed.cfg
*.egg
.venv/
venv/
ENV/
env/

# Node.js
node_modules/
npm-debug.log*
yarn-debug.log*
yarn-error.log*
.pnpm-debug.log*
.npm
.eslintcache

# IDE
.vscode/
.idea/
*.swp
*.swo
*~
.DS_Store

# PyX
.pyx/
*.pyx-cache/

# Environment
.env
.env.local
.env.*.local

# Testing
coverage/
.coverage
*.cover
.hypothesis/
.pytest_cache/
playwright-report/
test-results/

# Build
dist/
out/
.next/
.vercel/

# Logs
*.log
logs/

# OS
Thumbs.db
```

---

### 16. scripts/setup.sh

```bash
#!/bin/bash

set -e

echo "🚀 Setting up PyX development environment..."

# Check prerequisites
echo "📋 Checking prerequisites..."

if ! command -v rustc &> /dev/null; then
    echo "❌ Rust not found. Install from: https://rustup.rs/"
    exit 1
fi

if ! command -v python3 &> /dev/null; then
    echo "❌ Python 3 not found. Install Python 3.11+