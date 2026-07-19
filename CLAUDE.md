# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Context

The Racer's Edge is a marketing site for a high-end bike shop in Boca Raton, FL. The desired vibe is clean, premium, and athletic: dark mode UI with "Electric Blue" (`#007FFF`) accents, mobile-first layouts (target audience checks the site from their phone), and copy that reads elite/professional/athletic rather than generic retail.

## Tech Stack / Tooling

Static HTML only — there is no `package.json`, no bundler, and no build step. Tailwind CSS is pulled in via the CDN script tag (`<script src="https://cdn.tailwindcss.com">`) directly in each page's `<head>`, so utility classes work with zero build process.

To preview the site, just open the HTML file directly in a browser (or serve the directory with any static file server, e.g. `npx serve .`). There is no dev server, lint, or test command configured in this repo.

## Canonical entry point — read this before editing any index*.html

There are four `index*` files; only one is current:

- **`index.html` — CANONICAL.** This is the live homepage. It has the newest mtime of the group and matches the structure described in `conductor/site-split-plan.md` (Hero, Bike Collection, Fittings, Contact/Location).
- `performance.html` — current secondary page, linked *from* nowhere yet but itself links back to `index.html` (`href="index.html"`, `#bikes`, `#contact`). Holds "Essential Kit" (component/gear brand logos) and part of the fitting content.
- `indexnew.html` — an alternate/abandoned in-progress rewrite using a scroll-snap carousel approach (`scroll-snap-type`, `.carousel-slide`, etc.) not used by `index.html`. Not linked from anywhere. Do not edit expecting it to be live.
- `index_new.html` — an earlier draft; contains an "Essential Kit" section that was later split out into `performance.html`.
- `index_old.html` — legacy multi-page version of the site, links out to now-nonexistent pages (`bikefit.html`, `road.html`, `mtn.html`, `gravel.html`, `tri.html`, `ebikes.html`, `demo.html`, `contact.html`). Kept only for reference; not part of the current site.

Note: the site-split plan in `conductor/` calls for removing the Fittings/"Master Fit Center" section from `index.html` once it's duplicated into `performance.html`, and for `index.html`'s nav to link to `performance.html`. As of now `index.html` still contains that section inline and does not yet link to `performance.html` — this migration is incomplete, so don't assume the split is finished when making changes.

## `conductor/` directory

Not a build tool — it's a plans folder. Currently contains `site-split-plan.md`, a design/implementation plan describing the index.html/performance.html split (goals, section ownership per page, nav wiring, verification checklist). Treat files here as planning docs to consult/update, not executable tooling.

## Assets

Images live under `Images/` (capitalized), with brand logos under `Images/LOGOS/<brand>/...`. Paths in HTML use this exact casing — preserve it, since deployment may be case-sensitive even though local Windows dev isn't.

## Style rules carried over from GEMINI.md

- Always use Tailwind utility classes for styling (no separate CSS files/frameworks).
- Dark mode with Electric Blue (`#007FFF`) accent color throughout.
- Mobile-first: verify layouts work for cyclists browsing on a phone.
- Comment non-obvious code with "why", not "what".
- Any new layout must be responsive before considering it done.

There is also a Gemini CLI custom command at `.gemini/commands/bocafy.toml` ("Boca-Premium" content reviewer persona: elevates copy to sound elite/athletic, enforces Tailwind dark mode, checks CTAs are punchy/direct). It's Gemini-CLI-specific tooling, not something Claude Code runs, but its review criteria are useful to keep in mind when writing or editing on-page copy.
