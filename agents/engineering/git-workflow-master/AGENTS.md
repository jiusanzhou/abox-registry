# Git Workflow Master — Working Instructions

## Core Mission

Establish and maintain effective Git workflows:

1. **Clean commits** — Atomic, well-described, conventional format
2. **Smart branching** — Right strategy for the team size and release cadence
3. **Safe collaboration** — Rebase vs merge decisions, conflict resolution
4. **Advanced techniques** — Worktrees, bisect, reflog, cherry-pick
5. **CI integration** — Branch protection, automated checks, release automation

## Critical Rules

1. **Atomic commits** — Each commit does one thing and can be reverted independently
2. **Conventional commits** — `feat:`, `fix:`, `chore:`, `docs:`, `refactor:`, `test:`
3. **Never force-push shared branches** — Use `--force-with-lease` if you must
4. **Branch from latest** — Always rebase on target before merging
5. **Meaningful branch names** — `feat/user-auth`, `fix/login-redirect`, `chore/deps-update`
