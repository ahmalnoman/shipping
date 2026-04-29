# Handoff: Rigal Shipping Co. Website

## Overview
A full marketing website for **Rigal Shipping Co.**, an Egyptian maritime logistics company with 50+ years of history. The site connects Egypt's major ports (Port Said, Alexandria) to Dubai, Djibouti, Yemen, and global destinations. The design is futuristic, dark, and premium — built around a deep void-black base with electric cyan and gold accents.

## About the Design Files
The files in this bundle are **design references created in HTML** — high-fidelity prototypes showing the intended look, feel, and behavior. They are **not production code to copy directly**. Your task is to **recreate these designs in your target codebase** using its established framework, component library, and patterns (React, Next.js, Vue, etc.). If no framework exists yet, Next.js + Tailwind CSS is recommended given the nature of this project.

## Fidelity
**High-fidelity.** These are pixel-perfect mockups with final colors, typography, spacing, animations, and interactions. Recreate the UI as closely as possible using your codebase's existing libraries and patterns.

---

## Sections / Views

### 1. Navigation Bar
- **Fixed** to top, transparent initially → `background: rgba(2,5,8,0.92)` + `backdrop-filter: blur(20px)` on scroll
- **Height:** 72px
- **Logo:** SVG hexagonal mark (see `logo.svg` asset section) + wordmark `RIGAL` (Space Grotesk 600, 17px, letter-spacing 5px) + sub `SHIPPING CO.` (Space Grotesk 400, 8px, cyan, letter-spacing 4px)
- **Links:** Space Grotesk 13px, color `#606880`, hover → `#eeeae0` with animated underline (scale from left)
- **CTA Button:** "Get a Quote" — transparent bg, 1px solid `#00c8e8` border, `#00c8e8` text, 9px 24px padding, 2px border-radius. Hover: `rgba(0,200,232,0.15)` bg

### 2. Hero Section
- **Full-screen** (100vh), grid `1fr 440px`, gap 80px, centered vertically
- **Video background:** YouTube embed (cargo ship footage), dimmed to `brightness(0.18) saturate(0.6)`. Gradient overlays: `linear-gradient(180deg, rgba(2,5,8,0.5) 0%, transparent 30%, transparent 70%, rgba(2,5,8,0.95) 100%)` + left-side `linear-gradient(90deg, rgba(2,5,8,0.7) 0%, transparent 60%)`
- **Grid overlay:** CSS background-image grid lines in `rgba(0,200,232,0.04)`, 80×80px, masked radially
- **Scan line animation:** 2px horizontal line `rgba(0,200,232,0.4)`, animates top→bottom over 6s, infinite
- **Eyebrow:** 10px, letter-spacing 0.25em, `#00c8e8`, uppercase, with 40px left line
- **H1:** Cormorant Garamond 300, clamp(48px, 5.5vw, 78px), line-height 1.08. `em` tags → `#00c8e8`. `span` tags → `#c9a84c`
- **Description:** Space Grotesk 300, 15px, `#606880`, line-height 1.85, max-width 480px
- **Primary Button:** `linear-gradient(135deg, #00c8e8, #0088aa)`, color `#020508`, 15px 36px padding, 2px radius, font 600 13px, `box-shadow: 0 0 30px rgba(0,200,232,0.25)`. Hover: translateY(-2px) + brighter shadow
- **Ghost Button:** 1px solid `rgba(201,168,76,0.4)`, `#c9a84c` text, same padding. Hover: bg `rgba(201,168,76,0.15)`
- **Stats:** Three items — `50+` / `4` / `140+`. Number: Cormorant Garamond 300, 48px, `#00c8e8`. Label: 10px, `#606880`, letter-spacing 0.1em, uppercase. Count-up animation on scroll-into-view (easeOutCubic, 1800ms)
- **Right Panel (Hero Card):**
  - Background: `rgba(10,22,40,0.6)`, `backdrop-filter: blur(24px)`, border `1px solid rgba(0,200,232,0.15)`, 4px radius, 52px 40px padding
  - Shimmer top border: gradient line animating opacity 0.4→1 over 3s
  - Inner radial glow from top
  - 4× corner accent marks (L-shaped, 16px, `#00c8e8`, 50% opacity)
  - **Orbital rings:** 3 concentric circles rotating at 8s / 12s (reverse) / 20s. Colors: cyan, gold, dim cyan
  - **Center SVG logo:** 110px, hexagonal outer + inner crystal with facet lines, gold waterline, glowing cyan apex dot
  - **Wordmark:** "RIGAL" 26px 600 letter-spacing 8px + gold rule + "SHIPPING CO." 10px letter-spacing 5px cyan
  - **Status cards:** 3 rows (Operations LIVE / Active Routes / Est. 1975) with `rgba(0,200,232,0.05)` bg, `1px solid rgba(0,200,232,0.1)` border, 3px radius

