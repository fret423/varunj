# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Hugo static site (v0.155+). It was scaffolded with `hugo new site` and is currently a blank project with no theme or content yet.

## Common Commands

```bash
# Run local dev server with live reload and draft content
hugo server -D

# Build the site (output to public/)
hugo

# Create a new content page
hugo new content content/posts/my-post.md
```

## Architecture

Standard Hugo directory layout:

- `hugo.toml` — Site configuration (base URL, title, language)
- `archetypes/` — Templates for `hugo new` (default archetype uses TOML front matter with `+++`)
- `content/` — Markdown content pages
- `layouts/` — HTML templates (overrides theme templates)
- `themes/` — Hugo themes (currently empty; a theme must be added before the site will render)
- `static/` — Files copied as-is to the built site
- `assets/` — Files processed by Hugo Pipes (SCSS, JS bundling, etc.)
- `data/` — Supplemental data files (JSON, TOML, YAML)
- `i18n/` — Translation strings for multilingual support

## Setup Note

A theme must be installed before the site can be built or served. Typical approach:

```bash
git submodule add https://github.com/<user>/<theme>.git themes/<theme>
```

Then set `theme = '<theme>'` in `hugo.toml`.
