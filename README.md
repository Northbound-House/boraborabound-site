# Bora Bora Bound

A static rebuild of [boraborabound.com](https://boraborabound.com) for hosting on **GitHub Pages**. Hand-coded HTML/CSS/JS — no build step, no dependencies.

## Pages

| File | Page |
| --- | --- |
| `index.html` | Home |
| `about.html` | About Zac |
| `promise.html` | Our Promise |
| `testimonials.html` | Testimonials |
| `refer.html` | Refer & Earn |
| `404.html` | Not-found page |

Shared assets live in `assets/css/styles.css` and `assets/js/main.js`. The nav, footer, and contact modal are repeated in each page (static site — no templating).

## Deploying to GitHub Pages

1. Create a repo (e.g. `boraborabound-site`) and push these files to the default branch.
   ```bash
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin git@github.com:<you>/boraborabound-site.git
   git push -u origin main
   ```
2. In the repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, branch `main`, folder `/ (root)`.
3. **Custom domain:** the included `CNAME` file already points to `boraborabound.com`. In your DNS provider, add:
   - An `ALIAS`/`ANAME`/flattened-`CNAME` record on the apex `boraborabound.com` → `<you>.github.io`, **or** four `A` records to GitHub's IPs: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`.
   - A `CNAME` record for `www` → `<you>.github.io`.
4. Back in **Settings → Pages**, confirm the custom domain and tick **Enforce HTTPS** once the cert is issued.

`.nojekyll` is included so GitHub serves the files as-is without Jekyll processing.

## ⚠️ TODO — Connect the forms

The contact modal (every page) and the referral form (`refer.html`) are **styled placeholders**. On submit they show a friendly "not connected yet" message and reset — no data is sent anywhere.

When your CRM forms are ready, wire each one up:

- **Contact form** — search for `<form data-placeholder>` inside the `#contact-modal` block on every page.
- **Referral form** — `<form data-placeholder>` inside `#refer-form` in `refer.html`.

For each form: point the `action`/embed at your CRM, remove the `data-placeholder` attribute (this disables the placeholder JS handler in `assets/js/main.js`), and map the existing field `name`s (`name`, `email`, `message` / `your_name`, `your_email`, `friend_name`, `friend_email`, `message`).

## Improvements over the original

- Fully responsive with a mobile slide-in menu and accessible (focus-trapped, `Esc`-closable) modal.
- Scroll-reveal animations, sticky translucent header, and a hero scroll cue (all respect `prefers-reduced-motion`).
- Refer page upgraded with a 3-step "how it works" layout and a richer referral form (captures both your and your friend's details).
- Per-page SEO titles/descriptions, favicon, and a branded 404 page.
- Semantic HTML, system-friendly fonts via Google Fonts, no tracking or third-party scripts.

## Swapping imagery

Hero/section photos are free Unsplash placeholders referenced inline via CSS custom properties (e.g. `--hero-img`, `--page-img`, `--media-img`, `--cta-img`). Each has a gradient/color fallback, so the design holds even if an image fails to load. Replace the URLs with your own photos (ideally dropped into an `assets/img/` folder) when ready.
