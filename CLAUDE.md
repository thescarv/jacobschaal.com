# Project Memory — Jacob Schaal Personal Website

## Project Purpose
Personal academic/policy website for Jacob Schaal. Pure HTML/CSS/JS with JSON data layer. No build step. Deployed to GitHub Pages.

## Architecture
- `index.html` — Homepage with 9 scrollable sections
- `writing/index.html` — Full publications list
- `about/index.html` — Extended bio
- `data/content.json` — All structured content (publications, talks, media, affiliations)
- `css/` — Design tokens, base styles, components, responsive
- `js/main.js` — JSON renderer, mobile nav, smooth scroll
- `assets/logos/` — SVG placeholder logos (swap for real ones later)

## Design System
- Fonts: Newsreader (headings), DM Sans (body) — Google Fonts
- Colours: warm white #FAFAF8, dark text #1a1a1a, accent #3d5a80
- Spacing: 8px base scale
- Breakpoints: 1024px (desktop), 768px (tablet), 480px (mobile)

## Content Updates
To add a publication: edit `data/content.json` → add object to relevant array
To add a logo: drop SVG in `assets/logos/`, reference filename in `content.json`
Every external URL should have both `url` and `archiveUrl` (Perma.cc) fields

## Conventions
- BEM-style CSS class naming
- Semantic HTML (section, nav, article, footer)
- No external JS dependencies
- CSS custom properties for all design tokens
- Mobile-first responsive considerations

## Known Pitfalls
<!-- Add corrections here as encountered -->
