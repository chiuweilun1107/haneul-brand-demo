# HANEUL (하늘) — Korean Minimalist Contemporary Fashion

> Editorial Korean fashion house. Off-white milk, charcoal ink, dusty-rose whisper.
> Quiet luxury. Generous negative space. Time slows down here.
> Reference: Hannam-dong galleries × Apgujeong ateliers × Andersson Bell × ADER ERROR's restraint.
>
> Schema: design-md v2 (13-section, 2026-05-26)
> Transformed from Linear.app (dark engineering) → HANEUL (light editorial)
> Source method: structural inversion — preserve Linear's discipline & restraint, invert palette/motion/voice

---

## §1 Visual Theme & Atmosphere

Off-white editorial gallery — like leafing through a hand-bound seasonal lookbook, not a typical e-commerce site.
The lightness isn't bright; it's quiet. Typography is the architecture — generous tracking, hairline serifs.
Motion is slow and intentional (400-800ms eases). The brand communicates "we made this for people who pause."

- **Overall mood**: Quiet, editorial, gallery-grade
- **Target feeling**: Stillness, intention, presence ("this rewards attention")
- **Visual personality**: Restrained, poetic, monochrome-warm with one whisper of rose
- **Reference comparables**: ADER ERROR's product page minimalism × Andersson Bell's lookbook restraint × COS editorial × 신세계 (Shinsegae) Jung-gu flagship pacing
- **Korean cultural cues**: 여백의 미 (the beauty of empty space), 한 (quiet melancholy), Bauhaus-meets-jeongja (정자)

---

## §2 Color Palette & Roles

### (A) Surface & Text Tokens

```css
:root {
  --bg:         #FAFAF7;  /* warm off-white milk — page base */
  --surface:    #FFFFFF;  /* product card / modal — pure white sits on warm bg */
  --surface-2:  #F2EFE9;  /* hover state / section divider — warm bone */
  --border:     #E5E1D8;  /* hairline dividers, input borders */
  --text:       #1A1A1A;  /* charcoal — never pure black (#000 is too harsh) */
  --text-muted: #6B6B6B;  /* secondary text, metadata, prices */
  --text-faint: #A8A6A0;  /* placeholder, disabled, captions */
}
```

### (B) Semantic Color Tokens

```css
:root {
  --accent:     #D9A89B;  /* HANEUL signature dusty rose — single accent (CTA on cream, ribbon, sale tag) */
  --accent-2:   #2E3A2E;  /* forest sage — limited use (footer, editorial chapter divider) */
  --neutral:    #8B7E6E;  /* warm taupe — body model skin reference, secondary type */
  --success:    #6B7E63;  /* sage green — order confirmed (NOT bright green) */
  --warning:    #B89968;  /* warm camel — backorder, ships-in-X-days */
  --danger:     #A85B5B;  /* muted clay red — error, sold-out badge (NOT firetruck red) */
}
```

