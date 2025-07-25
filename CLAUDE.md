# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

### Running the Hugo site locally
```bash
# Navigate to Hugo directory
cd hugo-site

# Serve the site locally
hugo server

# Build the site for production
hugo --minify

# Manual deploy to GitHub Pages (from hugo-site directory)
hugo --minify && cp -r public/* ../
cd .. && git add . && git commit -m "Update site" && git push

# Automatic deploy (just push changes)
# GitHub Actions will automatically build and deploy
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

The site features:
- Pure Tufte CSS typography with ET Book font
- Academic layout with sidenotes and margin notes
- Clean, professional design focused on readability
- Research focus on distributed systems, CRDTs, and peer-to-peer architectures
- Responsive design that works on mobile devices