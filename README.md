# buyNmore — Corporate Website

Static marketing site for buyNmore, a food & beverage distribution group operating in Egypt (buyNmore) and Germany (buyNmore GmbH).

## Overview

Single-page site with client-side routing (hash-based) covering:
Home · About · Services · Locations · Country pages (Egypt, Germany) · Brands directory · Contact.

## Technology

- One self-contained `index.html` — all markup, styles, scripts and images are inlined.
- No framework install, no build step, no backend, no environment variables.
- Fonts: Nunito and Montserrat, loaded from Google Fonts at runtime (the only external request).

## Project structure

```
buynmore-site/
├── index.html      # the complete site
├── README.md
└── .gitignore
```

## Run locally

Open `index.html` in any modern browser, or serve the folder:

```
npx serve .
```

## Deploy

**Vercel:** import the repository → Framework preset “Other” → no build command → output directory `.` (root).

**Netlify:** New site from Git → leave the build command empty → publish directory `.` (root).

Both detect the static `index.html` automatically.

## Contact form

There is no backend. The “Send message” button opens the visitor’s email client (`mailto:`) with the form content pre-filled, routed to `info@buynmore.net` (Egypt) or `germany@buynmore.net` (Germany). To collect submissions server-side, connect a form service (e.g. Netlify Forms, Formspree) and replace the `mailto:` handler.

## Security notes

- No credentials, API keys or tokens exist in this project.
- Form inputs are length-limited and line-breaks stripped before being placed in the `mailto:` URL; everything is URL-encoded.
- Remaining consideration: `mailto:` depends on the visitor having a mail client configured. Use a form service for reliable lead capture.

## Editing content

The site is generated from a design source (`buyNmore Website.dc.html` in the design project). Edit there and re-export rather than editing `index.html` by hand.

## Upload to GitHub

```
cd buynmore-site
git init
git add .
git commit -m "Initial buyNmore website"
git branch -M main
git remote add origin https://github.com/<your-org>/buynmore-website.git
git push -u origin main
```