**Color Notes**:
- Background type: ☑ Warm off-white (NEVER pure #FFF as bg — feels clinical)
- Accent strategy: ☑ Single accent (dusty rose) + 1 limited tertiary (sage). Never both at once on same fold.
- Gradient usage: ☑ None. (HANEUL inherits Linear's rule — gradients break editorial restraint)
- Black usage: ☑ Charcoal #1A1A1A only. Pure #000 is banned for type / surface / borders.

---

## §3 Typography Rules

**Font Families**:
- Display / Editorial: `'Spectral'` (serif, Korean web-safe via Pretendard fallback)
- Wordmark / Brand: `'Spectral'` weight 300, letter-spacing +0.15em
- Body / UI: `'Pretendard Variable'` (Korean-optimized sans, ko/en glyph unity)
- Korean text: `'Pretendard Variable'` (Hangul kerning is calibrated; never use Noto Sans KR — too generic)
- Numerals (prices, sizes): `font-variant-numeric: tabular-nums; font-feature-settings: 'lnum';`
- Mono / Code: `'JetBrains Mono'` weight 300 (only for size-charts, technical specs)

**Type Scale** (9 tokens; larger display jumps than Linear, editorial spacing):

```
display:     72px / 4.5rem    weight: 300   line-height: 1.05  letter-spacing: -0.02em   serif
editorial:   48px / 3rem      weight: 300   line-height: 1.15  letter-spacing: -0.01em   serif
subhead:     32px / 2rem      weight: 400   line-height: 1.25  letter-spacing:  0        sans
overline:    14px / 0.875rem  weight: 500   line-height: 1.4   letter-spacing: +0.18em  uppercase sans
lead:        20px / 1.25rem   weight: 400   line-height: 1.6   letter-spacing: -0.005em sans
body:        16px / 1rem      weight: 400   line-height: 1.7   letter-spacing:  0        sans
body_small:  14px / 0.875rem  weight: 400   line-height: 1.55  letter-spacing:  0        sans
caption:     12px / 0.75rem   weight: 500   line-height: 1.4   letter-spacing: +0.06em  sans
price:       18px / 1.125rem  weight: 500   line-height: 1.2   font-variant-numeric: tabular-nums
```

**Typography Rules**:
- Display + editorial headings: serif (Spectral light) for poetic weight
- UI / body: sans (Pretendard) for clarity and Korean glyph harmony
- Overline + caption: WIDE positive letter-spacing (+0.18em) — anchors the editorial mood
- Body line-height: **1.7** (extra-generous — air, slow reading)
- Max line length: **62ch** for editorial paragraphs
- Hangul (한글) at body size: use Pretendard 400 (Korean text needs a touch more weight than Latin to feel balanced)
- Brand wordmark "HANEUL": always Spectral light, +0.15em tracking, never bold, never italic
- Prices: tabular-nums always — ₩ 198,000 must align column-wise on product grid

---

## §4 Spacing & Layout

**Grid**:
- Max content width: 1440px (editorial pages), 1280px (product grid), 720px (article / story)
- Side margins: desktop 96px / tablet 48px / mobile 20px
- Product grid: 2-col mobile, 3-col tablet, 4-col desktop (NEVER 5+)
- Lookbook: full-bleed image, max-w none — image breathes

**Spacing Scale** (8px base, editorial bias toward larger steps):
```
4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 96 / 128 / 192
```
- Base unit: ☑ **8px (standard)** — but defaults to 24+ for editorial breathing

**Component Padding**:
- Tight: 8-12px (chips, sale tags, breadcrumbs)
- Default: 16-20px (buttons, inputs, nav items)
- Relaxed: 32-48px (product cards, modal content)
- Editorial: 64-96px (section vertical, between lookbook frames)

**Section Padding**:
- Hero: 128-192px vertical (cinematic stop)
- Standard: 96px vertical
- Product list rows: 24-32px vertical (NOT 8-12px — never feel rushed)

**Breakpoints**:
- Mobile: < 768px
- Tablet: 768-1024px
- Desktop: 1024-1440px
- Wide: > 1440px (lookbook full-bleed activates)

---

## §5 Border Radius Scale

(HANEUL uses near-zero radii — feels architectural, like a Bauhaus catalogue)

```
None    0px      Hero images, section blocks, full-bleed lookbook, hairline dividers
Sharp   2px      Buttons, inputs, sale tags (whisper of softness, almost imperceptible)
Soft    4px      Cards on cream surface — the maximum allowed
Pill    9999px   ONLY for: avatar (24px), filter chips (in collection page) — used sparingly
```

**Radius Philosophy**: ☑ Architectural / near-zero (≤4px throughout, except avatars and filter chips)
**Banned**: ✗ 8px+ rounded cards (feels SaaS, not editorial) ✗ Rounded-pill buttons (feels app, not atelier)

---

## §6 Elevation & Shadow

Inverted from Linear's dark-surface rule: on light bg, prefer subtle shadow + plenty of white space for hierarchy. NEVER heavy drop shadows — they feel ecommerce.

```css
--shadow-whisper:  0 1px 2px rgba(26, 26, 26, 0.04);                                  /* hover only */
--shadow-card:     0 2px 8px rgba(26, 26, 26, 0.05), 0 1px 2px rgba(26, 26, 26, 0.04); /* product card resting */
--shadow-elevated: 0 8px 24px rgba(26, 26, 26, 0.08), 0 2px 6px rgba(26, 26, 26, 0.05); /* dropdowns, mini-cart */
--shadow-overlay:  0 24px 48px rgba(26, 26, 26, 0.12);                                /* modal, image lightbox */
```

**Elevation via Whitespace** (preferred — gallery method):
- Layer 0: `--bg` (#FAFAF7 cream) — page
- Layer 1: 64-96px padding around content blocks (whitespace IS the elevation)
- Layer 2: `--surface` (#FFFFFF pure white) — product card, lifts visually against warm cream
- Layer 3: `--shadow-card` ONLY when card is interactive (hover state)

**Glassmorphism**: ☑ Not used. (HANEUL aesthetic is opaque, hand-printed catalogue — no frosted glass)

---

## §7 Components

### Buttons

- **Primary**: bg `#1A1A1A` charcoal, text `#FAFAF7` cream, radius Sharp (2px), padding 14px 32px, letter-spacing +0.08em uppercase 13px
  - Hover: bg `#2E3A2E` sage (subtle warm shift, 600ms ease-out)
  - Focus: outline 1px `#1A1A1A`, offset 3px
  - Disabled: 30% opacity
  - Active: bg `#0D0D0D` (nearly black, deliberate press feedback)
- **Secondary (Ghost-Outline)**: bg transparent, border 1px `#1A1A1A`, text `#1A1A1A`
  - Hover: bg `#1A1A1A`, text `#FAFAF7` (inversion, 400ms ease)
- **Quiet**: bg transparent, no border, text `#6B6B6B` with underline on hover (text-only link button)
- **CTA Accent (rare)**: bg `#D9A89B` dusty rose, text `#1A1A1A` — used for "Add to Bag" only
- **Sizes**: Small (32px, 8-16px pad, 11px label) | Medium (40px, 12-24px, 13px) | Large (48px, 14-32px, 14px)
- **Touch target mobile**: extend hit area with padding to reach 48px (never less)
- **Buttons NEVER**: ✗ pill-rounded ✗ have icons inside (icon = separate adjacent element) ✗ use gradient

### Cards / Product Tiles

- **Product Card (default)**:
  - Layout: ☑ image-on-top (4:5 portrait aspect ratio — fashion industry standard, NOT square)
  - bg `--surface` (#FFFFFF), padding 0 on image, 16px 0 on info block
  - Border: NONE on cream bg (whitespace separates), or 1px `--border` if grid-density mode
  - Radius: Sharp (2px) ONLY on image bottom corners if needed
  - Hover: image opacity 0.92 + reveal "Quick Look" overlay (centered button, 600ms cross-fade)
  - Info block: brand caption (overline 11px) → product name (subhead 16px regular) → price (price 16px medium) — vertical stack, left-aligned, 4px gap
- **Editorial Card (story / lookbook)**:
  - Full-bleed image (no padding), no card chrome
  - Caption overlay: bottom-left, 32px margin, overline + 1-line headline
- **Image position**: ☑ image-top portrait (NEVER image-bottom or image-side — feels off-brand)

### Inputs / Forms

- **Default**: bg `--surface` (#FFFFFF), border 1px `--border`, radius Sharp (2px), padding 14px 16px
- **Label**: above field, 12px overline uppercase, letter-spacing +0.1em, `--text-muted`
- **Placeholder**: `--text-faint`, NEVER italic
- **Hover**: border `--text-muted`
- **Focus**: border `--text` (charcoal), no glow ring (inherits Linear's anti-glow rule)
- **Error**: border `--danger` (muted clay), no bg fill change, helper text below in `--danger`
- **Disabled**: bg `--surface-2`, text `--text-faint`
- **Input height**: 48px (matches button medium) — generous for editorial pacing
- **Newsletter signup** (footer): underline-only input, no border box, charcoal underline 1px, transparent bg

### Chips / Filter Tags (Collection page only)

- **Inactive chip**: bg transparent, border 1px `--border`, text `--text-muted`, radius Pill (only place pill is allowed), padding 6px 16px, 12px
- **Active chip**: bg `--text` charcoal, text `--bg` cream, same shape
- **Hover**: border `--text`, text `--text`

### Lists (Order rows, Account pages)

- **Row height**: 56-72px (editorial breathing, NEVER 32-40px like Linear's data density)
- **Padding**: 24px vertical
- **Divider**: 1px `--border` between rows
- **Hover**: bg `--surface-2` warm bone, 400ms transition
- **No selection chips, no left accent bar** — HANEUL is for browsing, not data manipulation

### Checkboxes & Radio

- **Size**: 18px square (checkbox) / 18px circle (radio) — slightly larger than Linear's 16px for tactile feel
- **Unchecked**: border 1px `--text` charcoal (not faint), bg `--surface`
- **Checked**: bg `--text` charcoal, white checkmark
- **Focus**: outline 1px `--text`, offset 3px
- **Use case**: size selector, color selector, newsletter consent
- **Color swatch picker**: 28px circle, border 1px `--border`, no chrome, click → 2px ring of `--text` around circle

### Tooltips

- **Background**: `--text` charcoal (inverted)
- **Text**: `--bg` cream, 12px
- **Radius**: Sharp (2px), padding 8px 12px
- **Border**: none (charcoal on cream is enough contrast)
- **Max width**: 280px
- **Delay**: 400ms hover (slower than Linear — HANEUL doesn't rush)

### Badges

- **Sale tag**: bg `--accent` dusty rose, text `--text` charcoal, radius Sharp (2px), overline 11px "SALE −20%"
- **New tag**: bg transparent, border 1px `--text`, text `--text`, overline 11px "JUST IN"
- **Sold-out**: bg `--surface-2`, text `--danger`, overline 11px "품절 SOLD OUT" (bilingual)
- **Inventory dot**: 6px circle on product card, semantic color, NOT numeric

### Navigation (Top Bar)

- Position: ☑ fixed top horizontal nav (NOT sidebar like Linear — HANEUL is a storefront, not a tool)
- Height: 72px desktop, 56px mobile
- Background: `--bg` cream (no border on scroll, no shadow until scroll-y > 80 then `--shadow-whisper`)
- Layout: logo center | menu left (SHOP / LOOKBOOK / JOURNAL) | utility right (SEARCH / ACCOUNT / BAG)
- Active item: charcoal text + 1px underline (NOT background fill)
- Menu typography: overline 12px uppercase, letter-spacing +0.12em
- Logo placement: ☑ centered (editorial signature)
- Mobile: hamburger left, logo center, bag right
- Mobile drawer: slides from left, full-height, charcoal bg, cream text (inverted — feels intentional)

### Hero Section

- Layout: ☑ image-led full-bleed (NOT text-centered like Linear)
- Aspect ratio: 16:9 desktop / 4:5 mobile
- Image: editorial photograph (model in product) with seasonal context
- Headline overlay: bottom-left, 32-48px margin, white text on darkened image edge (NO scrim — choose images with naturally dark lower-left)
- Headline type: editorial 48px serif light, 1-line max
- CTA: ghost-outline white below headline, max 2 buttons (1 primary collection + 1 secondary journal)
- NO 3D, NO illustration, NO video autoplay (HANEUL allows hover-to-play 8s seasonal film on lookbook only)

### Newsletter Footer

- Layout: 2-column desktop (left: brand wordmark + manifesto 1-line | right: email input + subscribe)
- Background: `--accent-2` forest sage (the only place sage takes over)
- Type color: `--bg` cream
- Input: underline-only, transparent bg, cream underline
- Submit: text-only "SUBSCRIBE →" overline 12px

---

## §8 Motion & Animation

HANEUL's signature: **slow + ease-out**. The opposite of Linear. Motion makes you breathe with the brand, not react to it.

**Easing**:
- Standard: `cubic-bezier(0.16, 1, 0.3, 1)` (custom — fast-then-very-slow, "exhale" feel)
- Image fade: `cubic-bezier(0.4, 0, 0.2, 1)` (standard)
- Banned: ☑ no spring, ☑ no overshoot, ☑ no bounce (these are youthful/playful — HANEUL is quiet)

**Duration Scale**:
```
quick    200ms    nav underline hover, chip toggle
default  400ms    button hover, color shift, input focus
slow     600ms    product card image dim, modal entrance
cinema   800ms    hero image cross-fade, lookbook slide
glacial  1200ms   editorial section reveal on scroll (paragraph fade-in)
```

**Common Patterns**:
- **Product card hover**: image opacity 1.0 → 0.92 (600ms ease-out) + "Quick Look" overlay fades in (400ms delay 100ms)
- **Hero image rotation**: 5s static → 800ms cross-fade to next image (lookbook style, never slide)
- **Modal open**: 600ms ease-out, opacity 0→1 + translateY 12px→0 (gentle rise)
- **Page transition**: 400ms fade through cream (no slide) — feels like turning a page
- **Add to bag**: bag icon scales 1.0 → 1.08 → 1.0 (300ms total, single pulse, no bounce)

**Reduce Motion**: honor `prefers-reduced-motion: reduce` → disable all reveals, keep only opacity (no transform)

---

## §9 Iconography

**Library**: ☑ Custom hairline set OR Phosphor Icons "thin" variant (1px stroke)
- NEVER Lucide / Heroicons (1.5-2px — too SaaS, breaks editorial restraint)
- NEVER Tabler / Feather at default weight

**Stroke width**: **1px** (hairline — uniform across all sizes; if site renders too thin on retina, fall back to 1.2px BUT never 1.5+)

**Sizes**:
```
xs    14px   inside chips
sm    16px   inline with body text
md    20px   nav utility (search, account, bag) — HANEUL most common
lg    24px   section header accent (rare)
xl    32px   empty state (e.g., "your bag is empty")
```

**Style Rule**:
- ☑ Outlined ONLY, never filled (filled icons feel app-grade, not editorial)
- Color: default `--text` charcoal (NOT muted — HANEUL icons earn their visual weight)
- Hover: no color change, no fill — only subtle 0.7 → 1.0 opacity if needed
- ✗ Never use emoji as UI icon
- ✗ Never use animated icons (no Lottie spinners; use 8px circle + opacity pulse for loading)

**Special icons**:
- Bag (cart): hairline shopping bag outline, NOT cart-with-wheels
- Account: hairline person outline, NOT filled silhouette
- Search: hairline magnifying glass, 1px stroke
- Wishlist (optional): hairline heart outline, NEVER filled even when active (use small dot indicator instead)

---

## §10 Do's and Don'ts

1. **Do** use Spectral light serif for all editorial headlines (display + editorial scale)
2. **Do** use Pretendard for all Korean and English body — never mix with Noto Sans KR
3. **Do** keep transitions ≥400ms (the opposite rule from Linear; HANEUL is slow)
4. **Do** prefer whitespace over chrome (no borders / no shadows for hierarchy; pad more instead)
5. **Do** use charcoal #1A1A1A — never pure #000 — for type and surfaces
6. **Do** show product images in 4:5 portrait aspect ratio (industry standard for fashion)
7. **Do** apply tabular-nums to all prices and sizes (₩ 198,000 must align in grid)
8. **Don't** ✗ Use gradients (any — even subtle cream-to-white)
9. **Don't** ✗ Use rounded pill buttons (use Sharp 2px or text-only ghost)
10. **Don't** ✗ Use heavy drop shadows on cards (max `--shadow-card` and only on hover/interactive)
11. **Don't** ✗ Use bright primary colors (no red, no royal blue, no neon — keep muted)
12. **Don't** ✗ Animate icons or use spring easing
13. **Don't** ✗ Auto-play video on hero (lookbook frame allows hover-to-play, 8s max)
14. **Don't** ✗ Stack more than 4 columns in product grid
15. **Don't** ✗ Use emoji in UI, marketing copy, or product names
16. **Don't** ✗ Bold body text for emphasis (italicize in Spectral for emphasis, or change color to charcoal from muted)
17. **Don't** ✗ Make CTAs scream — keep them confident, charcoal, no shadow, no glow

---

## §11 Responsive Behavior

**Navigation**:
- Desktop: fixed top horizontal, centered logo, 72px height
- Tablet (768-1024): same as desktop but tighter horizontal padding (48px)
- Mobile: hamburger left + centered logo + bag right, 56px height, drawer slides from left

**Hero / Landing**:
- Desktop: full-bleed 16:9, headline bottom-left 48px margin, type 48px serif
- Mobile: full-bleed 4:5 (portrait — fashion-friendly on phone), headline 32px serif, CTAs stack vertically

**Product Grid**:
- Mobile: 2-col, 16px gap, image 4:5
- Tablet: 3-col, 24px gap
- Desktop: 4-col, 32px gap (never 5+)
- Filter / sort: sticky top below nav on desktop, drawer-from-right on mobile

**Editorial / Journal**:
- All breakpoints: max-w 720px centered, generous 96-128px section padding, 62ch line length

**Typography**:
- Display mobile: 48px (66% of desktop 72px)
- Editorial mobile: 32px (66% of desktop 48px)
- Body: 16px across all breakpoints (never shrink below)

**Touch Targets**:
- Minimum 48×48px (one step above Linear's 44 — gentler taps for slower pace)
- Spacing between targets: ≥12px

---

## §12 Agent Prompt Guide

**Bias toward**:
- Off-white (#FAFAF7) page bg + pure white (#FFFFFF) product cards — never invert
- Serif (Spectral light, 300 weight) for ALL editorial / display headlines
- Sans (Pretendard) for ALL body and UI labels
- Charcoal (#1A1A1A) for text — never pure #000
- Single accent dusty rose (#D9A89B) used sparingly (CTA-accent only, or one ribbon detail)
- Sage (#2E3A2E) limited to footer or one chapter-divider per page
- Image-led product cards in 4:5 portrait aspect ratio
- Generous whitespace (64-128px section padding) — let pages breathe
- Slow motion (400-800ms ease-out) — exhale, don't react
- Hairline icons (1px stroke, Phosphor thin or custom)
- Tabular nums for all prices and sizes (₩ 198,000 grid-aligns)
- Bilingual touches where natural: 품절 SOLD OUT, 신상 JUST IN, 가을 컬렉션 FALL COLLECTION

**Reject**:
- ✗ No dark mode (HANEUL is a daylight brand; do not invert to dark)
- ✗ No bright / saturated colors (no red, no royal blue, no neon, no fuchsia)
- ✗ No gradients of any kind
- ✗ No rounded-pill buttons (Sharp 2px max except chips + avatars)
- ✗ No heavy shadows or "elevation" via shadow on cards
- ✗ No motion under 200ms (feels rushed) or over 1500ms (feels broken)
- ✗ No spring / overshoot / bounce easing
- ✗ No icons heavier than 1.2px stroke
- ✗ No emoji in UI or product names
- ✗ No autoplay video / no parallax scrolling
- ✗ No carousel with auto-advance < 6s
- ✗ No 5+ column product grid
- ✗ No filled icons (only outlined hairline)
- ✗ No pure #000 text or #FFF bg surface (always warm #1A1A1A / #FAFAF7)
- ✗ No Noto Sans KR (use Pretendard for Korean; it's calibrated for ko/en harmony)
- ✗ No SaaS-feeling "Get Started" CTAs (use "SHOP NEW ARRIVALS" or "둘러보기 BROWSE")

---

## §13 Skills（特效程式碼庫）

### Skill A: Slow Editorial Image Cross-Fade (Hero rotation)

```css
.hero-frame {
  position: absolute;
  inset: 0;
  opacity: 0;
  transition: opacity 800ms cubic-bezier(0.4, 0, 0.2, 1);
}
.hero-frame.active {
  opacity: 1;
}
```

```javascript
const frames = document.querySelectorAll('.hero-frame');
let i = 0;
setInterval(() => {
  frames[i].classList.remove('active');
  i = (i + 1) % frames.length;
  frames[i].classList.add('active');
}, 5800);
```

**使用時機**: Hero section with 3-5 seasonal lookbook frames — never slide, only cross-fade
**使用元素**: ☑ hero, lookbook frame stack, brand story image rotation

---

### Skill B: Product Card Quiet Hover (image dim + overlay reveal)

```css
.product-card {
  position: relative;
  cursor: pointer;
}
.product-card .product-image {
  transition: opacity 600ms cubic-bezier(0.16, 1, 0.3, 1);
}
.product-card:hover .product-image {
  opacity: 0.92;
}
.product-card .quick-look {
  position: absolute;
  inset: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 400ms cubic-bezier(0.16, 1, 0.3, 1) 100ms;
  pointer-events: none;
}
.product-card:hover .quick-look {
  opacity: 1;
  pointer-events: auto;
}
.quick-look button {
  background: #FAFAF7;
  color: #1A1A1A;
  padding: 14px 32px;
  border: none;
  font-size: 12px;
  letter-spacing: 0.12em;
  text-transform: uppercase;
}
```

**使用時機**: All product grid tiles — establishes HANEUL's "quiet luxury" hover
**使用元素**: ☑ product cards, lookbook tiles, related-products carousel

---

### Skill C: Glacial Section Reveal on Scroll (editorial paragraph fade)

```css
[data-reveal] {
  opacity: 0;
  transform: translateY(24px);
  transition: opacity 1200ms cubic-bezier(0.16, 1, 0.3, 1),
              transform 1200ms cubic-bezier(0.16, 1, 0.3, 1);
}
[data-reveal].revealed {
  opacity: 1;
  transform: translateY(0);
}
@media (prefers-reduced-motion: reduce) {
  [data-reveal] {
    opacity: 1;
    transform: none;
    transition: none;
  }
}
```

```javascript
const observer = new IntersectionObserver(
  entries => entries.forEach(e => {
    if (e.isIntersecting) {
      e.target.classList.add('revealed');
      observer.unobserve(e.target);
    }
  }),
  { threshold: 0.2, rootMargin: '0px 0px -10% 0px' }
);
document.querySelectorAll('[data-reveal]').forEach(el => observer.observe(el));
```

**使用時機**: Editorial pages (journal, brand story, lookbook captions) — slow, deliberate appearance
**使用元素**: ☑ section headings, paragraphs, full-bleed image captions, chapter dividers

---

## Brand Asset References

| File | Use | Path |
|------|-----|------|
| `01-logo.png` | Wordmark — header, footer, OG image | `~/Downloads/haneul-brand/01-logo.png` |
| `02-hero.png` | Homepage hero, OG cover image | `~/Downloads/haneul-brand/02-hero.png` |
| `03-product-flatlay.png` | Product page sample, journal article cover | `~/Downloads/haneul-brand/03-product-flatlay.png` |
| `04-lookbook.png` | Lookbook portrait, about page, lookbook tile | `~/Downloads/haneul-brand/04-lookbook.png` |

**Image style guide** (for future asset generation):
- All photography: muted warm palette (bone white + cream + dusty rose + warm taupe + sage)
- Lighting: soft natural daylight, never harsh studio strobe
- Model direction: contemplative, off-camera gaze; never grinning, never edgy/aggressive
- Color grade: medium-format film aesthetic, light grain, slightly desaturated
- Composition: generous negative space (right or top third often empty)
- Aspect ratios: 4:5 portrait for product / lookbook, 16:9 for hero on desktop, 1:1 for logo + flatlay

---

*Generated by design-md skill v2 — Linear.app structural inversion → HANEUL Korean fashion brand*
*Transformation date: 2026-05-27*
*Source: examples/linear-design.md (v2 13-section) → HANEUL identity by palette/typography/motion/voice inversion*
