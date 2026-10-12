# PHCCO website

This repository contains the Jekyll website for the Param Hansa Centre for Computational Oncology. It follows the page-oriented structure of `sarthak-sahoo-0710.github.io` and adds data-driven faculty, student, and collaboration profiles.

## Edit people and collaborations

- `_data/people.yml` stores profile details, research interests, recognitions, grants, and advising records.
- `_data/collaborations.yml` defines Mohit Kumar Jolly's pairwise collaboration pages.
- `_data/joint_publications.yml` stores joint publications grouped by collaborator; the layouts group them by year automatically.
- `_data/research_themes.yml` provides the four illustrated research themes.
- `_pages/faculty/`, `_pages/students/`, and `_pages/collaborations/` contain the public profile routes.

The collaboration map is a responsive equirectangular SVG generated from Natural Earth public-domain geometry. Faculty marker positions live in `_data/people.yml`. Theme artwork lives in `assets/images/research/`.

Only add grants, advising relationships, contact details, and recognitions when an authoritative source is available. Publication entries should include a DOI whenever possible.

## Add or edit a page

The home page lives in `index.md`; additional pages live in `_pages/`. Each page begins with front matter:

```yaml
---
layout: page
title: Example page
permalink: /example/
nav: true
nav_order: 5
description: A short description of this page.
---
```

Write the page content below the second `---` using Markdown or HTML. Set `nav: true` to show it in the main navigation and use `nav_order` to control its position.

Shared HTML is in `_layouts/` and `_includes/`. Global colors and layout rules are in `assets/css/main.scss`. Site-wide settings, including the GitHub Pages base URL, are in `_config.yml`.

## Run locally

```bash
bundle exec jekyll serve
```

The production site is built and deployed by the Pages workflow in `.github/workflows/pages.yml` whenever `main` is updated.
