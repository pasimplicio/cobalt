# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users
Brazilian users who want to save a video, audio track, or photo from a social or media site (TikTok, YouTube, Instagram, X and others) by pasting a link, without accounts, ads, or installs.

## Product Purpose
A media downloader front end, published by PSDev Sistemas, built on the open-source cobalt project. Paste a link, get the file. Success is: link in, file saved, in one step, with clear feedback when something fails.

## Positioning
Run and branded by PSDev Sistemas (Desenvolvimento de Software) on top of a self-hosted cobalt processing instance. No trackers or ads; files are proxied or tunneled, not stored.

## Operating Context
Used on phones and desktops, often in a hurry: copy link from an app, open the site, paste, save. Also offers a local remux tool and a settings area (video quality, audio format, filenames, appearance, privacy, instances).

## Capabilities and Constraints
- SvelteKit app in `web/`, talks to the cobalt API set by `WEB_DEFAULT_API`.
- Routes: save (home), remux, settings (many subpages), about (general, privacy, terms, credits), updates (changelog), donate (to be removed in the PSDev build).
- i18n via `web/i18n/<lang>/`: PT-BR is the default locale; English and Russian remain selectable.
- Web code is CC-BY-NC-SA-4.0: derivatives must remove cobalt branding (name, logo, meowbalt mascot), credit the original repo, keep the same license, and stay non-commercial.

## Brand Commitments
- Name: PSDev Sistemas. Tagline: "Desenvolvimento de Software".
- Logo: `logopsdev.png` (repo root): P+S monogram with `</>`; navy P, electric-blue S, "PSDEV" in heavy geometric caps with "PS" in electric blue, "Sistemas" in regular weight.
- Theme follows the system by default, light and dark both supported.
- A visible credit to cobalt / imput.net stays on the About page.

## Evidence on Hand
- Logo raster only (`logopsdev.png`, 1536x1024, with background glow). No vector logo, no brand typeface file, no other brand assets.
- No testimonials, customers, or usage numbers. Do not invent any.

## Product Principles
1. The link box is the product; everything else is secondary.
2. Errors say what happened and what to try next, in plain Portuguese.
3. Brand lives in precise details, never in the way of the task.
4. Honest about origin: credit cobalt, claim nothing it does not do.
