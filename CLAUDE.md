# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

### Running the Hugo site locally
```bash
# Navigate to Hugo directory
cd hugo-site

# Serve the site locally with live reload
hugo server

# Build the site for production
hugo --minify

# Manual deploy to GitHub Pages (from hugo-site directory)
hugo --minify && cp -r public/* ../
cd .. && git add . && git commit -m "Update site" && git push

# Automatic deploy (just push changes)
# GitHub Actions will automatically build and deploy when pushing to main
```

## Architecture

This is a Hugo-based academic personal website for Abel Dantas using pure Tufte CSS for elegant typography. The site structure:

- **hugo-site/**: Hugo project directory
  - **layouts/**: Custom templates
    - **_default/baseof.html**: Base template with Tufte CSS
    - **index.html**: Homepage template
  - **static/**: Static assets (images, CSS)
  - **hugo.toml**: Hugo configuration
- **Root directory**: Contains built static files for GitHub Pages
- **.github/workflows/hugo.yml**: Automated deployment workflow

The site features:
- Pure Tufte CSS typography with ET Book font
- Academic layout with sidenotes and margin notes
- Clean, professional design focused on readability
- Research focus on distributed systems, CRDTs, and peer-to-peer architectures
- Responsive design that works on mobile devices

## Deployment

GitHub Actions automatically builds and deploys the site when changes are pushed to the main branch. The workflow:
1. Builds Hugo site with `hugo --minify` in the hugo-site directory
2. Copies built files from hugo-site/public/ to the root directory
3. Deploys to GitHub Pages at https://abeldantas.github.io/web/

## Git Commit Message Guidelines

When making commits in this repository:
- Write commit messages in imperative mood (e.g., "Add feature" not "Added feature")
- Keep messages simple and concise
- Focus on providing context for the change
- DO NOT use prefixes like `feat:`, `fix:`, `docs:`, etc.
- DO NOT add Claude Code signatures or co-author lines
- Good examples: "Update bio section", "Add research publications", "Fix broken link in navigation"