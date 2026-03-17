# CLAUDEME - Technical Change Log

**Project:** Morito Chocolates - Shopify Theme Infrastructure
**Managed by:** Claude Code (Impulsa Lab)

---

## Session: 2026-03-07

### Changes Made

#### 1. Slideshow Glassmorphism Enhancement
- **File:** `sections/slideshow.liquid`
- **Change:** Updated `.slideshow__text.glass-effect` background opacity from `0.88` to `0.65` for a true Glassmorphism effect
- **Specs applied:**
  - `background: rgba(249, 245, 240, 0.65)` (Organic Cream palette with transparency)
  - `backdrop-filter: blur(12px); -webkit-backdrop-filter: blur(12px)`
  - `border: 1px solid rgba(255, 255, 255, 0.3)` (subtle border)
  - Text color `#332520` (Dark Mocha) maintained for legibility
- **Rationale:** More transparent glass effect creates a premium, modern look while keeping text readable against the blurred background

#### 2. Documentation Initialization
- **Files:** `CLAUDEME.md` (created), `README.md` (reviewed, no changes needed)
- **Purpose:** Establish persistent technical documentation for ongoing development sessions

#### 3. Seasonal Content Cleanup - Announcement Bar
- **File:** `config/settings_data.json`
- **Change:** Replaced Valentine's Day promotional text in announcement bar with evergreen brand messaging
- **Old text:** `Pre-Orders Now Open — Get your order before Valentine's Day ... Ships February 9 | Free Shipping...`
- **New text:** `Crafted in Brooklyn. Shipped Nationwide. | Premium Plant-Based Chocolate | Free Shipping on orders over $65 | Corporate & bulk orders: info@moritochocolates.com`
- **Skipped:** Valentine-related URLs in `page.find-us.json` and `settings_data.json` (legitimate press article links from Greenpointers, not promotional content)
- **Rationale:** Remove time-sensitive seasonal content; replace with brand-reinforcing, atemporal messaging

#### 4. Integrated Corporate Tracker (Marquee on Cacao Plantation)
- **Files:** `sections/image-banner.liquid`, `templates/index.json`
- **Change:** Glassmorphic corporate logo marquee, vertically centered on the cacao plantation image
- **Logo assets:** `file_url` with `asset_url` fallback for maximum compatibility
  - `Cypresshills logo.png`, `ford foundation logo.png`, `Hotbread Kitchen logo.png`, `Macys logo.png`
  - `mexico now logo.png`, `One Horizon logo.png`, `Porcelanosa logo.png`, `TD Bank logo.png`
- **Design specs (v5 — Luxury Execution):**
  - Banner: `max-height: 400px` desktop / `300px` mobile — narrow, cinematic
  - Strip: `rgba(255, 255, 255, 0.92)` — pure white, logo backgrounds blend seamlessly
  - No backdrop-filter — clean fusion, no glass distortion
  - No borders — invisible integration with image
  - Strip height: `100px` desktop / `70px` mobile
  - Logo size: `45px` desktop / `30px` mobile — generous negative space
  - Logo filter: `grayscale(100%) opacity(0.55)` — elegant, shapes fully legible
  - Hover: full color + subtle scale(1.05) with 0.4s ease
  - Infinite scroll: 35s cycle, configurable via schema

## Session: 2026-03-09

### Changes Made

#### 1. Corporate Marquee Logo Update
- **File:** `sections/image-banner.liquid`
- **Change:** Updated all 8 logo URLs to use edited versions with transparent backgrounds (`_-_Edited.png`)

