# ⚡ Nivex — Next-Generation Package Management

<p align="center">
  <strong>A smarter way to manage JavaScript and TypeScript packages.</strong>
  <br />
  Built for flexibility, reliable downloads, and a better developer experience.
</p>

<p align="center">
  ![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
  ![Node.js](https://img.shields.io/badge/Node.js-20.18%2B-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
  ![ESM](https://img.shields.io/badge/ESM-Native-black?style=for-the-badge)
  ![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)
  ![Status](https://img.shields.io/badge/Status-Experimental-orange?style=for-the-badge)
</p>

---

## 🚀 Meet Nivex

**Nivex (NPMX)** is an experimental TypeScript package manager built around a simple idea: developers deserve more control over how their packages are downloaded, verified, and managed.

From configurable registries and mirror strategies to caching and package integrity, Nivex aims to make package management more flexible and resilient.

Whether you're building JavaScript applications, developing TypeScript libraries, or exploring new developer tooling, Nivex is designed to grow into a modern package management solution.

> [!WARNING]
> Nivex is experimental and under active development. Its capabilities and compatibility must be verified against the current implementation. It is not yet a drop-in replacement for npm.

## ✨ Why Nivex?

- 🌐 **Flexible registries** — a foundation for configurable package sources.
- 🔄 **Mirror-aware downloads** — explore alternative registries and failover strategies.
- 🛡️ **Integrity verification** — help detect package content that differs from expected integrity data.
- 📦 **Package caching** — reduce repeated downloads when cached content is reusable.
- ⚡ **Network resilience** — configurable retries and timeouts where implemented.
- 🧩 **TypeScript-first** — built with TypeScript and native ES modules.
- 🛠️ **Dedicated CLI** — manage the tool through the `npmx` command.
- 🔍 **Developer experience** — clearer diagnostics and a maintainable architecture.

*Feature availability depends on the current source code. These goals should not be interpreted as guarantees that every feature is complete.*

## 📋 Table of Contents

- [Requirements](#-requirements)
- [Installation](#-installation)
- [Quick Start](#-quick-start)
- [CLI](#-cli)
- [Registries and Mirrors](#-registries-and-mirrors)
- [Configuration](#️-configuration)
- [Cache and Security](#-cache-and-security)
- [Development](#-development)
- [Project Status](#-project-status)
- [Roadmap](#️-roadmap)
- [Contributing](#-contributing)
- [FAQ](#-faq)
- [License](#-license)

## 💻 Requirements

Before getting started, make sure you have:

- **Node.js:** `20.18.0` or newer
- **npm:** installed and available in your terminal
- **Network access:** required for downloading packages from remote registries

Operating-system compatibility should be verified against the current implementation.

## 📦 Installation

Nivex is intended to be distributed through npm.

After the package has been published under the name `nivex`, install it globally:

```bash
npm install --global nivex
```

Verify the installation:

```bash
npmx --version
```

View the available commands:

```bash
npmx --help
```

> [!NOTE]
> Installation from npm will work only after the package name is available and the published package includes the required compiled files.

### Install from source

```bash
git clone <YOUR_REPOSITORY_URL>
cd nivex-pm
npm install
npm run build
```

Replace `<YOUR_REPOSITORY_URL>` with the actual Git repository URL.

## ⚡ Quick Start

Start by exploring the available CLI options:

```bash
npmx --help
```

Check the installed version:

```bash
npmx --version
```

For package installation, dependency management, and registry configuration, refer to the commands actually implemented in the current version.

Nivex does not automatically support every command offered by npm, pnpm, or Yarn.

## ⌨️ CLI

The Nivex command-line executable is called `npmx`.

| Command | Description |
|---|---|
| `npmx --help` | Display available commands and options |
| `npmx --version` | Display the installed version |

Additional commands should be listed here only after confirming their syntax and behavior in the source code.

## 🌐 Registries and Mirrors

Network reliability is an important part of the Nivex design.

The project aims to support a flexible registry workflow with capabilities such as:

- Configurable package registries
- Multiple mirror endpoints
- Mirror priorities
- Connection timeouts and retries
- Failover when a registry is unavailable
- Connectivity and latency diagnostics

The exact capabilities available depend on the current implementation.

### Performance philosophy

A mirror can sometimes improve download reliability or speed, but results depend on geographic location, network conditions, registry load, and cache state.

Nivex does not claim to be faster than npm without reproducible benchmarks.

## ⚙️ Configuration

Nivex aims to make package-source configuration easier to manage.

If the current implementation supports `.npmxrc.json`, document its verified structure, accepted fields, defaults, and precedence rules here.

Do not assume that configuration keys from npm or other package managers are compatible with Nivex.

A robust configuration system should clearly communicate:

- Active registry URLs
- Mirror selection and priority
- Retry and timeout settings
- Cache location
- Project-level and user-level settings

## 📦 Cache and Security

### Package cache

Caching can reduce repeated downloads and improve workflows when previously downloaded package contents can be reused.

Cache location, eviction behavior, offline support, and cache-management commands must be confirmed against the current implementation.

### Integrity verification

Integrity verification helps identify content that does not match an expected checksum.

However, a valid checksum does not prove that a package is trustworthy or free from malicious code. Always review dependencies and use trusted package sources.

### Security considerations

- Prefer HTTPS registry endpoints.
- Protect private registry credentials.
- Review dependencies before using them in sensitive projects.
- Verify the implementation's handling of redirects, archives, and integrity metadata.
- Do not assume lifecycle scripts are disabled or enabled without checking the source code.

## 🧑‍💻 Development

Nivex uses TypeScript and native ES modules.

Install dependencies:

```bash
npm install
```

Check TypeScript types:

```bash
npm run typecheck
```

Build the project:

```bash
npm run build
```

Run tests:

```bash
npm test
```

Run lint checks:

```bash
npm run lint
```

Check formatting:

```bash
npm run format:check
```

### Build output

The package is configured to expose compiled files from `dist/`, including the CLI entry point:

```text
dist/
├── cli/
│   └── main.js
└── index.js
```

The exact output depends on `tsconfig.json`. Confirm that the required files exist before publishing.

## 📊 Project Status

Nivex is currently **experimental**.

| Area | Status |
|---|---|
| TypeScript and ESM configuration | Configured |
| npm package metadata | Configured |
| `npmx` executable | Configured; output needs verification |
| Registry and mirror management | Verify implementation |
| Automatic mirror failover | Verify implementation |
| Dependency resolution | Verify implementation |
| Cache and offline installation | Verify implementation |
| Lockfile support | Verify implementation |
| Integrity verification | Verify implementation |
| Production readiness | Not established |

This table distinguishes project configuration from functionality that must be verified in the implementation.

## 🗺️ Roadmap

Potential future development goals:

- [ ] Expand registry and mirror management
- [ ] Improve network diagnostics
- [ ] Refine retry and failover behavior
- [ ] Strengthen dependency resolution
- [ ] Improve lockfile reproducibility
- [ ] Expand cache management
- [ ] Increase automated test coverage
- [ ] Improve cross-platform compatibility
- [ ] Publish reproducible performance benchmarks
- [ ] Document security guarantees and limitations

These items are planned goals, not promises of completion or release dates.

## 🤝 Contributing

Contributions and reproducible bug reports are welcome.

Before submitting a pull request:

1. Follow the project's existing code conventions.
2. Keep changes focused and explain their purpose.
3. Add or update tests when behavior changes.
4. Run the available type checks, tests, lint checks, and formatting checks.
5. Update documentation to match the actual implementation.

When reporting a bug, include your Node.js version, operating system, command, and relevant error output. Never publish passwords, access tokens, or private registry credentials.

## ❓ FAQ

### Is Nivex faster than npm?

That has not been established. Performance depends on the registry, network, dependency graph, and caching. Reliable comparisons require reproducible benchmarks.

### Can Nivex replace npm?

Not yet. Nivex is experimental and should not be treated as a drop-in replacement.

### Does it support private registries?

Verify private-registry and authentication support in the current implementation before relying on it.

### Can it install packages offline?

Offline installation depends on cache completeness and the implemented installation workflow. Complete offline support is not guaranteed.

### Does it execute lifecycle scripts?

Check the installer implementation before relying on any assumptions about package scripts. Script execution has security implications.

### Is Nivex production-ready?

No production-readiness guarantee is made. Use established tooling for critical production workflows until Nivex has been thoroughly tested.

## 📄 License

Nivex is intended to be distributed under the **MIT License**.

See [`LICENSE`](LICENSE) for the full license text if the file is present in the repository.

---

<p align="center">
  <strong>⚡ Nivex — A more flexible approach to package management.</strong>
  <br />
  <sub>Built with TypeScript. Designed to evolve.</sub>
</p>
