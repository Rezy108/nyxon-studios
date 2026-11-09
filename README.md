# NYXON STUDIOS — Website V1.0

Responsive bilingual (German / English) static website, ready for Vercel. No build dependencies.

## Run locally


Use a local web server from the project directory:

```bash
python -m http.server 8080
```

Visit http://localhost:8080. Avoid opening index.html directly with file://.

## Deploy to Vercel

1. Upload the extracted `nyxon-studios` folder to a GitHub repository (including `index.html`, `styles.css`, `app.js`, `config.js`, `assets/`, `legal.html`, `favicon.svg`, and `vercel.json`).
2. In Vercel choose **Add New → Project**, import that repository.
3. Select **Other** as framework preset, leave build command empty, and set output directory to `.` (project root).
4. Deploy. Connect your custom domain later if desired.

## Edit content

- `config.js`: Discord invite and product catalog, statuses, descriptions, tags, optional prices, Tebex package URLs.
- `app.js`: German/English translations, product card and dialog behavior.
- `styles.css`: brand colors and responsive styles.
- `assets/nyxon-logo.png`: provided NYXON logo.

## Tebex integration (not active yet)

This version is a product showcase only, not a checkout. To enable an external Tebex product link later:

1. Create a legitimate Tebex store and verify the account, eligibility, platform requirements and permitted payment setup. Since the project owner is a minor, complete the necessary parental/legal steps before any sales.
2. Set a product's `status` to `available` and provide its verified HTTPS `tebexPackageUrl` in `config.js`.
3. The product dialog will show an external link to that package. Checkout, fulfillment and licensing remain handled by Tebex, not this website.
4. Set `tebexStoreUrl` for your own reference. No API key is required or embedded in this frontend.

Never put Tebex secret keys, tokens, webhooks secrets or customer data into browser-facing files. For future API integration, implement secure server-side endpoints and verify Tebex documentation.

## Before launch

- Replace placeholder Discord URL and product data.
- Fill in the legal page with accurate mandatory provider information and privacy disclosures; the current page is NOT a compliant legal notice.
- Confirm you have the right to use all brand assets and check the NYXON name for trademark conflicts.
- Test on desktop/mobile and confirm all links.
- Do not enable commercial sales before required permissions, business registration and payment provider eligibility are resolved.

## Technical notes

- Vanilla HTML/CSS/JS, no npm install or backend required.
- Language preference saved locally in the browser using localStorage.
- No third-party analytics or cookies configured. Google Fonts are loaded from Google; consider self-hosting fonts or using system fonts for privacy compliance.
- Product descriptions are escaped before insertion into the DOM, and external product links must be HTTPS.
