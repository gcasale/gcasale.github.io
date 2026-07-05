# Giuliano Casale - Personal Page (Static Copy)

A self-contained static mirror of the personal homepage of **Giuliano Casale**,
Department of Computing, Imperial College London, originally at
<https://wp.doc.ic.ac.uk/gcasale/> (a WordPress site).

All internal links, stylesheets, scripts and images have been localized so the
site runs as plain static files - no PHP, database or WordPress runtime
required. It is ready to deploy on GitHub Pages.

## Contents

| Path | Page |
|------|------|
| `index.html` | Home |
| `research/` | Research |
| `recent-talks/` | Talks |
| `fun-and-miscellanea/` | Misc |
| `wp-content/`, `wp-includes/` | Theme CSS/JS, images, slide PDFs and other assets |

External navigation links (the QORE group site, the YouTube videos playlist, the
`imperial-qore` GitHub, the CV PDF on `www.doc.ic.ac.uk`, Imperial College,
Google Fonts, and the footer *Login*) intentionally still point to their live
locations.

## Colour palette / branding

The theme was rebranded to the current Imperial visual identity, matching the
QORE static site:

- The header wordmark is the current Imperial SVG logo
  (`wp-content/themes/ic-doc-default/library/images/imperial-logo.svg`),
  replacing the previous raster `logo_imperial_college_london.png`.
- The brand accent colour was changed from the old WordPress teal `#1e8cbe`
  to **Imperial Blue `#0000cd`** throughout
  `wp-content/themes/ic-doc-default-simple/style.css`.

## What was changed vs. the live site

- The theme's PHP-generated stylesheets (`style.php`, `style-custom.php`) were
  fetched and saved as static `style.css` / `style-custom.css`.
- Absolute `https://wp.doc.ic.ac.uk/gcasale/...` URLs were converted to relative
  paths; PHP short-links resolve to their static `index.html` pages.
- Dead WordPress `<head>` metadata (pingback, RSS, iCal, oEmbed, canonical,
  shortlink, Tribe Events API) was stripped.
- The defunct social-share widget (Delicious / Digg / StumbleUpon / iMedia
  share) was removed.

## Run locally

```bash
python3 -m http.server 8000
# then open http://localhost:8000/
```

(Open via a web server, not `file://`, so the pretty directory URLs resolve.)

## Deploy on GitHub Pages (user site)

This is intended to be published as a **GitHub user site** served at
`https://<username>.github.io/`. The repository must be named
**`<username>.github.io`**.

When ready to publish (not done yet):

```bash
git remote add origin git@github.com:<username>/<username>.github.io.git
git push -u origin master        # or: git branch -M main && git push -u origin main
```

Then in *Settings -> Pages* set **Source = Deploy from a branch**, branch
`master` (or `main`), folder `/ (root)`.

The `.nojekyll` file disables Jekyll processing so all files are served
verbatim.
