# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll-based blog using the Architect theme. The site is structured as a GitHub Pages site with blog posts, pages, and a custom theme. Content is written in Markdown and compiled to static HTML.

## Key Directories and Files

- `_posts/` - Blog posts in Markdown format with date prefixes
- `_layouts/` - HTML templates for page structure
- `_includes/` - Reusable HTML components
- `_sass/` - Sass stylesheets for the theme
- `assets/` - CSS, images, and other static assets
- `_config.yml` - Jekyll configuration
- `index.md` - Main page content
- `001-tools/`, `002-edu.md`, etc. - Content sections

## Development Commands

### Local Development
```bash
# Start local development server with live reload
./run.sh
# or
bundle exec jekyll serve --trace --incremental

# Build site locally
bundle exec jekyll build
```

### Setup
```bash
# Install dependencies
./script/bootstrap
# or
gem install bundler && bundle install
```

### Testing
```bash
# Run full test suite
./script/cibuild
# or individually:
bundle exec jekyll build
bundle exec htmlproofer ./_site --check-html --check-sri
bundle exec rubocop -D --config .rubocop.yml
bundle exec script/validate-html
gem build jekyll-theme-architect.gemspec
```

## Workflow

1. Write content in Markdown files
2. Use `./run.sh` for local preview
3. Test with `./script/cibuild` before committing
4. Site automatically builds on GitHub Pages

## Architecture Notes

- Uses Jekyll with the Architect theme
- Responsive design with mobile support
- SEO optimized with jekyll-seo-tag
- Sass-based styling system
- GitHub Pages deployment ready
- Structured content with categories in sidebar