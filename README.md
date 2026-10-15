# Vicente K. Pedreros Aballay — Portfolio

[![Jekyll](https://img.shields.io/badge/Jekyll-4.4-red.svg)](https://jekyllrb.com/)
[![Ruby](https://img.shields.io/badge/Ruby-3.3-red.svg)](https://www.ruby-lang.org/)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

Personal research portfolio focusing on cosmology, large-scale structure, and modified gravity, built with Jekyll and the Emergence design system.

🔗 **Live Site**: [vpedreros.github.io](https://vpedreros.github.io)

---

## Design Philosophy

Deep Glacier and Stellar Field are the light and dark environments—not
decorative backdrops. Both modes keep the same geometry while their optical
treatment changes with the photograph.

- **Field** — the Glacier or Stellar image establishes the environment
- **Plane** — a small number of optical surfaces protect navigation and reading
- **Trace** — thin horizons communicate selection, separation, and continuity
- **Point** — circular indicators are reserved for state, focus, and the theme
  control
- **Project type first** — research implementations and software systems remain
  the primary content structure

The Horizon Rail is therefore a low, long Plane with one active Trace; it is
not a generic pill. Glacier uses a near-white reading surface and charcoal
type; Stellar uses a near-black surface and off-white type. Both reserve one
muted blue-grey accent for links, active traces, focus, and the hero signature;
low-saturation status colors are the only semantic exception. Repeated projects
and related content are separated by rules rather than cards.

📖 See [`DESIGN.md`](DESIGN.md) for the full form contract and
[`ASSET-LICENSES.md`](ASSET-LICENSES.md) for photograph licensing.

---

## Project Structure

```
vpedreros.github.io/
├── _layouts/               # HTML templates
│   ├── base.html           # HTML shell (head, body)
│   ├── custom-page.html    # Tab pages layout
│   └── post.html           # Individual content pages
│
├── _includes/              # Reusable Liquid partials
│   ├── nav.html            # Shared navigation
│   └── project-card.html   # Project row renderer
│
├── _tabs/                  # Main navigation pages
│   └── about.md            # Pulls data from _data/profile.yml
│
├── _data/
│   ├── profile.yml         # Personal info (single source of truth)
│   ├── theme_dark.yml      # Dark mode design tokens
│   └── theme_light.yml     # Light mode design tokens
│
├── _projects/              # Project collection
├── _archive/               # Inactive, restorable template features
│
└── _sass/emergence/        # Custom design system (SCSS @use module system)
    ├── _variables.scss
    ├── _base.scss
    ├── _typography.scss
    ├── _components.scss
    ├── _navigation.scss
    └── pages/
```

---

## Quick Start

### Prerequisites

- Ruby 3.3.6 (via rbenv)
- Bundler

### Installation

```bash
git clone https://github.com/vPedreros/vpedreros.github.io.git
cd vpedreros.github.io
bundle install
LANG=en_US.UTF-8 bundle exec jekyll serve --livereload
```

Visit `http://localhost:4000`

---

## Adding Content

### Add a Project

Create `_projects/[project-name]/index.md`:

```yaml
---
title: "Project Title"
description: "Brief description"
categories: [Projects]
icon: fas fa-calculator
tags: ["Tag1", "Tag2"]
link: "#"
order: 1
status: planned   # planned | in-progress | completed
project_type: physics   # physics | software (ml reserved, no tab yet)
---
```

---

## Customization

### Personal Info

Edit `_data/profile.yml` — single source of truth for name, affiliation, social links, and research interests.

### Design Tokens

Edit `_data/theme_dark.yml` or `_data/theme_light.yml` — no SCSS knowledge required.

---

## Archived Template Features

Inactive Notes, Readings, blog, project filtering, Dev Container, theme-sync,
and legacy Chirpy asset features are kept under
[`_archive/legacy-template-features/`](_archive/legacy-template-features/) with
restoration instructions. They are excluded from the generated site.

---

## Tech Stack

| Category | Technology |
|----------|-----------|
| Generator | Jekyll 4.4 |
| Styling | SCSS (`@use` module system) |
| Icons | FontAwesome 6 |
| Hosting | GitHub Pages |
| Plugins | `jekyll-seo-tag`, `jekyll-sitemap` |

---

## Build & Deploy

```bash
# Local build
LANG=en_US.UTF-8 bundle exec jekyll build

# Deploy: push to main branch → GitHub Actions auto-deploys
git push origin main

# HTML validation
bundle exec htmlproofer _site --disable-external
```

---

## License

The site code is available under the [MIT License](LICENSE). The Deep Glacier,
Stellar Field, and composite preview images have separate terms documented in
[`ASSET-LICENSES.md`](ASSET-LICENSES.md).