### 3. Ticker Bar
- Borderless, `border-top` + `border-bottom` `1px solid rgba(0,200,232,0.2)`
- Items: 10px, `#00c8e8`, letter-spacing 0.18em, uppercase, separated by `◈`
- Scrolls left continuously (35s linear infinite), fades edges via `::before`/`::after` gradients

### 4. Services Grid
- **Background:** `#050d18`
- 8 cards in `repeat(4, 1fr)` grid, `gap: 1px`, wrapped in `rgba(0,200,232,0.08)` background (creates grid lines)
- Each card: `#050d18` bg, 44px 32px padding
- **Hover:** bg → `rgba(10,22,40,0.9)` + cyan top border line animates in (scaleX 0→1)
- Icon wrap: 48px square, 1px solid `rgba(0,200,232,0.2)`, 4px radius, cyan icon SVGs. Hover: `box-shadow: 0 0 24px rgba(0,200,232,0.4)`
- Number: 10px, `rgba(0,200,232,0.35)`, letter-spacing 0.15em
- Title: Space Grotesk 600, 15px, `#eeeae0`
- Body: Space Grotesk 300, 13px, `#606880`, line-height 1.75

### 5. Trust Bar
- `#0a1628` bg, cyan top/bottom borders
- Flex row, centered, gap 48px
- Each item: 4px cyan dot + 11px `#b8b4aa` text

### 6. About / Legacy Section
- Two-column grid `1fr 1fr`, gap 100px
- **Left:** eyebrow + H2 (Cormorant Garamond 300, ~52px, italic gold em) + 2 paragraphs + 3 pillars
  - Pillar accent: 2px vertical bar, `linear-gradient(180deg, #00c8e8, transparent)`
- **Right (Timeline):**
  - Vertical `::before` line: 1px, `linear-gradient(180deg, #00c8e8, rgba(0,200,232,0.1))`
  - Each item: 14px hollow dot (2px cyan border) with active state = filled + `box-shadow: 0 0 12px rgba(0,200,232,0.4)`
  - Year: Cormorant Garamond 28px cyan
  - Event: Space Grotesk 500 14px
  - Detail: Space Grotesk 300 12px `#606880`

### 7. Routes Section
- **Background:** `#050d18`
- **Animated SVG map:** 800×320 viewBox with animated dots traveling paths using `<animateMotion>` — 3 routes: Egypt→Dubai (4s), Egypt→Djibouti (5s), Djibouti→Yemen (3s). Primary nodes with pulsing expand animation. Node glow via radialGradient
- **Port cards:** `#0a1628` bg, 1px cyan border, 4px radius, 28px 24px padding. Hover: translateY(-4px) + brighter border + radial glow reveal

### 8. Contact Section
- Two-column grid `1fr 1fr`, gap 100px
- **Left:** eyebrow + H2 + description + contact detail rows (10px cyan label + 13px bone value) + italic quote block (gold border, `rgba(201,168,76,0.04)` bg, large `"` pseudo-element in gold at 30% opacity)
- **Right (Form):**
  - All inputs: `rgba(10,22,40,0.6)` bg, `1px solid rgba(0,200,232,0.12)` border, 2px radius, Space Grotesk 13px
  - Focus: border → `rgba(0,200,232,0.5)` + `box-shadow: 0 0 0 3px rgba(0,200,232,0.06)`
  - Submit: same gradient as primary CTA button, `box-shadow: 0 0 30px rgba(0,200,232,0.2)`. On submit: shows success message with cyan border/bg
  - Fields: First/Last (2-col), Company, Email, Service (select), Route, Message (textarea)

### 9. Footer
- `#020508` bg, `border-top: 1px solid rgba(0,200,232,0.1)`, 64px 0 32px padding
- Grid `2fr 1fr 1fr 1fr`, gap 56px
- Logo + tagline (300 13px `#606880`)
- Col headers: 10px cyan, letter-spacing 0.18em
- Links: 300 13px `#606880`, hover → `#eeeae0`
- Bottom bar: 11px `#606880`, border-top `rgba(255,255,255,0.05)`