#### 2. Decadent Flavors — Floating Levitation Effect (Marketing Identity Pillar)
- **Files:** `sections/image-with-text.liquid`, `templates/index.json`
- **Change:** Replaced animated chocolate border with high-end floating product effect
- **Image:** Switched from `MatchaStrawberryclear.png` to `MatchaStrawberryclear_-_Edited.jpg` (transparent background)
- **New schema setting:** `floating_image` checkbox (independent of `animated_border`)
- **Design specs:**
  - No borders, no containers — image floats freely
  - Aura `::before` pseudo-element: `radial-gradient(circle, rgba(214, 138, 89, 0.15) 0%, rgba(249, 245, 240, 0) 70%)`
  - Resting state: `filter: drop-shadow(0 10px 15px rgba(51, 37, 32, 0.2))`, `transition: all 0.6s ease-out`
  - Hover state: `transform: translateY(-15px) scale(1.03)`, `filter: drop-shadow(0 25px 25px rgba(51, 37, 32, 0.15))`
  - Section background: Organic Cream `#F9F5F0`
  - Headings: Playfair Display enforced via `:has()` selector
  - Mobile: touch `:active` fallback with reduced lift
  - `prefers-reduced-motion`: transitions disabled

#### 3. Mobile Carousel Zoom Optimization
- **File:** `sections/slideshow.liquid`
- **Change:** Reduced Ken Burns animation intensity on mobile for better product visibility
- **Specs:**
  - New `kenBurnsMobile` keyframe: max scale `1.04` (was `1.08` from desktop)
  - `object-position: center 35%` (was `30%`) — more breathing room
  - Product images feel complete, not zoomed-in on faces/details

#### 4. Text Overlay Transparency Refinement
- **File:** `sections/slideshow.liquid`
- **Change:** Increased transparency on all text containers for better photo integration
- **Specs:**
  - Glass effect (desktop): `rgba(249, 245, 240, 0.45)` (was `0.65`)
  - Subtitle background: `rgba(51, 37, 32, 0.40)` (was `0.45`)
  - Button background: `rgba(51, 37, 32, 0.45)` (was `0.55`)
  - Priscilla's product photography textures now visible through overlays

#### 5. Announcement Bar Height Increase
- **File:** `sections/announcement-bar.liquid`
- **Change:** Increased vertical padding for bolder, more modern presence
- **Specs:**
  - Desktop padding: `1.4rem` (was `1rem`) — +40% taller
  - Mobile padding: `1.15rem` (was `0.9rem`) — +28% taller
  - Text remains centered via flexbox alignment

#### 6. Best Sellers — Luxury Polish with Clean Assets (Sprint Close)
- **Files:** `sections/best-sellers.liquid`, `templates/index.json`
- **Change:** Updated product images to edited transparent-background PNGs via direct CDN URLs; desktop UI refinements
- **New images (CDN-injected):**
  - Hazelnut: `Hazelnut_best_sellers.png`
  - Coconut: `Coconut_Best_sellers.png`
  - Salted Peanut: `Salted_best_sellers.png`
- **New schema setting:** `image_url` (direct CDN URL, takes priority over `image_file` asset)
- **Design specs:**
  - Image levitation: `filter: drop-shadow(0 15px 20px rgba(51, 37, 32, 0.12))`
  - Desktop (≥990px): price `1.4rem`, button `1.1rem` / `font-weight: 700` / `padding: 16px 36px`
  - Button: Roasted Rust `#D68A59`, white text, Montserrat bold (unchanged, confirmed)
  - Card background: Organic Cream `#F9F5F0` (unchanged, confirmed)

#### 7. Best Sellers — 3D Perspective Tilt & Viewport Entrance Animation
- **File:** `sections/best-sellers.liquid`
- **Change:** Full rewrite of interaction system — replaced flat levitate-hover with 3D perspective tilt + IntersectionObserver
- **3D Perspective Tilt (Desktop):**
  - `transform: perspective(1000px) rotateX(var(--rotate-x)) rotateY(var(--rotate-y))`
  - CSS custom properties driven by JS `mousemove` — max rotation ±8° Y / ±6° X
  - `transform-style: preserve-3d` on card, wrapper, link, info
  - Image: `transform: translateZ(50px) scale(1.04)` on hover — pops out of card plane
  - Info text: `translateZ(25px)` / Button: `translateZ(30px)` — layered depth
  - `mouseleave` resets to `0deg` with CSS transition easing
