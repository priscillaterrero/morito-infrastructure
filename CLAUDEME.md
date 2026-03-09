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

---

### Sprint Summary — 2026-03-09
All 7 optimization rounds completed:
1. Corporate Marquee — transparent-background logos
2. Decadent Flavors — floating levitation effect with aura
3. Mobile Carousel — reduced Ken Burns zoom
4. Text Overlay Transparency — glass effect + subtitle + button
5. Best Sellers — luxury polish with clean edited assets
6. Best Sellers — 3D perspective tilt + IntersectionObserver entrance
7. Best Sellers — 4K quality reconstruction + intensified 3D + typography hierarchy
