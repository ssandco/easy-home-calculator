# Home Calculator — 100 separate pages

Built 2026-11-24 from the source file `~/workspace/ts-spaces/home-calculator/index.html`.

## What is in this folder

- **100 tool pages** — one real HTML file per calculator, e.g. `paint-calculator.html`,
  `concrete-calculator.html`, `cubic-yard-calculator.html`. Each page works standalone:
  enter measurements, the result updates instantly, using the exact same fields and
  formula as the source. No JavaScript framework, no server needed — open any file
  in a browser (or serve the folder with any static host).
- **`index.html`** — the hub: all 100 calculators grouped by category, with a live
  search box that filters the list.
- **`privacy.html`, `about.html`** — short supporting pages linked from the footer.
- **`sitemap.xml`** — lists the hub + all 100 tool pages + privacy/about (103 URLs).
- **`robots.txt`** — points search engines at the sitemap.

## Verified counts (source of truth checked)

The source file **claims** 100 tools — and it really does contain exactly 100:
20 in the main `TOOLS` array + 53 added with `T({...})` + 27 added by helper
functions (`volBag` 6, `volTon` 8, `areaCover` 8, `tileLike` 3, `linearPerim` 2).
Categories: **Yard & Outdoor 35, Interior 34, Structure & Build 31 = 100**.
No tools were invented; every page below is one of those 100.

## What each tool page has

- Title tag + H1 with that tool's main keyword (e.g. "Paint Calculator")
- A direct-answer box at the top with the formula (AEO/GEO)
- A short intro paragraph using 3–5 related search phrases for *that* tool only
- A "People also search for" section with 8 related phrases for that tool
  (linked to the matching tool page where one exists, plain text otherwise)
- 3 FAQs per page, with FAQPage schema
- Meta description + keywords, canonical URL, Open Graph / Twitter tags
- Related calculators: 5 links to tools in the same category + a breadcrumb
  back to the hub. No page links to all 100 tools.
- Share buttons (WhatsApp / X / Facebook), clean white style with green
  accent `#147a4d`, matching the source
- Google Analytics (GA4) and Search Console placeholders — commented out,
  marked `G-XXXXXXXXXX` / `YOUR_VERIFICATION_CODE` for Sana to fill in.
  No AdSense yet, as instructed.

## Verification done (2026-11-24)

- **Calculators: 100/100 pass.** Each page's calc function was run with its
  default field values in Node and returned a real, finite result; the calc
  code embedded in each page is byte-identical to the source.
  One real bug was found and fixed during this check: 22 helper-built tools
  (topsoil, sand, grout, laminate, etc.) close over helper values
  (`bagCf`, `tonsPerCy`, `unit`) — those values are now defined in each
  affected page, so the calculators work standalone.
- **Rendered in a real DOM (jsdom): 16/16 spot-checked pages pass** —
  paint, concrete, cubic-yard, topsoil, grout, btu, stair, excavation,
  pond-volume, grass-seed, roof-pitch, heated-floor, two-by-four,
  water-heater, sand, laminate — each shows a non-zero result and its
  input fields on load. Sample defaults: Paint 1.7 gallons, Concrete
  56 × 80 lb bags, Cubic Yard 1.02 cu yd, Tile 88 tiles.
- **Links: 0 broken.** All internal `.html` links in all 103 pages point
  to files that exist in this folder; the hub links to all 100 tool pages.
  (The only `data:,` hrefs are favicon placeholders, not links.)
- **Sitemap: 103/103 URLs**, matching the files in this folder exactly.
- **Structure: every tool page** has its title, H1, meta description,
  FAQPage schema with 3 FAQs, "People also search for", 5 related
  calculators and a hub link.

## Not done — needs Sana / the main agent

- **NOT published, NOT deployed, no domain bought.** The canonical URLs
  use `https://easyhomecalculator.com/` as a placeholder — that domain
  is in Sana's Namecheap cart (unpaid at last check) and must be bought
  and pointed at a host before these pages go live.
- Upload this whole folder to the host (free static hosting, e.g. Vercel
  or GitHub Pages), then submit `sitemap.xml` in Google Search Console.
- Fill in the GA4 Measurement ID and Search Console verification code
  (placeholders are marked in every page's `<head>`).
- Nothing else in the TrackCE / KDP work was touched by this build.