- **Desktop Scale (≥990px):**
  - Image wrapper: `scale(1.1)` — 110% of original
  - Product title: `1.8rem` Playfair Display (was `1.25rem`)
  - Price: `1.5rem` font-weight 500, Dark Mocha (was `1rem`)
  - Button: `1.1rem` / 700 weight / `16px 36px` padding
- **Mobile Viewport Entrance (≤749px):**
  - IntersectionObserver: `threshold: 0.15`, `rootMargin: 0px 0px -40px 0px`
  - Cards start `opacity: 0; translateY(40px)` → `.is-visible` triggers `opacity: 1; translateY(0)`
  - 0.7s cubic-bezier transition, one-shot (unobserve after trigger)
  - Fallback: if IntersectionObserver unavailable, cards visible immediately
  - Generous spacing: gap `45px`, padding `28px`, title `1.35rem`, price `1.15rem`
- **Accessibility:** `prefers-reduced-motion` disables all transitions and forces visible state

#### 8. Best Sellers — Luxury Reconstruction (4K + Intensified 3D)
- **File:** `sections/best-sellers.liquid`
- **Change:** Image quality preservation, doubled tilt intensity, upgraded typography hierarchy
- **4K Quality Preservation:**
  - `object-fit: contain` (was `cover`) — no cropping, full product visible
  - Image dimensions: `1200×1200` (was `800×800`) — sharper on retina
  - Removed all `opacity` filters on price — full vivid Dark Mocha
  - Resting drop-shadow: `0 18px 25px rgba(51,37,32, 0.18)` — deeper presence
- **3D Intensity (Desktop):**
  - `perspective(1200px)` (was `1000px`) — wider depth field
  - Image hover: `translateZ(80px) scale(1.05)` (was `50px / 1.04`) — product pops off screen
  - Dynamic hover shadow: `drop-shadow(0 35px 40px rgba(51,37,32, 0.25))` — shadow retreats as product lifts
  - Card shadow on hover: `0 40px 80px -25px rgba(51,37,32, 0.28)` — dramatic depth
  - Info: `translateZ(35px)` / Button: `translateZ(40px)` — increased layer separation
  - JS tilt: ±14° Y / ±10° X (was ±8° / ±6°) — dramatic but controlled
- **Typography Hierarchy (Desktop ≥990px):**
  - Product title: `2.2rem` Playfair Display, `letter-spacing: -0.02em` (was `1.8rem`)
  - Price: `1.8rem`, `font-weight: 600`, full opacity (was `1.5rem` / 500 / 0.75)
  - Button: `15px 40px` padding, Roasted Rust `#D68A59` vibrante

#### 9. Best Sellers — Seamless Cards + Scroll Highlight
- **File:** `sections/best-sellers.liquid`
- **Change:** Removed white card backgrounds, dark chocolate price, scroll-triggered highlight for all devices
- **Visual fixes:**
  - Card, image-wrapper, info: `background: transparent` — cards fuse with Organic Cream section
  - Card `box-shadow: none` in resting state — clean, borderless
  - Price color: `#3E2117` (dark chocolate) with `font-weight: 600`
- **Scroll entrance (all devices):**
  - IntersectionObserver now runs on desktop AND mobile (was mobile-only)
  - Staggered entrance: cards 1/2/3 enter with 0s / 0.15s / 0.3s delay
  - Cards start `opacity: 0; translateY(30px)` → `.is-visible` fades in
- **Hover refinements:**
  - Card scales `1.04` on hover for emphasis
  - Product title transitions to Warm Copper `#D68A59` on hover
  - Image gets `brightness(1.06)` — chocolate pops with warmth

#### 10. Best Sellers — Kinetic Luxury Animation + Dark Mocha Pricing
- **File:** `sections/best-sellers.liquid`
- **Change:** Triple-spin hover animation, price emphasis, 4K rendering optimization
- **`kineticLuxury` keyframe:**
  - 3 full rotations (1080°) on Y-axis + scale to 1.3 in 0.5s
  - Elastic bounce: `cubic-bezier(0.34, 1.56, 0.64, 1)` — overshoot at 70% then settle
  - Keyframe structure: 0% → 70% spin+zoom → 85% slight shrink (1.22) → 100% final (1.3)
