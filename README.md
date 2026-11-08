# Design Atlas

A static UI/UX resource hub: 190 design resources, each listed with its creator, price and licence.
Temporary address: https://design-atlas.onrender.com/ (replace before launch)

Static site in plain HTML, CSS and JavaScript. No framework and no third-party CDN at runtime: fonts, icons and the small page renderer ship in `assets/`. No build step needed to host it.

## Pages
- `index.html`: the whole site as hash routes (home, explore, resource plates, collections, shortlist, settings, submit, about, privacy, terms, manage)
- `404.html`: not-found page (noindex)

## Files
| Path | What it is |
|---|---|
| `index.html` | Page markup (pure HTML; links the CSS and JS below) |
| `assets/css/app.css` | All styles: fonts, themes, components |
| `assets/js/dc-lite.js` | Template renderer (no framework) |
| `assets/js/tpl-index.js` | Page templates |
| `assets/js/app.js` | Page logic |
| `assets/fonts/` | Source Sans 3 and Source Serif 4 (woff2, self-hosted) |
| `assets/vendor/phosphor/` | Phosphor Icons 2.1.1 (CSS + woff2/woff) |
| `data/atlas-data.json` | Catalog: resources, categories, collections, site settings |
| `assets/icons/` | Favicon set: SVG mark, 32 px PNG, Apple touch icon, 192/512 and maskable icons |
| `assets/og-image.png` | 1200×630 social sharing image |
| `favicon.ico` | 16/32/48 px icon for older browsers |
| `robots.txt`, `sitemap.xml`, `site.webmanifest` | Crawling, indexing and install metadata |
| `render.yaml` | Render static-site config: security and cache headers |
| `.gitignore`, `.gitattributes` | Git rules (images marked binary) |

## Theme
Light is always the default. Dark and high contrast apply only when a visitor picks them; the choice is saved in their browser.

## Updating the catalog
1. Edit in **Manage** on the live site (changes save to that browser only).
2. **Manage → JSON editor → Export** downloads `atlas-data.json`.
3. Replace `data/atlas-data.json`, commit and push.

## Third-party
Shipped in `assets/`: Phosphor Icons 2.1.1 (MIT), Source Sans 3 and Source Serif 4 (SIL OFL). Loaded at runtime: wsrv.nl image proxy and Google favicon service for resource previews.

## Deploy (Render)
1. Delete the old files in the repo first (including `assets/`), then copy this folder in.
2. Push with Git or GitHub Desktop (not web drag-and-drop).
3. Render, `design-atlas`: Manual Deploy, then "Clear build cache & deploy".
4. Hard refresh (Ctrl+Shift+R).

Build tag: `<meta name="da-build">` in `index.html` and `?v=` on every CSS/JS link.

If the domain changes, replace `https://design-atlas.onrender.com` in `index.html` (canonical, og:url, og:image and the `SITE` constant), `sitemap.xml` and `robots.txt`.

## Before launch
- Get the Privacy and Terms pages reviewed by a qualified person.
- Check each Commercial use value against the source licence.
- Connect the contact, newsletter and submit forms to a form service.
- Protect `#/manage`: it has no login.
