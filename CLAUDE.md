# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll-based personal academic website for Xiao Bowen. The site is built using the Minimal Mistakes theme and hosted on GitHub Pages at https://Bowie375.github.io. It serves as an academic portfolio showcasing publications, CV, and research work.

## Technology Stack

- **Static Site Generator**: Jekyll with Minimal Mistakes theme
- **Markup**: Markdown (kramdown parser)
- **Styling**: Sass/SCSS
- **Build Tool**: Ruby Bundler for dependency management
- **Auxiliary Scripts**: Python (Jupyter notebooks and scripts for publishing workflows)

## Project Structure

```
.
├── _config.yml                      # Main Jekyll configuration
├── _config.dev.yml                  # Development-specific overrides
├── _pages/                          # Main page content (about.md, publications.md, etc.)
├── _layouts/                        # HTML/Liquid layout templates (single.html, talk.html, etc.)
├── _includes/                       # Reusable template components (archive-single-publication.html, etc.)
├── _publications/                   # Individual publication markdown files (named by date: YYYYMMDD-slug.md)
├── _posts/                          # Blog posts (optional, currently minimal)
├── _talks/                          # Talk/presentation entries
├── _teaching/                       # Teaching-related content
├── _portfolio/                      # Portfolio projects
├── _data/                           # Configuration data (navigation.yml, authors.yml, ui-text.yml)
├── _sass/                           # Sass stylesheets
├── assets/                          # JS, CSS, images
├── images/                          # Image assets
├── files/                           # Static files (resume.pdf, etc.)
├── markdown_generator/              # Python/Jupyter scripts for batch-generating publication markdown
├── _site/                           # Build output (gitignored)
├── Gemfile / Gemfile.lock           # Ruby dependencies
└── package.json                     # NPM scripts for asset minification
```

## Common Development Commands

### Local Development

```bash
# Install Ruby dependencies
bundle install

# Start Jekyll development server with live reload
bundle exec jekyll serve

# Start with incremental build (faster for development)
bundle exec jekyll serve --incremental

# Build static site to _site/ directory
bundle exec jekyll build

# Clean build output and rebuild
bundle exec jekyll clean && bundle exec jekyll build
```

### Content Workflow

- **Add Publication**: Create new markdown file in `_publications/` with filename format `YYYYMMDD-slug.md`. See existing files for YAML frontmatter structure (collection, permalink, title, authors, venue, date, citation, paper_url, code_url, etc.).

- **Modify About Page**: Edit `_pages/about.md`. Content is rendered into `single.html` layout via `{{ content }}` Liquid tag.

- **Update Navigation**: Modify `_data/navigation.yml` to add/remove nav links.

- **Batch Publication Generation**: Use Jupyter notebooks in `markdown_generator/` (publications.ipynb, PubsFromBib.ipynb, talks.ipynb) to convert TSV data into markdown files. Python equivalents available (.py files).

### Asset Management

```bash
# Minify and watch JavaScript
npm run build:js
npm run watch:js
```

## Jekyll Architecture & Key Concepts

The site uses a **content + layout** pattern:

1. **Content Files** (_pages/, _publications/, _posts/, etc.) are written in Markdown with YAML frontmatter
2. **Frontmatter** specifies which **layout** to use (e.g., `layout: single`, `layout: talk`)
3. **Layout files** (_layouts/single.html, _layouts/talk.html) are HTML/Liquid templates that include the `{{ content }}` variable where markdown is rendered
4. **Includes** (_includes/) are reusable template fragments included via `{% include filename.html %}` in layouts or content

### Collection Defaults (from _config.yml)

- `_publications/` → `single.html` layout + author profile
- `_posts/` → `single.html` layout + comments + social share
- `_talks/` → `talk.html` layout
- `_teaching/` → `single.html` layout
- `_portfolio/` → `single.html` layout

## Key Files and Their Purposes

- **_config.yml**: Site title, author info (name, bio, email, GitHub, Google Scholar, ORCID), social links, collection definitions, plugin settings
- **_pages/about.md**: Homepage content; edit here to change main page text
- **_pages/publications.md**: Publications listing page (includes publication items via Liquid loops)
- **_data/navigation.yml**: Top navigation links (Publications, CV, etc.)
- **_layouts/single.html**: Most common layout; includes author sidebar and main content area
- **_includes/archive-single-publication.html**: Template for rendering individual publication entries
- **markdown_generator/publications.tsv**: Tab-separated data for batch publication generation

## Styling & Customization

- Global styles in `_sass/` (compiled to CSS at build time)
- Theme configuration: `_config.yml` has color and layout settings
- Development server enables live CSS reload when `.scss` files change

## Deployment

The site is hosted on GitHub Pages and deploys automatically on push to master branch. The generated `_site/` directory is what GitHub Pages serves.

## Notes on Recent Changes

The repository has recent modifications to publication organization (files now use date-prefixed naming: `20250711-robohanger.md`, `20260121-foldnet.md`) and personal info updates. When adding publications, ensure YAML frontmatter includes all required fields: collection, permalink, title, authors, date, venue, status, paper_url, excerpt, and citation.

