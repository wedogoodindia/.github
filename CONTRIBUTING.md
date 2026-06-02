# Contributing

Thank you for contributing to WeDoGood. This guide covers the conventions shared across all repositories in this organisation.

---

## Getting started

1. Fork or clone the repository.
2. Create a branch from `main`:
   ```bash
   git checkout -b feat/your-feature-name
   ```
3. Make your changes, commit, and open a pull request.

---

## Branch naming

| Prefix | When to use |
|--------|-------------|
| `feat/` | New feature or behaviour |
| `fix/` | Bug fix |
| `chore/` | Tooling, dependencies, config |
| `docs/` | Documentation only |
| `test/` | Tests only |

---

## Commit style

Use the imperative mood, present tense:

- ✅ `add mentor scoring endpoint`
- ✅ `fix null check in profile resolver`
- ❌ `added mentor scoring endpoint`
- ❌ `fixed null check`

Keep the subject line under 72 characters. Add a body when the *why* is non-obvious.

---

## Python repos

Python repos in this org are managed with [`uv`](https://docs.astral.sh/uv/).

```bash
# Install dependencies
uv sync

# Run tests
uv run pytest

# Add a runtime dependency
uv add <package>

# Add a dev-only dependency
uv add --dev <package>
```

- Never edit `requirements.txt` by hand.
- Always commit both `pyproject.toml` **and** `uv.lock`.

---

## JavaScript / Node repos

```bash
# Install dependencies
npm install

# Run tests
npm test

# Start dev server
npm run dev
```

---

## Pull requests

- Keep PRs small and focused — one logical change per PR.
- Link the related issue in the PR description (`Closes #123`).
- All checklist items in the PR template must be ticked before requesting review.
- Prefer rebasing over merging to keep a clean history.

---

## Secrets

Never commit `.env` files, API keys, tokens, or any credentials. Use environment variables and document required keys in the repo's README or an `.env.example` file.
