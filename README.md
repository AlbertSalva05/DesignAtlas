# Design Atlas

A static UI/UX resource hub: HTML, JS and one JSON catalog. No build step. Render serves this folder as it is.

## Files

```
├── index.html             the whole site
├── ResourceCard.dc.html   card component, loaded by index.html
├── support.js             runtime (do not edit)
├── data/
│   └── atlas-data.json    catalog: resources, categories, collections, site settings
├── assets/
│   ├── favicon/           favicon.svg, favicon-32.png, apple-touch-icon.png,
│   │                      icon-192.png, icon-512.png, icon-maskable-512.png
│   └── og-image.png       1200×630 social sharing image
├── favicon.ico            16/32/48 px, for browsers that request /favicon.ico
├── site.webmanifest       install name, colours and icons (light theme)
├── robots.txt
├── sitemap.xml
└── render.yaml            Render static hosting and headers config
```

## Updating the catalog
1. Edit in **Manage** on the live site (changes save to that browser only).
2. **Manage → JSON editor → Export** downloads `atlas-data.json`.
3. Replace `data/atlas-data.json`, commit and push.

## Theme
Light is always the default. The site ignores the device's dark-mode setting; dark and high contrast only apply when a visitor picks them in the header or Settings, and that choice is saved in their browser.

## Before launch
- Replace `https://design-atlas.onrender.com` with the real domain in `index.html` (canonical, og:url, og:image and the `SITE` constant), `robots.txt` and `sitemap.xml`.
- Get the Privacy and Terms pages reviewed by a qualified person.
- Check each Commercial use value against the source licence.
- Connect the contact, newsletter and submit forms to a form service.
- Protect `#/manage`: it has no login.
