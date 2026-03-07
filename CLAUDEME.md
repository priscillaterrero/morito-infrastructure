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
- **Change:** Glassmorphic corporate logo marquee injected into the image-banner section (cacao plantation), lower third
- **Logo assets (Shopify Files, loaded via `file_url`):**
  - `Cypresshills logo.png`, `ford foundation logo.png`, `Hotbread Kitchen logo.png`, `Macys logo.png`
  - `mexico now logo.png`, `One Horizon logo.png`, `Porcelanosa logo.png`, `TD Bank logo.png`
- **Design specs:**
  - Background: `rgba(249, 245, 240, 0.82)` (Organic Cream 82% opacity)
  - `backdrop-filter: blur(10px)` — plantation image visible through the silk-like strip
  - `border-top: 1px solid rgba(255, 255, 255, 0.3)` — subtle glass edge
  - Logo filter: `brightness(0) saturate(100%) invert(13%) sepia(18%) saturate(1042%) hue-rotate(324deg) brightness(96%) contrast(90%)` — Dark Mocha (#332520) tone
  - Infinite horizontal scroll animation (35s cycle, configurable via schema)
  - Hover: pauses animation, removes filter to show original logo colors
- **Schema:** `show_marquee` toggle, `marquee_heading` text, `marquee_speed` range (15-60s)
- **Accessibility:** `prefers-reduced-motion` wraps to static grid, duplicate items hidden with `aria-hidden`
- **Rationale:** Corporate social proof integrated directly on brand origin imagery; glassmorphic strip reinforces premium positioning
