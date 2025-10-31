# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

This is a **GitHub Pages personal resume/portfolio website** for Oscar Fernando Zuniga. The site is a static HTML/CSS/JavaScript page built with Bootstrap and Font Awesome, served directly from the master branch via GitHub Pages at `FernandoZnga.github.io`.

## Architecture

**Technology Stack:**
- Static HTML5 site (single `index.html` file)
- Bootstrap 3 for responsive layout
- Font Awesome for icons
- jQuery 1.11.3 for DOM manipulation
- Jekyll theme configuration (`_config.yml`) for GitHub Pages

**Structure:**
```
├── index.html          # Main resume page (single-page application)
├── _config.yml         # Jekyll configuration for GitHub Pages
├── favicon.ico         # Site favicon
├── assets/
│   ├── css/           # Bootstrap and custom styles
│   ├── images/        # Profile picture and other images
│   ├── js/            # Custom JavaScript
│   ├── less/          # LESS source files
│   └── plugins/       # Bootstrap, Font Awesome, jQuery
```

**Layout Pattern:**
- Two-column responsive design: `.sidebar-wrapper` (left) and `.main-wrapper` (right)
- Sidebar contains: profile, contact info, education, languages, and interests
- Main section contains: career profile, work experiences, aptitudes, and skills

## Development Commands

### Local Development
```bash
# Serve locally with Jekyll (if installed)
jekyll serve

# Or use Python's simple HTTP server
python -m http.server 8000
# Then open http://localhost:8000
```

### Deployment
**Deployment is automatic.** Changes pushed to the `master` branch are automatically published to GitHub Pages within 1-2 minutes.

```bash
# Standard git workflow
git add .
git commit -m "Description of changes"
git push origin master
```

### View Live Site
https://fernandoznga.github.io

## Common Editing Tasks

**Update Resume Content:**
- All content is in `index.html` - edit HTML directly
- Profile information: lines 31-34
- Contact details: lines 37-46
- Education: lines 47-59
- Work experience: lines 91-184
- Skills: lines 202-315

**Update Styles:**
- Main stylesheet: `assets/css/styles-6.css`
- LESS source files in `assets/less/` (if you want to modify and recompile)

**Update Profile Picture:**
- Replace `assets/images/profile.jpg`

## Key Considerations

- **Single-page architecture**: All content lives in one HTML file
- **GitHub Pages hosting**: Changes to master branch deploy automatically
- **No build step required**: Pure static HTML/CSS/JS
- **Bootstrap 3**: Older version, be aware of deprecated features when modernizing
- **Responsive design**: Already mobile-friendly via Bootstrap grid

## Content Sections

When editing, maintain these structural sections:
1. **Sidebar**: Profile, Contact, Education, Languages, Interests
2. **Main**: Career Profile, Experiences (chronological), Aptitudes, Skills (with progress bars)
