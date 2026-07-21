# what-is-my-ip

Static, no-backend IP lookup site. Pure HTML/CSS/JS, one file: `index.html`.

## Deploy on GitHub Pages
1. Push these files to repo root (or `/docs` folder) of `what-is-my-ip`.
2. Repo Settings → Pages → Source: `main` branch, `/root`.
3. Custom domain: add your domain in Pages settings, this creates `CNAME` file automatically. Add DNS A records (GitHub Pages IPs) or CNAME record per GitHub docs.
4. Replace every `https://what-is-my-ip.example.com/` in `index.html`, `robots.txt`, `sitemap.xml`, `llms.txt` with your real domain.
5. Add an `og-image.png` (1200x630) at root for social previews, or remove the og:image tags.

## Submit to search engines
- Google Search Console: add property, submit `sitemap.xml`.
- Bing Webmaster Tools: same, or import from GSC.

## Notes
- No backend. IP geolocation via free client-side APIs: `ipwho.is` (primary, HTTPS, no key), `ipapi.co` (fallback).
- ip-api.com was intentionally NOT used as primary: its free tier is HTTP-only, which breaks on an HTTPS GitHub Pages site, and CORS/rate limit (45 req/min per IP) is stricter for browser use. Fallback list can be extended similarly if you add a 3rd provider.
- No cookies, no localStorage, no server logging — nothing is stored.