- **Price styling:**
  - Color: `#3E2117` (dark chocolate), `font-weight: 700`
  - Hover: `transform: scale(1.2)` with elastic easing — 20% growth guides eye to purchase
  - `display: inline-block` for transform support
- **Title hover:** transitions to Warm Copper `#D68A59`
- **Image quality:** `image-rendering: -webkit-optimize-contrast` — zero blur during animation

#### 11. Best Sellers — Always-Visible 'ADD TO CART' CTA
- **File:** `sections/best-sellers.liquid`
- **Change:** Button now always visible (was hidden until hover); redesigned for high conversion
- **Button specs:**
  - Background: Warm Copper `#D68A59`, text: `#FFFFFF`
  - Font: Montserrat 700, `1rem`, uppercase, `letter-spacing: 0.1em`
  - Padding: `15px 30px`, `border-radius: 4px`, `border: none`
  - Hover: `#BF7A4E` (10% darker Copper) + `scale(1.05)` + `box-shadow` glow
  - 3D sync: `translateZ(30px)` on card hover — button floats on its own depth layer
  - Mobile: full-width (`width: 100%`), slightly smaller padding
  - Desktop (≥990px): `1.1rem`, `15px 40px`
- **Removed:** `opacity: 0` / `pointer-events: none` — button is always clickable

---

## Session: 2026-03-17

### Changes Made

#### 1. Editorial Text Box — Desktop Translucent Overlay
- **File:** `sections/slideshow.liquid`
- **Change:** Applied translucent editorial box to ALL slideshow text containers on desktop (≥750px)
- **Specs:**
  - `background: rgba(230, 220, 210, 0.65)` — warm translucent cream
  - `backdrop-filter: blur(8px); -webkit-backdrop-filter: blur(8px)`
  - `padding: 3rem; border-radius: 8px`
  - Heading colors: `.first` → Warm Copper `#D68A59`, `.second/.third` → Dark Mocha `#332520`
  - Subtitle: `color: #332520`, no text-shadow (clean on translucent bg)

#### 2. Viewport Auto-Fit — Desktop & Mobile
- **File:** `sections/slideshow.liquid`
- **Change:** Slide height now fills exactly one viewport minus header + announcement bar
- **Desktop (≥750px):**
  - `height: calc(100vh - var(--header-height, 80px) - var(--announcement-bar-height, 40px))`
  - Image: `object-fit: cover` with absolute positioning — no zoom overflow
- **Mobile (≤749px):**
  - `height: calc(100dvh - var(--header-height, 60px) - var(--announcement-bar-height, 40px))`
  - Uses CSS custom properties for dynamic header/bar heights
- **Small phones (≤374px):**
  - Fallback defaults: `--header-height: 55px`, `--announcement-bar-height: 35px`

#### 3. Slide Cleanup — Limited to 3 Slides
- **File:** `templates/index.json`
- **Change:** Removed `slide-4-coconut` (Coconut Cherry) from slideshow block_order and block definitions
- **Remaining slides:** Sticks (hero), Mini Cups (matcha/strawberry), Corporate Gifting
- **Rationale:** 3 slides = tighter messaging, faster perceived rotation, less cognitive load

#### 4. Unified Glassmorphism Box — All Slides Identical
- **File:** `sections/slideshow.liquid`
- **Change:** Strict unification so slides 1, 2, and 3 share identical translucent box style
- **Specs (desktop ≥750px):**
  - `background: rgba(249, 245, 240, 0.55) !important` — slightly higher opacity for dark-photo contrast
  - `backdrop-filter: blur(10px) !important` — unified blur (was 8px general / 12px glass-effect)
  - `border: 1px solid rgba(255, 255, 255, 0.3) !important` — matching glass edge
  - `.glass-effect` block updated to same values (was `0.45` opacity, `blur(12px)`)
