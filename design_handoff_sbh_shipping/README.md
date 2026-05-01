# Handoff: SBH Shipping Co. — Marketing Site

## Overview

This package is a complete handoff for the **SBH Shipping Co.** marketing website — a single-page brand site for a 112-year-old Egyptian maritime logistics company with operations across the Suez Canal, Red Sea, and Gulf of Aden corridor. The site presents the company's heritage, network, services, and contact channels, with full English ⇄ Arabic (RTL) support.

The brand was rebuilt around a new visual identity: a combined **cargo-ship-meets-lighthouse** mark, a white/electric-blue color system, and a typographic system using **Space Grotesk** (display/UI) and **JetBrains Mono** (numerals/codes/eyebrows).

---

## About the Design Files

The HTML file in `design_reference/` is a **design reference** — a high-fidelity prototype showing the intended look, content, and behavior of the site. **It is not production code to ship as-is.**

Your task is to **recreate this design in your target codebase's environment** (Next.js / React / Astro / Vue / SvelteKit / static / WordPress — whatever fits the project) using the codebase's existing patterns, component library, and build tooling. If no environment exists yet, choose the framework best suited to the project (we'd recommend **Next.js + Tailwind** or **Astro** for a marketing site of this kind).

The HTML uses inline React/Babel for the dynamic bits (i18n switcher, language toggle, ticker, scroll reveal); in production these should be implemented as proper components in the chosen framework.

---

## Fidelity

**High-fidelity (hifi).** Colors, typography, spacing, motion, copy, and layout are all final. Reproduce pixel-perfectly using the codebase's existing libraries and patterns.

---

## File Structure

```
design_handoff_sbh_shipping/
├── README.md                                  ← you are here
├── design_reference/
│   └── SBH Shipping.html                      ← the hi-fi prototype
└── brand/
    ├── sbh-logo-mark.svg                      ← icon-only mark (square, transparent)
    ├── sbh-logo-horizontal.svg                ← icon + "SBH SHIPPING CO." wordmark
    ├── favicon.svg                            ← modern browsers
    ├── favicon.ico                            ← legacy (16/32/48 bundled)
    ├── apple-touch-icon.png                   ← 180×180
    ├── icon-192.png                           ← PWA manifest
    ├── icon-512.png                           ← PWA manifest
    ├── site.webmanifest                       ← PWA manifest JSON
    └── png/                                   ← PNG renders, transparent
        ├── sbh-mark-16.png
        ├── sbh-mark-32.png
        ├── sbh-mark-48.png
        ├── sbh-mark-64.png
        ├── sbh-mark-128.png
        ├── sbh-mark-180.png
        ├── sbh-mark-192.png
        ├── sbh-mark-256.png
        ├── sbh-mark-512.png
        ├── sbh-mark-1024.png
        └── sbh-horizontal-{280x64,560x128,840x192,1120x256}.png
```

---

## Logo Usage

- **Primary lockup:** horizontal SVG (`sbh-logo-horizontal.svg`) on header/footer when there's room.
- **Compact / square contexts:** mark-only SVG (`sbh-logo-mark.svg`) — favicons, social avatars, app icons, mobile nav.
- **Always prefer SVG.** PNGs are provided as fallbacks for environments that need raster (email signatures, social posts, OS icons).
- **Backgrounds:** the mark is designed for **white or very light backgrounds**. On dark backgrounds, switch to a white-stroked variant — not included; create one by overriding `#0066ff → #ffffff` and `#0a1f3d → #ffffff` if needed.
- **Clear space:** keep at least the height of the lantern (top dome) clear on all sides.
- **Minimum size:** 16px (favicon) — below that, details break down. Don't render the horizontal lockup smaller than 120px wide.

### Favicon HTML

Drop this in `<head>`:

```html
<link rel="icon" type="image/svg+xml" href="/favicon.svg" />
<link rel="icon" type="image/x-icon" href="/favicon.ico" />
<link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png" />
<link rel="manifest" href="/site.webmanifest" />
<meta name="theme-color" content="#0066ff" />
```

---

## Design Tokens

### Colors

| Token | Value | Use |
|---|---|---|
| `--void` (page bg) | `#f4f8ff` | App background, hero overlay |
| `--navy` (panel) | `#e9f0fb` | Slightly inset panels, hover states |
| `--ink` (primary text) | `#0a1f3d` | Headings, body text |
| `--bone` (secondary text) | `#3a4a6b` | Subheads, paragraph copy |
| `--gray` (muted) | `#7a8aa6` | Eyebrows, captions, meta |
| `--cyan` (accent) | `#0066ff` | Brand primary, links, CTAs, accents |
| `--gold` (accent 2) | `#00d4ff` | Highlights, glow, secondary accent |
| `--gold-dim` | `rgba(0,212,255,0.14)` | Tinted accent backgrounds |
| Status / live | `#4ade80` | "24/7 LIVE" indicator |

Primary gradient: `linear-gradient(135deg, #00d4ff, #0066ff, #0044cc)`

### Typography

| Family | Use | Source |
|---|---|---|
| **Space Grotesk** | All display & UI text. Weights 300–700. | Google Fonts |
| **JetBrains Mono** | Numerals, codes, ticker, eyebrows. Weights 300–600. | Google Fonts |
| **Cairo** *(Arabic)* | RTL text fallback. | Google Fonts |

Type scale (px): hero 88 → section title 56 → card title 28 → body 16 → micro 11.
Letter-spacing on uppercase labels: `0.18em` for nav/eyebrows, `0.32em` for stat dividers.

### Spacing & Radius

- **Section vertical padding:** 140px (top & bottom on desktop), 80px on mobile.
- **Container max-width:** 1280px, 36px gutter.
- **Card / panel radius:** **2–4px only** — design intentionally avoids soft corners. Pills/badges use `999px`.
- **Borders:** 1px, low-opacity (`rgba(0,102,255,0.10)` to `0.18`).

### Shadows

- Panel hover: `0 24px 80px rgba(0, 40, 100, 0.15)`
- Glow accent: `0 0 50px rgba(0, 102, 255, 0.4)`

### Motion

- Easing: `cubic-bezier(0.25, 0.4, 0.25, 1)` for content, `cubic-bezier(0.16, 1, 0.3, 1)` for entrances.
- Fade-up reveal on scroll: 24px translateY + opacity, 700ms, staggered by 80–120ms.
- Hover lifts: `translateY(-2px to -4px)`, 280ms.
- Counter animation: 1800ms ease-out on first viewport entry.
- Orbital ring rotation: 8s / 12s / 20s linear infinite.

---

## Sections (top → bottom)

1. **Nav** — fixed, transparent → frosted-white on scroll. Logo left, anchor links center, language toggle (EN/AR) + "Get a Quote" CTA right.
2. **Hero** — full-viewport, YouTube background video (muted, looped), light overlay. Left: eyebrow + 88px headline + 18px description + CTAs. Right: glassmorphic "panel card" with the orbital animated logo, name lockup, and a stat row (112 / Years · 4 / Strategic Hubs · 24/7 / Live Ops).
3. **Live Ticker** — full-width strip with continuously scrolling cargo updates (vessel names, ports, ETAs).
4. **About / Heritage** — eyebrow "EST. 1914" + headline + 4-paragraph copy + 3-pillar feature grid.
5. **Timeline** — vertical timeline, 5 milestones (1914, 1952, 1989, 2010, 2026).
6. **Routes / Network** — 4 hub cards (Alexandria, Jebel Ali Dubai, Djibouti, Aden) with port stats.
7. **Services** — 6-card grid: FCL, LCL, Project Cargo, Customs Brokerage, Inland Distribution, Ship Husbandry.
8. **Stats Strip** — 4 large counters (vessels handled, TEU/year, on-time %, ports served).
9. **Trust / Heritage Quote** — full-width pull quote on light tinted bg.
10. **Contact** — left: contact details (HQ Alexandria, network, ops, email, heritage quote). Right: form (first/last name, company, email, phone, service select, route, message, submit).
11. **Footer** — logo lockup, address, secondary nav, copyright, "Egypt → World" tagline.

Use `[data-screen-label]` on each section root if you want them visible in design tooling.

---

## Interactions & Behavior

- **Language toggle (EN / AR):** flips `dir="ltr"` ↔ `dir="rtl"` on `<html>`, swaps every `data-i18n` and `data-placeholder-i18n` text, and reverses any directional gradient. Persist to `localStorage` key `sbh-lang`.
- **Nav scroll state:** add `.scrolled` class to `<nav>` when `window.scrollY > 24`.
- **Fade-up reveal:** elements with `.fade-up` start at opacity 0 + 24px down; `IntersectionObserver` (threshold 0.15) adds `.in-view` to play. Stagger via `.fade-up-d1`, `.fade-up-d2`, etc.
- **Stat counters:** numeric children of `.stat-num` count from 0 → target value over 1800ms when scrolled into view, once per page load.
- **Live ticker:** CSS-only marquee, two duplicated tracks animating `transform: translateX(-50%)` on a 60s loop. Pause on hover.
- **Form submit:** validate locally, show `.form-success` message, then POST to your contact endpoint. The current prototype just `preventDefault()`s and shows the success state.
- **Background video:** hosted on YouTube, loaded as `<iframe>`. Replace with a self-hosted `<video>` (muted, autoplay, playsInline) in production for performance and to avoid YouTube branding leak.

---

## Responsive Notes

- **≥ 1100px:** two-column hero, four-column hub grid.
- **768–1099px:** single-column hero (panel card stacks below copy), two-column grids.
- **< 768px:** single column throughout, nav collapses to logo + hamburger (you'll need to build the drawer — the prototype shows the desktop nav only).
- All grids use CSS Grid with `auto-fit` / `minmax()` so they degrade automatically.

---

## State Management

Minimal — this is a marketing site. Only persistent state is **language preference** (`localStorage['sbh-lang']`). All other interactivity is local component state (hover, scroll position, form fields, success flag).

If using Next.js, render server-side per locale (`/en`, `/ar`) and skip the client-side i18n switcher; let Next handle it via `next-intl` or built-in `i18n` config.

---

## Copy & Content

All copy is in the design reference file inside `<script>` blocks `EN_TRANSLATIONS` and `AR_TRANSLATIONS`. Pull these directly into your i18n system (`messages/en.json`, `messages/ar.json` for `next-intl`, or equivalent).

The Arabic strings have been hand-translated for tone and idiom — don't run them through machine translation again, they'll lose nuance.

---

## Assets

- **Logos & favicons:** in `brand/` — see file structure above. All transparent, all formats covered.
- **Background video:** placeholder is a YouTube embed (`7J5nt0V5XOE`). Replace with a licensed maritime/cargo aerial clip, encoded as `mp4` (H.264) + `webm` (VP9), max 8 MB, 1920×1080.
- **Photography (if you add any):** lean editorial, cool blue grade, Suez/Red Sea / port operations / aerial shipping lanes. Avoid stock-photo clichés (no shaking-hands shots, no globe overlays).
- **Icons:** the design uses a mix of inline SVG and the `◈` glyph as a brand mark accent. Don't introduce a third-party icon set unless it's needed for a service grid icon — and if you do, use a single set (Phosphor or Lucide, thin weight) consistently.

---

## Implementation Checklist

- [ ] Choose framework + scaffold project
- [ ] Install Space Grotesk + JetBrains Mono + Cairo via Google Fonts (or self-host with `next/font`)
- [ ] Drop `brand/` files into `public/` and wire favicon `<link>` tags
- [ ] Convert design tokens to CSS custom properties / Tailwind config
- [ ] Build sections in order (nav → hero → ticker → about → timeline → routes → services → stats → trust → contact → footer)
- [ ] Wire i18n with EN + AR JSON tables (extract from design reference)
- [ ] Implement scroll reveals via `IntersectionObserver` (or `framer-motion`'s `whileInView`)
- [ ] Replace YouTube hero video with self-hosted asset
- [ ] Build mobile nav drawer (not in prototype)
- [ ] Wire contact form to backend / email service (Resend, Postmark, SendGrid)
- [ ] SEO: title, description, OpenGraph image (use `sbh-mark-512.png`), JSON-LD `Organization` schema
- [ ] Lighthouse pass: 95+ on all categories before ship

---

## Files Referenced

- `design_reference/SBH Shipping.html` — open in a browser to see the full prototype, including animations, RTL toggle, and all interactions.
- `brand/*` — all logo and favicon assets, ready to copy into `public/`.

Questions on intent or design rationale? The prototype is the source of truth — when in doubt, match it pixel-for-pixel.
