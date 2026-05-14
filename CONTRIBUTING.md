# Contributing to Nexara

> Nexara is contributor-first. This guide exists to make your experience — from first issue to merged PR — as clear and welcoming as possible.

---

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Ways to Contribute](#ways-to-contribute)
- [Development Setup](#development-setup)
- [Submitting Issues](#submitting-issues)
- [Submitting Pull Requests](#submitting-pull-requests)
- [Commit Conventions](#commit-conventions)
- [Testing Requirements](#testing-requirements)
- [Review Process](#review-process)
- [Community Programs](#community-programs)

---

## Code of Conduct

All contributors must follow our [Code of Conduct](CODE_OF_CONDUCT.md). We enforce it firmly and fairly. This community is for everyone.

---

## Ways to Contribute

You don't need to write code to make a meaningful contribution.

**For everyone:**
- Report bugs with clear reproduction steps
- Suggest features via GitHub Discussions before filing an issue
- Fix typos and improve documentation clarity
- Answer questions in Discord or GitHub Discussions
- Write blog posts, tutorials, and talks about Nexara

**For developers:**
- Fix bugs labeled `bug` + `help wanted`
- Implement features labeled `enhancement` + `good first issue`
- Write or expand test coverage
- Build plugins via the Nexara plugin SDK
- Profile and improve performance

**For AI/ML practitioners:**
- Contribute model provider adapters
- Build evaluation and benchmarking frameworks
- Write reference implementations of agentic patterns

---

## Development Setup

### Prerequisites

| Tool | Version | Notes |
|---|---|---|
| Node.js | ≥ 20.x | LTS recommended |
| pnpm | ≥ 9.x | Monorepo workspace manager |
| Git | ≥ 2.40 | |
| Docker | ≥ 24 | Required for integration tests |

### Steps

```bash
# 1. Fork on GitHub, then clone your fork
git clone https://github.com/YOUR_USERNAME/neuroweave.git
cd neuroweave

# 2. Add upstream remote
git remote add upstream https://github.com/nexara-org/neuroweave.git

# 3. Install all workspace dependencies
pnpm install

# 4. Build all packages
pnpm build

# 5. Verify your setup
pnpm test
```

### Common Commands

```bash
pnpm build          # Build all packages
pnpm dev            # Watch mode
pnpm test           # Full test suite
pnpm test:unit      # Unit tests only (fast, no network)
pnpm test:e2e       # End-to-end tests (requires Docker)
pnpm lint           # ESLint + TypeScript type check
pnpm format         # Prettier
pnpm changeset      # Create a changeset for your PR
```

---

## Submitting Issues

### Before Opening an Issue

1. Search existing issues (open and closed)
2. Check the [FAQ](https://docs.nexara.dev/faq) and [Discussions](https://github.com/nexara-org/neuroweave/discussions)
3. Reproduce on the latest `main` branch

### Issue Templates

| Template | When to Use |
|---|---|
| 🐛 Bug Report | Something is broken or behaving incorrectly |
| ✨ Feature Request | Proposing new functionality |
| 📖 Documentation | Missing, incorrect, or unclear docs |
| 🔐 Security | **Do NOT use issues** — see [SECURITY.md](SECURITY.md) |

A good bug report includes: package version, Node.js version, OS, a **minimal reproduction**, expected behavior, actual behavior, and full error output.

---

## Submitting Pull Requests

For non-trivial changes, open an issue or Discussion first. For small fixes (typos, obvious bugs), open the PR directly.

### PR Checklist

- [ ] `pnpm build` passes
- [ ] `pnpm test` passes
- [ ] New code has test coverage
- [ ] `pnpm lint` passes with no errors
- [ ] Documentation updated if behavior changed
- [ ] Changeset added (`pnpm changeset`) for user-facing changes
- [ ] PR description explains **what** changed and **why**

### PR Title Format

```
feat(core): add resumable checkpoint support for long-running agents
fix(providers): handle rate limit retry with exponential backoff
docs(plugins): add plugin SDK cookbook with examples
```

### Keeping Your Branch Updated

```bash
git fetch upstream
git rebase upstream/main
```

Rebase only — do not merge `main` into your branch.

---

## Commit Conventions

We follow [Conventional Commits](https://www.conventionalcommits.org/).

```
<type>(<scope>): <short description>
```

**Types:** `feat` | `fix` | `docs` | `refactor` | `test` | `chore` | `perf` | `ci`

**Scopes:** `core` | `agents` | `plugins` | `providers` | `studio` | `cli` | `docs`

Breaking changes: add `!` after scope or include `BREAKING CHANGE:` in the footer.

---

## Testing Requirements

All changes must include appropriate tests. PRs that reduce coverage without justification will not be merged.

| Layer | Location | Purpose |
|---|---|---|
| Unit | `packages/*/tests/unit/` | Pure functions, class methods, edge cases |
| Integration | `packages/*/tests/integration/` | Module interactions |
| E2E | `tests/e2e/` | Full pipeline execution |

Use `MockProvider` for tests that don't need real API calls:

```typescript
import { MockProvider } from "@nexara/testing";
const provider = new MockProvider({ responses: [{ text: "mock" }] });
```

---

## Review Process

- **Initial response:** within 2 business days
- **Full review:** within 5 business days
- **Complex PRs:** may require multiple rounds

Keep PRs focused. Respond to feedback promptly. Don't force-push after review has started.

---

## Community Programs

- 🎓 **GSoC / GSSoC** — We participate annually. Best preparation: make small contributions before applications open. [See project ideas →](https://github.com/nexara-org/neuroweave/discussions/categories/gsoc)
- 🏆 **Nexara Champions** — Active contributors recognized with early access, direct team communication, and release credit.
- 🧑‍🏫 **Mentorship** — New to open source? Say so in Discord (#mentorship) or in your first issue.

---

## Questions?

- **Discord:** [discord.gg/nexara](https://discord.gg/nexara) — fastest response
- **GitHub Discussions:** for longer-form technical questions
- **Email:** contributors@nexara.dev

Thank you for being part of Nexara. Every contribution matters. 🚀
