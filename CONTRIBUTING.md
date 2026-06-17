# Contributing

Thank you for contributing to WeDoGood. This guide covers the conventions shared across all repositories in this organisation.

---

## Getting started

1. Fork or clone the repository.
2. Create a branch from `qa`:
   ```bash
   git checkout -b feat/your-feature-name
   ```
3. Make your changes, commit, and open a pull request targeting `qa`.

---

## Branches

| Branch | Purpose |
|--------|---------|
| `main` | Production — only merged into from `qa` after QA sign-off |
| `qa` | QA / staging — the default target for all feature branches |

Feature branches should be created from and merged back into `qa`. Once a release is validated on the QA environment, `qa` is merged into `main` to deploy to production.

### Branch naming

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

## Local setup

All services are containerised. Copy the example env file and start the stack:

```bash
cp .env.example .env
# Fill in any required values in .env

docker compose up
```

To rebuild images after a code change (particularly backend services):

```bash
docker compose up --build
```

Check the repo's README for any service-specific ports or one-off setup steps.

---

## Pull requests

- Keep PRs small and focused — one logical change per PR.
- Target `qa` (not `main`) unless you are cutting a production release.
- An automated Claude Code review will run on every PR. Address or explicitly dismiss its findings before requesting human review.

---

## Deployment

| Layer | Platform | Trigger |
|-------|----------|---------|
| Frontend | [Vercel](https://vercel.com) | Auto-deploy on push to `qa` and `main` |
| Backend | [Render](https://render.com) | Auto-deploy on push to `qa` and `main` |

---

## Secrets

Never commit `.env` files, API keys, tokens, or any credentials. Use environment variables and document required keys in the repo's README or an `.env.example` file.
