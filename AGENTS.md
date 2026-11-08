# AGENTS.md

Minimal **Astro 7** static site for Springs Digital: a dark coming-soon landing page. Output: `dist/`.

## Required skills

**You must** read and apply the matching skill (`SKILL.md` at the path below) before implementing or advising in that area. Do not skip them or substitute ad-hoc workflows.

| Skill | Path | Apply when |
| ----- | ---- | ---------- |
| **git-commit** | `/Users/bruno/.agents/skills/git-commit/SKILL.md` | **Every** git commit the user requests or you create with approval — [Conventional Commits](https://www.conventionalcommits.org/) only; see [Git commits](#git-commits). |

In chat, attach or invoke **`/git-commit`** when committing so the same workflow is explicit.

## Run

- `npm install`
- `npm run dev` — local dev server
- `npm run build` — static build to `./dist/`
- `npm run preview` — preview production build

Node **>= 22.12.0** (`package.json` `engines`).

## Project layout

| Area | Location |
| ---- | -------- |
| Home / coming soon | `src/pages/index.astro` |
| Shared layout (title, dark theme) | `src/layouts/Layout.astro` |
| Static assets | `public/` |
| Astro config | `astro.config.mjs` |
| Commit lint (Husky) | `commitlint.config.js`, `.husky/commit-msg` |

Unused Astro starter files (`src/components/Welcome.astro`, `src/assets/*`) may be removed when tightening the repo.

## Git commits

**ALWAYS** use the **git-commit** skill for every commit:

1. Read `/Users/bruno/.agents/skills/git-commit/SKILL.md` (or user-attached **git-commit** / **`/git-commit`**).
2. Run `git status` and inspect `git diff` / `git diff --staged`.
3. Stage only the files that belong to the change; never commit secrets (`.env`, credentials, keys).
4. Write a [Conventional Commits](https://www.conventionalcommits.org/) message: `type[optional scope]: imperative description` (present tense, under ~72 characters in the subject).

Never use ad-hoc commit messages or skip this workflow. Husky runs **commitlint** on `commit-msg`; messages must pass conventional commit rules.

Git safety (from the skill): do not update git config; do not skip hooks unless the user asks; do not force-push `main`/`master`; if a hook fails, fix the issue and create a **new** commit (do not amend unless the user's rules allow it).

Only create commits when the user explicitly asks.

## Learned User Preferences

- **ALWAYS** use the `git-commit` skill for every git commit: analyze status and diff, stage appropriately, and write a Conventional Commits message. Never commit with ad-hoc messages or skip this workflow.

## Learned Workspace Facts

- Springs Digital site was bootstrapped from `brunocalderon-site` (same Astro + Husky + commitlint stack).
- Default page title: **Springs Digital — Coming soon**; homepage shows brand line + **Coming soon** heading.
- Package name: `springsdigital-site`.
