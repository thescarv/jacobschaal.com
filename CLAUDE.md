# Project Memory — Jacob Schaal Personal Website

## Project Purpose
Personal academic/policy website for Jacob Schaal. Pure static HTML/CSS/JS. No build step. Deployed to GitHub Pages.

## Architecture
- `index.html` — Homepage (hero, affiliations, featured-in, selected writing, media, talks, newsletter)
- `writing/index.html` — Full publications list
- `about/index.html` — Extended bio
- `css/` — Design tokens, base styles, components, responsive
- `js/main.js` — Mobile nav, smooth scroll
- `assets/logos/` — SVG logos

## Design System
- Fonts: Newsreader (headings), DM Sans (body) — Google Fonts
- Colours: warm white #FAFAF8, dark text #1a1a1a, accent #3d5a80
- Spacing: 8px base scale
- Breakpoints: 1024px (desktop), 768px (tablet), 480px (mobile)

## Content Updates
All content lives directly in the HTML. There is no data layer.
- To add a publication: copy an existing `writing-item` block in `writing/index.html` (and `index.html` if it should be featured)
- To add a logo: drop an SVG in `assets/logos/` (lowercase filename) and reference it from the HTML; without a logo, use a visible `logo-bar__text` span
- Contact email is set via `data-name` / `data-domain` on `.js-email` links (home and About pages)
- Use canonical URLs, never personal gift/share links (e.g. Bloomberg `accessToken`, `substack.com/home/post/...`)

## Conventions
- BEM-style CSS class naming
- Semantic HTML (section, nav, article, footer)
- No external JS dependencies
- CSS custom properties for all design tokens
- Mobile-first responsive considerations

## Known Pitfalls
- SSRN 5516798 is Klein Teeselink (2025), not Jacob's paper; the Moravec index is arXiv 2510.13369
- Keep logo filenames lowercase; mixed-case duplicates break on case-insensitive checkouts
