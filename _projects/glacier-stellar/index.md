---
title: "Portfolio Design System"
description: "Open-source Jekyll design system with Glacier light and Galaxy dark environments, reusable presets, and tokenized components."
tags: ["Jekyll", "SCSS", "Open Source", "Design System"]
link: "https://github.com/sungmin-park-dev/glacier-stellar"
github_repo: "sungmin-park-dev/glacier-stellar"
permalink: /projects/glacier-stellar/
order: 5
status: completed
project_type: software
published: false
---

## Overview

This is an open-source Jekyll design system, extracted and anonymized from
this portfolio and published as
[`sungmin-park-dev/glacier-stellar`](https://github.com/sungmin-park-dev/glacier-stellar).
It ships an image-led **Glacier** (light) and **Galaxy** (dark) preset, ready
to clone and preview immediately.

## Features

- Glacier light and Galaxy dark environments with a persistent runtime toggle
- Responsive AVIF and WebP background assets with JPEG compatibility fallbacks
- Shared Field / Plane / Trace / Point grammar across navigation, reading surfaces, and controls
- Projects grouped by `project_type`, with optional Notes and Readings collections
- YAML theme data, CSS custom properties, modular SCSS, and portable token exports
- Jekyll 4 with no theme-gem dependency, deployed through GitHub Actions

## Design Concepts

- **Landscape for identity, content for attention** — imagery establishes the environment while restrained surfaces keep the work legible
- Glacier and Galaxy share one information structure while retaining independent optical treatment
- Planes exist only where reading contrast or functional grouping requires them; Trace and spacing handle lighter separation
- The Horizon Rail navigation and Point-like theme control describe location and environment without obscuring the photographs
- Focus visibility, reduced-motion behavior, and explicit theme-toggle labels are part of the component contract

## Links

- [GitHub Repository](https://github.com/sungmin-park-dev/glacier-stellar)
- [Live Demo](https://sungmin-park-dev.github.io/glacier-stellar/)
- [Design System](https://github.com/sungmin-park-dev/glacier-stellar/blob/main/DESIGN.md)
- [Glacier / Galaxy Preset](https://github.com/sungmin-park-dev/glacier-stellar/tree/main/presets/glacier-stellar)
