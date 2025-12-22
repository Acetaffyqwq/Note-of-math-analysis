# Copilot / AI Agent Instructions for Note-of-math-analysis

Purpose
- Help AI coding agents quickly understand repository structure, site build, editing patterns, and safe edit boundaries.

Big picture
- This repo is a small content-driven static site (Jekyll-style): root contains `_config.yml`, a `_layouts/` folder, and content in top-level folders such as `algebra/`, `math-analysis/`, and `geometry/`.
- Content files are Markdown pages under those directories. Styling lives in `assets/css/style.css` and layout templates in `_layouts/default.html`.

Key files and directories (examples)
- `README.md` — repo overview.
- `_config.yml` — site config (Jekyll/GitHub Pages).
- `_layouts/default.html` — main HTML wrapper; avoid broad refactors here.
- `algebra/13-Eigenvalue.md` — typical content page to use as an example when editing content.
- `math-analysis/` — main collection of course notes and canonical naming patterns.

Project-specific conventions
- Files are organized by topic directories; filenames often start with numbers (e.g. `1-sequence-limit.md`) to indicate order — preserve numeric prefixes when renaming.
- Most work should target individual `.md` content files; prefer lightweight edits (typo fixes, math notation, small restructuring) over large structural changes.
- Keep site layout and CSS changes minimal and explain rationale when proposing changes.
- Check for YAML front-matter in `.md` files before adding or removing metadata — some pages may rely on it for rendering.

Local preview / build notes
- This is a Jekyll-style site. To preview locally, use `jekyll serve` or the GitHub Pages preview workflow. If Jekyll is not installed, recommend `gem install jekyll bundler` then `bundle install` if a `Gemfile` is present.
- If you modify `_layouts/default.html` or `assets/css/style.css`, verify visually by serving the site locally.

Editing guidance for AI agents
- Favor edits to content files under `algebra/`, `math-analysis/`, and `geometry/`.
- When changing math notation, preserve existing inline conventions (use $...$ for inline LaTeX if present) — check the file first.
- Avoid changing permalink or ordering unless asked — these are implied by filenames and `_config.yml`.
- For multi-file refactors (renaming sections, moving pages), produce a clear plan and update `_config.yml` or any index pages referencing the moved files.

Examples of safe, actionable tasks
- Fix typo in [algebra/13-Eigenvalue.md](algebra/13-Eigenvalue.md).
- Add a short explanatory paragraph to [math-analysis/1-sequence-limit.md](math-analysis/1-sequence-limit.md) while preserving front-matter.
- Tweak CSS in `assets/css/style.css` for better math rendering, then run a local `jekyll serve` to confirm layout.

What to avoid
- Large-scale layout rewrites in `_layouts/` without explicit human approval.
- Removing numeric filename prefixes or changing URL structure without coordinating updates to any indices or `_config.yml`.

If unsure
- Open the specific `.md` page and check for YAML front-matter and example markup before editing.
- Ask a human reviewer when the change touches `_layouts/` or site configuration.

Request for feedback
- If any examples are missing or unclear, please point to a specific file to incorporate into this guide.
