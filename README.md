# wraithlightdigital.com

Website for Wraithlight Digital LLC, a New Mexico AI and automation business. Plain static HTML and CSS, no build step, hosted free on Cloudflare and deployed automatically from this repo.

## Layout
* `site/` everything that gets published. This is the folder Cloudflare serves.
  * `index.html` the one page home: hero, services, approach, brands (WWII Dispatches), contact.
  * `privacy.html` plain language privacy policy (served at /privacy).
  * `404.html` not found page.
  * `css/site.css` all styles. Brand colors are variables at the top.
  * `fonts/` Outfit, self hosted (SIL Open Font License, see `fonts/OFL.txt`).
  * `img/` logo, WWII Dispatches mark, and `og.png` (the 1200 x 630 share preview).
  * favicons, `site.webmanifest`, `robots.txt`, `sitemap.xml`.
  * `_headers` Cloudflare security and caching headers.

## Brand
Night navy `#0F1A2B`, wisp amber `#F2B45A`, bone cream `#F5F1E8`, slate `#4A5568`. Type is Outfit. Don't close the halo gap, rotate the mark, recolor the crescent, or add a star beside it. Full rules live in the Wraithlight Branding folder (BRAND-NOTES.md).

## Cloudflare setup (one time)
Hosted as a Cloudflare Worker with static assets. `wrangler.jsonc` tells it to serve the `site/` folder, use `404.html` for missing pages, and serve `/privacy` from `privacy.html`.
1. Cloudflare dashboard, Workers & Pages, Create, Import a repository, pick `Wraithlight-Digital/website`.
2. Project name: `website` (must match `name` in `wrangler.jsonc`). Build command blank. Deploy command `npx wrangler deploy`.
3. Deploy. It goes live at a `*.workers.dev` address.
4. Settings, Domains and Routes, add custom domains `wraithlightdigital.com` and `www.wraithlightdigital.com`.

After that, every push to `main` redeploys in about a minute.

## Editing
Change the HTML in `site/`, commit, push. Preview locally with `python3 -m http.server -d site 8000`.

## Adding a page later
Copy `privacy.html` as a starting point (it has the shared header and footer), then add the URL to `sitemap.xml`.
