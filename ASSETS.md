# Assets guide — where to drop your brand files

This answers: *where do images go, how do I supply a font, where does the brand guide live, and how do the Promise / Testimonials graphics get used.*

Everything lives in these three folders:

```
assets/img/      → all photos, logo, and the Promise/Testimonials graphics
assets/fonts/    → self-hosted font files (only if not a Google Font)
brand/           → your brand guide PDF + logo source files
```

After you drop files in, **tell me the filenames you used** (or just say "they're in") and I'll wire them into the HTML/CSS in one pass. Until then the site keeps showing the current Unsplash placeholders, so nothing looks broken.

---

## 1. Photos to replace → `assets/img/`

Drop a file using the **suggested name** in the table and I'll swap it for the matching placeholder. JPG or WebP, optimized for web (aim < 400 KB each). Sizes are recommendations — anything close works.

| Page | Where it shows | Suggested filename | Orientation / size |
| --- | --- | --- | --- |
| Home | Full-screen hero | `hero-home.jpg` | Landscape, ~1920×1280 |
| Home | "Welcome aboard" side image | `home-welcome.jpg` | Portrait 4:5, ~1000×1250 |
| Home | Bottom CTA band | `cta-home.jpg` | Landscape, ~1920×1080 |
| About | Page header banner | `about-hero.jpg` | Landscape, ~1920×900 |
| About | Photo of you (the tall image) | `about-zac.jpg` | Portrait 3:4, ~1050×1400 |
| About | Bottom CTA band | `cta-about.jpg` | Landscape, ~1920×1080 |
| Promise | Page header banner | `promise-hero.jpg` | Landscape, ~1920×900 |
| Promise | Bottom CTA band | `cta-promise.jpg` | Landscape, ~1920×1080 |
| Testimonials | Page header banner | `testimonials-hero.jpg` | Landscape, ~1920×900 |
| Refer | Page header banner | `refer-hero.jpg` | Landscape, ~1920×900 |
| Refer | Bottom CTA band | `cta-refer.jpg` | Landscape, ~1920×1080 |
| 404 | Error page background | `notfound.jpg` | Landscape, ~1920×1080 |

## 2. Logo → `assets/img/`

Right now the logo is a placeholder (a teal circle with a "B" + wave icon) used in the top nav, the footer, and the browser-tab favicon. Drop your real logo and I'll place it everywhere:

- `logo.svg` — preferred (scales crisply). PNG with transparent background also fine (`logo.png`, ~400px tall).
- If you have a **light/white version** for dark areas, add `logo-light.svg` (used in the footer over the navy background).
- A square **icon/monogram** version (`favicon.png`, 512×512) makes the best browser-tab icon.

## 3. Promise graphics → `assets/img/`

You said you have a graphic for each of the five promises. They'll replace the line icons on the **Promise** page (and the three shown on the home page). Name them in this order:

| # | Promise | Filename |
| --- | --- | --- |
| 1 | Bespoke Journeys | `promise-1.png` |
| 2 | Outstanding Opportunities | `promise-2.png` |
| 3 | Unmatched Guidance | `promise-3.png` |
| 4 | Network of Experts | `promise-4.png` |
| 5 | Dedicated Service | `promise-5.png` |

PNG/SVG with transparent background, roughly square (~600×600). If your graphics are full illustrations rather than icons, tell me — I'll switch the cards to an image-led layout instead of the small icon badge.

## 4. Testimonials graphics → `assets/img/`

You have graphics for the three testimonials. Name them by author:

| Testimonial | Filename |
| --- | --- |
| Michael C. | `testimonial-michael.jpg` |
| Steven | `testimonial-steven.jpg` |
| Becky G. | `testimonial-becky.jpg` |

Tell me whether each graphic is **a photo/portrait** (I'll add it beside the quote), **a screenshot of the review** (I'll show it as the card), or **a decorative illustration** — the layout differs for each, so I'll match it to what you've got.

---

## 5. Supplying a font

**If it's a Google Font** (e.g. "Cormorant", "Poppins"): just tell me the name(s) and which is for **headings** vs **body**. I'll swap the `<link>` in each page — nothing for you to upload.

**If it's a licensed / custom font:** drop the files in `assets/fonts/` and I'll add the `@font-face` rules. Best to provide:

- `.woff2` **and** `.woff` for each weight (woff2 is the modern format; woff is the fallback). `.ttf`/`.otf` also work but are larger.
- One file per weight you use, named like `BrandSans-Regular.woff2`, `BrandSans-Medium.woff2`, `BrandSerif-Bold.woff2`, etc.
- A note on **which font + weight = headings** and **which = body text**.

Make sure your license permits web embedding (most paid fonts include a webfont license).

## 6. Brand guide → `brand/`

Drop your brand guide in the `brand/` folder — a **PDF is ideal** (e.g. `brand/brand-guide.pdf`) — and tell me it's there. I can read it directly and pull out:

- **Colors** → mapped to the site's CSS variables (`--navy`, `--lagoon`, `--aqua`, `--sand`, `--cream`, etc.) so the whole site recolors at once.
- **Typography** → applied per §5 above.
- **Logo** usage, spacing, and any tagline/voice rules.

If the guide is a set of images instead of a PDF, drop those in `brand/` too. Once it's in, I'll apply it and show you a before/after.