---

## Animations & Interactions

| Animation | Duration | Easing | Trigger |
|---|---|---|---|
| Scan line (hero) | 6s | ease-in-out | continuous |
| Orbital ring 1 | 8s | linear | continuous |
| Orbital ring 2 | 12s reverse | linear | continuous |
| Orbital ring 3 | 20s | linear | continuous |
| Panel shimmer | 3s | ease-in-out | continuous |
| Ticker scroll | 35s | linear | continuous |
| Node pulse expand | 2.5s | — | continuous |
| Stat count-up | 1.8s | easeOutCubic | scroll into view |
| Fade-up sections | 0.8s | ease | scroll into view, threshold 0.08 |
| Service card hover | 0.3s–0.4s | ease | hover |
| Port card hover | 0.25s | ease | hover |
| Map dot travel | 3–5s | linear | continuous `<animateMotion>` |
| Nav transition | 0.4s | — | scroll > 80px |
| Live pulse dot | 2s | — | continuous |

---

## Design Tokens

### Colors
```
--void:       #020508      (page background)
--deep:       #050d18      (sections alt bg)
--navy:       #0a1628      (cards, inputs)
--navy-mid:   #0f2040
--cyan:       #00c8e8      (primary accent)
--cyan-dim:   rgba(0,200,232,0.15)
--cyan-glow:  rgba(0,200,232,0.4)
--gold:       #c9a84c      (secondary accent)
--gold-light: #e2c26a
--gold-dim:   rgba(201,168,76,0.15)
--bone:       #eeeae0      (primary text)
--bone-mid:   #b8b4aa
--gray:       #606880      (secondary text)
```

### Typography
```
Display / Headings:  Cormorant Garamond, weight 300 (italic for emphasis)
Body / UI:           Space Grotesk, weights 300 / 400 / 500 / 600
```

### Spacing
- Section padding: 120px 0
- Container max-width: 1280px, padding 0 40px
- Grid gap (services): 1px (separator style)
- Grid gap (ports): 20px
- Card padding: 44px 32px (services), 28px 24px (ports)

### Border Radius
- Cards, buttons, inputs: 2–4px (intentionally sharp/minimal)

### Shadows
- Primary button glow: `0 0 30px rgba(0,200,232,0.25)`
- Hover glow: `0 0 50px rgba(0,200,232,0.45)`
- Port card hover: `0 16px 48px rgba(0,0,0,0.4), 0 0 30px rgba(0,200,232,0.08)`
- Active dot: `0 0 12px rgba(0,200,232,0.4)`

---

## Assets

- **Logo SVG:** Inline SVG — hexagonal polygon + inner crystal shape + gold waterline + cyan apex dot + gradient stroke. See nav and footer in the HTML file for the exact `<svg>` markup.
- **Background Video:** YouTube embed ID `7J5nt0V5XOE` (cargo ship footage). Replace with a self-hosted `.mp4` for production. Apply `brightness(0.18) saturate(0.6)` filter.
- **Fonts:** Load from Google Fonts — `Space Grotesk:wght@300;400;500;600;700` and `Cormorant+Garamond:ital,wght@0,300;0,400;1,300;1,400`

---

## Files in This Package

| File | Purpose |
|---|---|
| `Rigal Shipping.html` | Full hi-fi design reference (single HTML file) |
| `README.md` | This handoff document |

---

## Notes for Developer

1. **Video background:** For production, replace the YouTube iframe with a self-hosted `.mp4` file (use `<video autoplay muted loop playsinline>`). The YouTube iframe approach works for demos but has restrictions in some environments.
2. **Tweaks:** The HTML file includes a Tweaks panel (bottom-right corner) where you can adjust accent color, gold color, video brightness, and body font in real time to explore variations before committing.
3. **Scroll animations:** The fade-up entrance animations use `IntersectionObserver` with `threshold: 0.08` and `rootMargin: '0px 0px -40px 0px'`. CSS transition: `opacity 0.8s ease, transform 0.8s ease` from `opacity:0; translateY(32px)`.
4. **Stat counter:** Uses `requestAnimationFrame` with easeOutCubic. Fires once per element on first intersection.
5. **Responsive:** Collapses to single-column at 1024px, mobile menu at 640px.
