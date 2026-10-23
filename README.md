# wraithlightdigital.com

Website for Wraithlight Digital LLC, a New Mexico AI and automation business. Plain static HTML and CSS, no build step, hosted free on Cloudflare Pages and deployed automatically from this repo.

## Layout
* `site/` everything that gets published. This is the Cloudflare Pages output folder.
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

## Cloudflare Pages setup (one time)
1. Cloudflare dashboard, Workers & Pages, Create, Pages, Connect to Git, pick this repo.
2. Framework preset: None. Build command: leave blank. Build output directory: `site`.
3. Save and Deploy. It goes live at a `*.pages.dev` address.
4. Custom domains, add `wraithlightdigital.com` and `www.wraithlightdigital.com`. Because the domain is already on Cloudflare, DNS is created automatically.
5. Optional: redirect www to the bare domain with a Redirect Rule.

After that, every push to `main` redeploys in under a minute.

## Editing
Change the HTML in `site/`, commit, push. Preview locally with `python3 -m http.server -d site 8000`.

## Adding a page later
Copy `privacy.html` as a starting point (it has the shared header and footer), then add the URL to `sitemap.xml`.
