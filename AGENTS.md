# emergence - Codex Context

## Current Baseline

Jekyll portfolio site for `vpedreros.github.io`, implemented with the custom `emergence` design system. GitHub Pages deployment is handled by GitHub Actions, not by a theme gem or direct Pages source build.

- Runtime: Ruby 3.3.6, Gemfile constraint `jekyll ~> 4.3`, currently locked to Jekyll 4.4.1.
- Theme: Chirpy has been decoupled; do not reintroduce `jekyll-theme-chirpy`.
- Design reference: `DESIGN.md`.
- Main generated CSS: `assets/css/emergence.scss` -> `assets/css/emergence.css` through Jekyll/Sass.

## Layout System

| File | Role | Notes |
|------|------|-------|
| `_layouts/base.html` | HTML shell | Shared `head`/`body`, FontAwesome CDN, SEO tags, manifest |
| `_layouts/custom-page.html` | Top-level tab pages | Shared nav and page container |
| `_layouts/post.html` | Collection item pages | Left sidebar, TOC, body content |

Tab pages under `_tabs/*.md` keep their own HTML/Liquid directly in the file and usually set `layout: custom-page`.

## SCSS Structure

`assets/css/emergence.scss` is only the Sass entrypoint. It must keep Jekyll front matter, `@charset`, comments, and `@use` statements. Do not add page/component style rules there.

```text
assets/css/emergence.scss
_sass/emergence/
  _variables.scss
  _base.scss
  _typography.scss
  _components.scss
  _navigation.scss
  pages/
    _projects.scss
    _about.scss
    _post.scss
```

Rules:

- Add new style rules to `_sass/emergence/` partials, not to `assets/css/emergence.scss`.
- Use Dart Sass `@use`, not deprecated `@import`.
- Load variables first and page partials last.
- Keep UTF-8 builds: use `LANG=en_US.UTF-8` for local Jekyll commands.

## Active Content Collections

Active collections are registered in `_config.yml`. Inactive Notes and
Readings templates are preserved under
`_archive/legacy-template-features/notes-readings/`.

| Collection | Folder | Tab | Permalink |
|------------|--------|-----|-----------|
| `site.projects` | `_projects/` | `/projects/` | `/projects/:path/` |

Important contracts:

- Project entries use folder pages such as `_projects/example-project/index.md`.
- Homepage projects must set `project_type: physics` or
  `project_type: software`; this is the primary grouping. A third value,
  `ml` (applied ML / signal processing), is reserved for when the first
  such project is ready to publish — no tab/panel renders it yet (see the
  comment above the tab markup in `index.html`).
- Valid project `status` values are `completed`, `in-progress`, and `planned`.
- `index.html`, `_includes/project-card.html`, and `_sass/emergence/pages/_projects.scss` all depend on those exact status strings.
- `completed` projects are rendered as linkable rows. `in-progress` and `planned` projects are rendered as locked rows.
- Avoid introducing `active`; it is not part of the current renderer contract.
- `published: false` hides a project row through `_includes/project-card.html`.

## Build And Deploy

Local shell inside Codex may not put rbenv first, so prefer the explicit PATH form:

```bash
LANG=en_US.UTF-8 bundle exec jekyll build
LANG=en_US.UTF-8 bundle exec jekyll serve --livereload
bundle exec htmlproofer _site --disable-external
```

Deployment path:

- Push to `main` or `master`.
- `.github/workflows/pages-deploy.yml` runs `bundle exec jekyll b`, then `bundle exec htmlproofer _site --disable-external`, uploads `_site`, and deploys through `actions/deploy-pages`.
- `_site/`, `.jekyll-cache/`, `.sass-cache/`, `.bundle/`, `vendor/`, `_archive/`, `AGENTS.md`, `claude.md`, and `.claude/` are excluded from the generated site.
- `.claude/` is local tooling state and should remain untracked; do not stage Claude permission-history files.

## Active Plugins

`_config.yml` currently enables:

- `jekyll-seo-tag`
- `jekyll-sitemap`

Blog-related plugin configuration and dependency notes are preserved under
`_archive/legacy-template-features/blog/`.

## Known Drift To Watch

- `claude.md` is intentionally a thin pointer to this file, so agent instructions do not drift in two places.
- `README.md` is user-facing and may be higher level than the agent guide.
- `_archive/legacy-template-features/` is cold storage. Do not edit archived files as though they were active source; restore a complete feature package first.
- Default `bundle` may resolve to macOS system Ruby 2.6 unless rbenv 3.3.6 is first in `PATH`.

## Common Failure Points

- Empty `href` values can fail HTML Proofer.
- Unsupported project statuses can disappear from the homepage because `index.html` builds the grid from known status buckets.
- Broken asset extension references are easy to miss after image compression or rename; current home backgrounds use 1920/3840 AVIF and WebP derivatives with `bg-dark.jpg` / `bg-light.jpg` as compatibility fallbacks.
- If collection additions do not appear, check both `collections:` and `defaults:` in `_config.yml`.
