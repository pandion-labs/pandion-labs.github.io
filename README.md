# Pandion Labs

The public organization site for Pandion Labs: tools for AI agents and the people who direct them.

The site is plain HTML and CSS, with a small SVG favicon. There is no build step, JavaScript, analytics, or application backend. Typography loads from Google Fonts; system fonts are the fallback.

## Preview

Run `python3 -m http.server 8765` from this directory and open <http://localhost:8765>.

## Publish

GitHub Pages serves the root of `main` at <https://pandionlabs.com/>. Changes pushed to `main` are published automatically. `.nojekyll` keeps the site as static files.

The company vision lives in `index.html`; the design and responsive layouts are in `styles.css`.

## Custom domain

The canonical site URL is <https://pandionlabs.com/>. GitHub Pages redirects both `www.pandionlabs.com` and `pandion-labs.github.io` to this address. HTTPS is enforced.

DNS is hosted at Hover. The apex (`@`) has four A records: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, and `185.199.111.153`. The `www` CNAME points to `pandion-labs.github.io`.

The root `CNAME` file contains `pandionlabs.com` and must be preserved. If the domain changes, update the GitHub Pages setting, DNS records, canonical and Open Graph URLs in `index.html`, `robots.txt`, and `sitemap.xml` together.
