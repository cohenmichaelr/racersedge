# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Context

The Racer's Edge is a marketing site for a high-end bike shop in Boca Raton, FL. The desired vibe is clean, premium, and athletic: dark mode UI with "Electric Blue" (`#007FFF`) accents, mobile-first layouts (target audience checks the site from their phone), and copy that reads elite/professional/athletic rather than generic retail.

## Tech Stack / Tooling

Static HTML only — there is no `package.json`, no bundler, and no build step. Tailwind CSS is pulled in via the CDN script tag (`<script src="https://cdn.tailwindcss.com">`) directly in each page's `<head>`, so utility classes work with zero build process.

To preview the site, just open the HTML file directly in a browser (or serve the directory with any static file server, e.g. `npx serve .`). There is no dev server, lint, or test command configured in this repo.

The site is deployed via GitHub Pages from the `main` branch root at https://cohenmichaelr.github.io/racersedge/.

## Pages

- **`index.html`** — the live homepage (Hero, Bike Collection, Fittings, Contact/Location).
- **`performance.html`** — secondary page holding "Essential Kit" (component/gear brand logos) and part of the fitting content. It links back to `index.html`, but `index.html` does not yet link to it — that nav wiring is still incomplete. The plan also calls for removing the Fittings/"Master Fit Center" section from `index.html` once `performance.html` fully owns it; as of now `index.html` still contains that section inline.
- **`services.html`** — legacy services page.

## Assets

Images live under `Images/` (capitalized), with brand logos under `Images/LOGOS/<brand>/...`. Paths in HTML use this exact casing — preserve it, since GitHub Pages is case-sensitive even though local Windows dev isn't.

## Style rules

- Always use Tailwind utility classes for styling (no separate CSS files/frameworks).
- Dark mode with Electric Blue (`#007FFF`) accent color throughout.
- Mobile-first: verify layouts work for cyclists browsing on a phone.
- Comment non-obvious code with "why", not "what".
- Any new layout must be responsive before considering it done.
- Copy should sound elite/athletic ("Boca-Premium"), with punchy, direct CTAs.