- **Text colors reverted:**
  - Removed Luminous Gold `#C5A059` and `text-shadow` from previous commit
  - All headings: Dark Mocha `#332520`; `.first` heading: Warm Copper `#D68A59`
- **Subheading upgrade:** `font-size: 1.15rem`, `font-weight: 500`, `color: #332520`
- **Rationale:** All 3 slides now look identical in text box treatment; gold was inconsistent with brand palette

#### 5. (Reverted) Luminous Gold Hero Text
- **File:** `sections/slideshow.liquid`
- **Change:** Replaced Dark Mocha heading color with Luminous Gold `#C5A059` on desktop glassmorphism text box
- **Specs:**
  - All `h2.banner__heading` inside `.slideshow__text.banner__box`: `color: #C5A059`
  - Micro-shadow: `text-shadow: 0 2px 4px rgba(51, 37, 32, 0.4)` — separates text from hazelnut/product details in background
  - `.first` heading also uses `#C5A059` for unified gold treatment
- **Rationale:** Dark Mocha text on translucent glass was hard to read against dark product photography; gold provides luxury contrast while maintaining brand identity

#### 5. Glassmorphism Refinement — Lighter, Luxury Organic
- **File:** `sections/slideshow.liquid`
- **Change:** Reduced text box opacity to match Corporate Gifting slide aesthetic across all slides
- **Specs:**
  - `background: rgba(249, 245, 240, 0.4)` (was `rgba(230, 220, 210, 0.65)` — too opaque)
  - Added `border: 1px solid rgba(255, 255, 255, 0.25)` for subtle glass edge
  - Added `box-shadow: 0 8px 32px rgba(51, 37, 32, 0.1)` for depth
  - `backdrop-filter: blur(8px)` and `padding: 3rem` preserved
- **Rationale:** True glassmorphism — image textures visible through text overlay

#### 5. Best Sellers — Simplified Hover (Removed Kinetic Spin)
- **File:** `sections/best-sellers.liquid`
- **Change:** Eliminated `kineticLuxury` triple-spin animation; replaced with subtle zoom + shadow
- **Removed:**
  - `@keyframes kineticLuxury` (1080° spin + elastic bounce)
  - 3D perspective tilt JS (`mousemove` rotation tracking, `--rotate-x/--rotate-y` vars)
  - `transform-style: preserve-3d` on card, image-wrapper, image-link, info
  - `translateZ()` depth layers on hover
  - Price `scale(1.2)` elastic bounce on hover
  - Image wrapper `scale(1.1)` resting state
- **New Desktop hover:**
  - Card: `transform: scale(1.05)` + `box-shadow: 0 20px 40px rgba(0,0,0,0.1)`
  - Image: `transform: scale(1.08)` within `overflow: hidden` container
  - Title transitions to Warm Copper `#D68A59`
- **New Mobile scroll highlight:**
  - IntersectionObserver with `threshold: 0.6` detects center-most card
  - `.is-active` class applies same zoom + shadow as desktop hover
  - Cards gain/lose `.is-active` dynamically as user scrolls
- **Rationale:** Kinetic spin was distracting; subtle zoom feels premium and organic

---

### Sprint Summary — 2026-03-09
All 10 optimization rounds completed:
1. Corporate Marquee — transparent-background logos
2. Decadent Flavors — floating levitation effect with aura
3. Mobile Carousel — reduced Ken Burns zoom
4. Text Overlay Transparency — glass effect + subtitle + button
5. Best Sellers — luxury polish with clean edited assets
6. Best Sellers — 3D perspective tilt + IntersectionObserver entrance
7. Best Sellers — 4K quality reconstruction + intensified 3D + typography hierarchy
8. Best Sellers — seamless transparent cards + scroll highlight + dark chocolate price
9. Best Sellers — kinetic luxury triple-spin animation + dark mocha pricing
10. Best Sellers — always-visible high-contrast 'ADD TO CART' CTA
