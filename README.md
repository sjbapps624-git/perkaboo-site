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
