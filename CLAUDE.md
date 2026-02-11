# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal blog at [varunj.com](https://varunj.com), built with Hugo (v0.155+) and the [Shibui](https://github.com/ntk148v/shibui) theme. Deployed to GitHub Pages via GitHub Actions on every push to `main`.

## Common Commands

```bash
# Run local dev server with live reload and draft content
hugo server -D

# Build the site (output to public/)
hugo

# Create a new blog post
hugo new content content/posts/my-post.md
```

## Writing a New Post

Create a markdown file in `content/posts/` with this front matter:

```markdown
---
title: "Post Title"
date: 2026-02-11
tags: ["tag1", "tag2"]
---

Content here.
```

Commit and push to `main` — the GitHub Actions workflow handles the rest.

## Architecture

- `hugo.toml` — Site configuration (base URL, title, theme, menus, markup settings)
- `content/` — Markdown content (posts live in `content/posts/`)
- `content/about.md` — About page
- `static/CNAME` — Custom domain file for GitHub Pages
- `.github/workflows/hugo.yml` — GitHub Actions workflow for build and deploy
- `themes/shibui/` — Theme (git submodule, do not edit directly)
- `archetypes/` — Templates for `hugo new` (default uses TOML front matter with `+++`)
- `layouts/` — HTML template overrides (empty; override theme templates here if needed)
- `static/` — Files copied as-is to the built site
- `assets/` — Files processed by Hugo Pipes (SCSS, JS bundling, etc.)

## Deployment

- **Host:** GitHub Pages
- **Domain:** varunj.com (DNS via GoDaddy, A records pointing to GitHub Pages IPs)
- **Build:** Automatic on push to `main` via `.github/workflows/hugo.yml`
- **Theme:** Shibui, installed as a git submodule at `themes/shibui`
