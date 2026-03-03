# Jacob Schaal — Personal Website

Personal academic/policy website. Pure HTML/CSS/JS with a JSON data layer. No build step required.

## Quick Start

Open `index.html` in a browser. For local development with proper path resolution, use a local server:

```bash
# Python
python -m http.server 8000

# Node.js (npx)
npx serve .
```

Then visit `http://localhost:8000`.

## File Structure

```
├── index.html              # Homepage
├── writing/index.html      # Full publications list
├── about/index.html        # Extended bio
├── css/
│   ├── tokens.css          # Design tokens (colours, fonts, spacing)
│   ├── base.css            # Reset, typography, global styles
│   ├── components.css      # All component styles
│   └── responsive.css      # Mobile/tablet breakpoints
├── js/main.js              # Renders content from JSON, handles interactions
├── data/content.json       # ALL structured content lives here
└── assets/
    ├── logos/              # Institutional/outlet logos (SVG/PNG)
    └── photo/              # Headshot
```

## How to Update Content

All content is in `data/content.json`. Edit this file to update publications, talks, media, affiliations, etc.

### Add a new publication

Add an object to `selectedWriting` (for homepage) and/or the appropriate category in `allWriting`:

```json
{
  "title": "Your Article Title",
  "venue": "Publication Name",
  "type": "Op-Ed",
  "date": "2026",
  "url": "https://example.com/article",
  "archiveUrl": "https://perma.cc/XXXX-XXXX",
  "description": "One-line description.",
  "coAuthors": "A. Co-Author"
}
```

Valid `type` values: `Op-Ed`, `Policy Analysis`, `Policy Brief`, `Policy Contribution`, `Standards Work`, `Newsletter`, `Report`, `Working Paper`, `Thesis`, `Research in Progress`

### Add a talk

Add to the `talks` array:

```json
{
  "event": "Conference Name",
  "location": "City",
  "date": "2026",
  "description": "Brief description."
}
```

### Add a media mention

Add to the `media` array:

```json
{
  "outlet": "Outlet Name",
  "headline": "Article headline or description",
  "date": "2026",
  "url": "https://example.com",
  "archiveUrl": "https://perma.cc/XXXX-XXXX",
  "logo": "outlet-name.svg"
}
```

### Update affiliations

Edit the `affiliations` array. Each entry has `institution`, `role`, `period`, `logo`, and `url`.

### Update social links

Edit the `social` array. Supported icons: `linkedin`, `twitter`, `substack`, `scholar`.

## How to Add a Real Logo

1. Place the SVG or PNG in `assets/logos/`
2. Name it to match the filename in `content.json` (e.g., `faz.svg`)
3. The placeholder text logo will be replaced automatically

For best results, use SVG logos at consistent heights (~40px). The CSS applies a greyscale filter with colour on hover.

## Perma.cc Workflow

For every external URL, create a permanent archive:

1. Go to https://perma.cc/manage/create/?folder=331553
2. Paste the URL and create the archive
3. Copy the Perma.cc link
4. Add it as `archiveUrl` in `content.json`

## Deployment

### GitHub Pages

1. Push to a GitHub repository
2. Go to Settings > Pages
3. Set source to "Deploy from a branch" > `main` > `/ (root)`
4. The site will be live at `https://username.github.io/repo-name/`

### Custom Domain

1. Add a `CNAME` file with your domain (e.g., `jacobschaal.com`)
2. Configure DNS with your domain registrar
3. Enable HTTPS in GitHub Pages settings

## Design System

- **Fonts:** Newsreader (headings), DM Sans (body) via Google Fonts
- **Colours:** Warm white `#FAFAF8`, dark text `#1a1a1a`, steel blue accent `#3d5a80`
- **All tokens** are CSS custom properties in `css/tokens.css`
