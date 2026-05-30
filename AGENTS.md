# AGENTS.md

## Cursor Cloud specific instructions

This repository is a **Git learning / notes** repo ([qfvip/git](https://github.com/qfvip/git)). It does not contain an application, package manager, Docker services, or automated tests.

### What to run

| Activity | Command / notes |
|----------|-----------------|
| Verify repo | `git status`, `git log --oneline` |
| Practice Git (isolated) | Use a temp directory (e.g. `/tmp/git-practice`) with `git init` so you do not dirty the main working tree unless the task requires it |
| Lint / test / build | **N/A** — no linters, test runners, or build scripts in this repo |

### Services

No processes need to be started. There is no `docker-compose`, dev server, or database.

### Dependencies

Only **Git** is required. It is available on the Cloud Agent VM (`git --version`).

### Secrets

No `.env` or app secrets are used. Pushing to GitHub uses the environment’s configured `origin` credentials.

### Gotchas

- Do not expect `npm install`, `pip install`, or similar — there is no lockfile or manifest.
- The README clone URL is `https://github.com/qfvip/git.git`; the workspace is already that clone on `main`.
