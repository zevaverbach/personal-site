# Personal Site - Static Files

This directory contains the generated static files for the personal website hosted on Netlify.

## Overview

This is the **output directory** for the custom static site generator located in `../zev.averba.ch/blargh/`. The files in `public/` are automatically generated and should not be edited directly.

## How It Works

### File Generation
- **Source**: Content and templates are stored in `../zev.averba.ch/blargh/`
- **Generator**: Custom Python application using Jinja2 and Mistune
- **Output**: Generated HTML and assets are placed in `public/`

### Deployment Process
1. **Build**: Run `uv run blargh/application.py` from `../zev.averba.ch/`
2. **Generated files**: Static HTML, CSS, and assets are created in `public/`
3. **Deploy**: Netlify automatically deploys when changes are pushed to the repository

### Netlify Configuration
- **Config file**: `netlify.toml` specifies `public/` as the publish directory
- **Auto-deployment**: Enabled for the main branch
- **Build**: No build command needed on Netlify (files are pre-generated locally)

## Directory Structure

```
personal-site/
├── README.md           # This file
├── netlify.toml        # Netlify deployment configuration
└── public/             # Generated static files (served by Netlify)
    ├── *.html          # Generated HTML pages
    ├── robots.txt      # SEO configuration
    └── static/         # Assets (CSS, fonts, images)
```

## Important Notes

- **Do not edit files in `public/`** - They will be overwritten on the next build
- **Make content changes** in `../zev.averba.ch/blargh/pages/` or `../zev.averba.ch/blargh/projects/`
- **CSS changes** should be made in `../zev.averba.ch/blargh/static/style.css`
- **Template changes** should be made in `../zev.averba.ch/blargh/templates/`

## Making Changes

To update the website:

1. Navigate to the generator directory:
   ```bash
   cd ../zev.averba.ch
   ```

2. Make your content changes in:
   - `blargh/pages/` for blog posts
   - `blargh/projects/` for project descriptions
   - `blargh/templates/` for layout changes
   - `blargh/static/` for CSS/asset changes

3. Rebuild the site:
   ```bash
   uv run blargh/application.py
   ```

4. Commit and push changes:
   ```bash
   git add .
   git commit -m "Update website content"
   git push origin main
   ```

5. Netlify will automatically deploy the updated `public/` directory

## Local Development

For local development with proper navigation:
```bash
cd ../zev.averba.ch
uv run blargh/application.py --local
```

This adds `.html` extensions to internal links for local file browsing.