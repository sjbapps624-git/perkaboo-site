# PerkaBoo site

Static pages for PerkaBoo: a landing page, privacy policy, terms of use and support page. No build step.

## Publish with GitHub Pages
1. Create a new **public** GitHub repository (suggested name: `perkaboo-site`). Leave it empty.
2. From this folder: `git remote add origin https://github.com/<you>/perkaboo-site.git && git push -u origin main`
3. In the repository: Settings > Pages > Build and deployment > Source: **Deploy from a branch**, Branch: `main`, folder `/ (root)`.
4. After a minute the site is at `https://<you>.github.io/perkaboo-site/`. The privacy policy is at `.../privacy.html`.

Use those URLs for the App Store listing (Support URL, Privacy Policy URL, Marketing URL) and in `src/constants/links.ts` in the app.

## Before publishing
- The privacy policy mentions Sentry crash reports. Publish it only together with (or after) the build that includes Sentry, or remove that section.
- These pages are drafts written from how the app works. Have them reviewed by a lawyer if you want legal certainty, especially the Terms (for example, whether to add a governing-law clause).
- Keep the policy and the App Store "App Privacy" answers consistent.

## Card credit pages (generated)
`cards/*.html`, `december-31.html` and `sitemap.xml` are generated from the app's library file, so the site and the app never disagree. **Do not edit them by hand.**

- Regenerate after the library changes: `node scripts/build-pages.mjs` (reads `../perkaboo/src/data/library.json`; pass another path as an argument).
- Only cards listed in `PUBLISH` inside `scripts/build-pages.mjs` get a page: those verified with confidence A or B in the app repo's `docs/library-verification.md`. Add a card only after verifying it; the Delta SkyMiles Reserve is not published yet (confidence C).
- Each page shows the latest `lastVerified` date of its credits. Pages ship the disclaimers (not affiliated, public terms, confirm with your issuer) and use text names only.
- `SITE_URL` in the script drives canonical links and the sitemap: change it if the site gets its own domain, and submit `sitemap.xml` in Google Search Console.
- Publish by merging to `main` (GitHub Pages deploys from there).
