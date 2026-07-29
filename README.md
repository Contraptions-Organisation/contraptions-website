# Rebooted Creative Lab

Static marketing site for Rebooted Education. It highlights OttoNinja-powered creative education labs, curated electronics kits, and downloadable curriculum resources. The site is built with [Astro](https://astro.build) so it can be deployed directly to Cloudflare Pages without a backend.

## Stack

- Astro 6 with island-friendly components
- Vanilla CSS with expressive gradients + typography (Sora + Space Grotesk)
- GitHub Actions workflow for CI (type-check + build) on every push/PR
- Deployed via Cloudflare Pages, connected directly to this repo

## Getting started

Prerequisites: Node.js 20.11+ and npm 10+.

```bash
npm install       # install dependencies
npm run dev       # start local dev server (press q to stop)
```

Key files:

- `src/pages/index.astro` – homepage sections (hero, projects, kits, timeline, CTA)
- `src/layouts/Layout.astro` – global HTML shell, fonts, and background system
- `astro.config.mjs` – site URL (`https://contraptions.nl`)

## Deploying to Cloudflare Pages

1. In the Cloudflare dashboard, go to **Workers & Pages → Create → Pages → Connect to Git**, and select this repository.
2. Build settings: framework preset **Astro**, build command `npm run build`, output directory `dist`.
3. Add `contraptions.nl` (and `www.contraptions.nl`) as custom domains on the Pages project once the zone's nameservers point to Cloudflare.
4. Every push to `main` triggers a new build/deploy automatically — no GitHub Actions involvement needed for deployment itself. `.github/workflows/ci.yml` still runs type-checking and a build on every push/PR as a sanity check.

## Customizing content

- Edit the data arrays at the top of `src/pages/index.astro` to add new kits, labs, or resource links.
- Update `public/favicon.svg` with your brand glyph (default is a simple Otto-inspired mark).
- Extend the layout or add new pages by creating `.astro` files in `src/pages/`.

## License

MIT © Rebooted Education
