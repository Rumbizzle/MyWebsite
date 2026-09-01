# rumbimunyaradzi.com

Static site. Deploy on GitHub Pages:

1. Create a repository (public) and upload **everything inside this folder**, keeping the folder structure:
   - index.html
   - support.js
   - uploads/
   - assets/
   - mentorship/ workshops/ speaking/ community/ books/ about/ faq/ contact/
   - sitemap.xml, robots.txt, CNAME, .nojekyll
2. Repo **Settings → Pages** → Source: *Deploy from a branch* → Branch: `main`, folder `/ (root)` → Save.
3. Settings → Pages → Custom domain: `rumbimunyaradzi.com` (the `CNAME` file already sets this). Tick **Enforce HTTPS**.
4. At your registrar: an `ALIAS`/`A` record for the apex pointing at GitHub Pages, and a `CNAME` record for `www` → `<username>.github.io`.

## SEO

- Every page has its own folder with a real URL, title, meta description, canonical and Open Graph / Twitter card tags.
- Structured data: Person, ProfessionalService, WebSite, Book (×3) and EventSeries on the home page; FAQPage on `/faq/`.
- `sitemap.xml` lists all nine URLs — submit it in **Google Search Console** (verify the domain first) and **Bing Webmaster Tools**.
- In-app navigation updates the URL, title and canonical via the History API, so sharing any page shares the right link.

**If you edit index.html, regenerate the sub-pages.** They are copies of `index.html` with root-absolute asset paths (`/uploads/…`) and their own head tags. Ask Claude to "regenerate the SEO sub-pages" after any content change.

Notes
- `.nojekyll` is required so GitHub serves files/folders as-is.
- All filenames are lowercase-hyphenated; GitHub Pages is case-sensitive, so keep them exactly as-is.
- Photos are compressed to 1600px max. Originals stay in the project.
- Book trailers stream from YouTube, so they need an internet connection.
- The three forms post into the linked Google Form / Sheet.
- Summer Masterclass slides: `uploads/summer-masterclass-1.jpeg` … `-5.jpeg`. To update the series, replace those five files (same names, 4:5 portrait) — the carousel picks them up automatically.
- `rumbi-munyaradzi-website.html` is an optional single-file copy of the whole site with every asset embedded. Use it for email/WhatsApp or offline viewing; it is not needed for the GitHub Pages deploy.
