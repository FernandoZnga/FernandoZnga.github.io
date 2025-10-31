# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

This is a **GitHub Pages personal resume/portfolio website** for Oscar Fernando Zuniga. The site is a modern, single-page application with custom CSS, dark/light theme toggle, and animated statistics, served directly from the master branch via GitHub Pages at `FernandoZnga.github.io`.

## Architecture

**Technology Stack:**
- Static HTML5 site (single `index.html` file - all CSS inline)
- Custom CSS with CSS variables for theming
- Vanilla JavaScript (no frameworks)
- Font Awesome 6 for icons
- Google Fonts (Inter, JetBrains Mono)
- GitHub API integration for live stats
- Jekyll theme configuration (`_config.yml`) for GitHub Pages

**Structure:**
```
├── index.html          # Main resume page (self-contained with inline CSS/JS)
├── _config.yml         # Jekyll configuration for GitHub Pages
├── favicon.ico         # Site favicon
├── README.md           # Project documentation
├── WARP.md            # This file
└── assets/
    └── images/        # Profile picture only
```

**Design Pattern:**
- Modern single-page scrolling design with sections
- Dark theme by default with light theme toggle
- Sticky header with navigation
- Animated statistics cards
- Responsive grid layouts throughout
- No external CSS/JS files - everything inline for performance

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

## Key Features

**Theme Toggle:**
- Light/Dark theme switcher (floating button on right side)
- Preference saved to localStorage
- CSS variables for easy customization
- Find theme colors in CSS `:root` and `[data-theme="light"]` blocks

**Animated Statistics:**
- 6 hero stat cards with counting animation (0 to target)
- Animation triggers on page load with staggered effect
- Counters use `data-target` attribute for values
- Update numbers in HTML (search for `data-target=`)

**GitHub Integration:**
- Auto-fetches public repository count from GitHub API
- Manual stats for total contributions (includes private repos)
- Current stats: 2,500+ commits, 300+ PRs, 500+ code reviews

**Sections:**
1. Hero with animated stats
2. About Me
3. Professional Experience (3 QA roles + Tigo history)
4. Featured Projects (5 GitHub projects)
5. Technical Skills (6 categories with progress bars)
6. Education
7. Contact

## Common Editing Tasks

**Update Statistics:**
- Search for `data-target="XXX"` in index.html
- Update hero stats around line 750-775
- Keep numbers realistic and impressive

**Update Resume Content:**
- All content is in `index.html` - edit HTML directly
- Profile information: hero section (~line 735)
- Contact details: contact section (~line 1356)
- Work experience: experience section (~line 858)
- Projects: projects section (~line 950)
- Skills: skills section (~line 1068)

**Update Colors/Theme:**
- Dark theme: `:root` CSS variables (~line 17)
- Light theme: `[data-theme="light"]` CSS variables (~line 33)
- Main variables: `--bg-primary`, `--accent-primary`, `--accent-gradient`

**Update Profile Picture:**
- Replace `assets/images/profile.jpg`
- Keep image square for best circular crop

## Key Considerations

- **Single-page architecture**: All content lives in one HTML file (~1500 lines)
- **Inline CSS/JS**: Everything embedded for performance and portability
- **GitHub Pages hosting**: Changes to master branch deploy automatically (1-2 min)
- **No build step required**: Pure static HTML/CSS/JS - just edit and push
- **No dependencies**: No npm, no build tools, no external CSS/JS files
- **Responsive design**: Custom CSS Grid and Flexbox (mobile-friendly)
- **API calls**: Only to GitHub API for public repo count (no auth needed)
- **localStorage**: Saves theme preference client-side

## Important Notes

**Manual Stats:**
- Commits, PRs, and Code Reviews are manually set (include private work)
- Only "GitHub Repos" count auto-updates from API
- Update these periodically to keep impressive

**Animation System:**
- Counter animations use Intersection Observer and setInterval
- All counters animate over 2 seconds with staggered start
- Theme toggle uses CSS transitions on CSS variables

**Contact Info:**
- Phone number removed for privacy
- Location changed to "Anywhere" for remote appeal
- Email uses @ icon instead of envelope
