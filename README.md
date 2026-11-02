# Pandion Labs

The public organization site for Pandion Labs: tools for AI agents and the people who direct them.

The site is plain HTML and CSS, with a small SVG favicon. There is no build step, JavaScript, analytics, or application backend. Typography loads from Google Fonts; system fonts are the fallback.

## Preview

Run `python3 -m http.server 8765` from this directory and open <http://localhost:8765>.

## Publish

GitHub Pages serves the root of `main` at <https://pandion-labs.github.io/>. Changes pushed to `main` are published automatically. `.nojekyll` keeps the site as static files.

The company vision lives in `index.html`; the design and responsive layouts are in `styles.css`.

## Domain forwarding

At the domain registrar, configure an unmasked permanent (301) redirect from `pandionlabs.com` to `https://pandion-labs.github.io/`. Include `www.pandionlabs.com` if desired and ensure the forwarding service supports HTTPS for the source domain.

There is intentionally no `CNAME` file: this setup uses registrar forwarding to the GitHub Pages URL. Serving the site directly at `pandionlabs.com` would instead require GitHub Pages custom-domain configuration and corresponding DNS changes.
