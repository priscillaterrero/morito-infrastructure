
# 🍫 Morito Chocolates: Digital Infrastructure V1

**Managed by:** Impulsa Lab  
**Status:** 🟢 Active / Production  
**Environment:** Shopify Online Store 2.0  

---

### 📂 Project Overview
This repository contains the source code for Morito's E-commerce ecosystem. It serves as the **Single Source of Truth** for the theme architecture, ensuring version control and safe deployments.

### 🛠 Tech Stack
* **Core:** Shopify Liquid (Theme 2.0 Standards)
* **Styling:** Tailwind CSS / Custom SCSS
* **Logic:** Vanilla JavaScript (Inventory & Bundles logic)
* **Integration:** GitHub Actions ↔ Shopify Integration

### 🚀 Key Modules (Phase 1 & 2)
1.  **Inventory Logic:** Custom rules for "On-Demand" production buffering.
2.  **Bundles System:** Component logic to handle composite products without overselling.
3.  **UX Enhancements:** Custom cursors, mobile-first animations, and cart upselling algorithms.
4.  **Clean Ingredients:** Streamlined headline + product image layout with horizontal brand attribute badges (vegan, zero preservatives, gluten free, soy free, non-GMO, palm oil free). Italic/bold headline typography with Playfair Display.
5.  **Best Sellers Polish:** Luxury product cards with edited transparent-background images, drop-shadow levitation, and refined desktop typography (price 1.4rem, button 1.1rem bold).
6.  **Special Events (MVP):** Simplified contact form using native Shopify `{% form 'contact' %}` — product catalog cards for reference + single inquiry form. Replaces complex JS cart/order system for manual event handling.
7.  **AI Discoverability (llms.txt):** Comprehensive `llms.txt` file served via `page.llms-txt` Liquid template (`{% layout none %}`) + URL redirect. Enables ChatGPT, Gemini, Claude, and other AI platforms to accurately discover and describe Morito Chocolates — includes full product catalog, certifications, sourcing story, shipping, wholesale, press, and FAQs.

### 🎨 Design Sprint — March 2026
All 5 optimization pillars executed: corporate marquee logos, clean ingredients comparison, mobile carousel zoom optimization, text overlay transparency refinements, and best sellers luxury polish.

**Latest (2026-03-25):** Slideshow fluid responsive typography with CSS `clamp()` — headings, subtext, and glass-effect box scale proportionally across all monitor sizes (`max-width: min(90%, 650px)`). Clean Ingredients elevated with editorial hierarchy — Morito card `scale(1.03)` with dramatic shadow, dashed separators, warmer left-card background. Special Events page simplified to native Shopify contact form (`{% form 'contact' %}`) replacing complex JS cart system — MVP approach for manual event handling.

**Latest (2026-04-16):** Responsive typography overhaul across homepage — fluid font sizes that scale smoothly on any screen. Best Sellers section polished with larger titles, optimized image loading, and reduced-motion accessibility. Clean Ingredients fully redesigned from dual-card comparison to streamlined headline + product image layout with brand attribute badges (vegan, gluten free, non-GMO, etc.). Slideshow Ken Burns animation synced to configurable speed setting with subtler zoom. Homepage about section typography unified.

**Latest (2026-04-19):** Pre-launch homepage copy review — corrected spelling and grammar errors across Mission, Carbon Free Shipping, Ethically Sourced, Environmentally Friendly, and Customer Reviews sections. Clean Ingredients visual refinement — chocolate stack image reduced 40%, headline and image brought closer together, attribute badge text enlarged to 1.7rem for better readability.

**Latest (2026-04-20):** Menu reorganization — final order: SHOP, ABOUT US, WHOLESALE, SPECIAL EVENTS, CONTACT, FIND US. Corporate Gifting removed as separate menu item (merged into Special Events page). Special Events displayed in all caps. Find Us moved to last position. Changes applied across mobile drawer, desktop dropdown, and mega menu.

---

### ⚠️ Security Protocol
* **Private Repository:** Access limited to authorized Impulsa Lab personnel and Client Admins.
* **No Credentials:** API Keys and Secrets are stored in `.env` variables, never in this code.

**© 2025 Impulsa Lab for Morito Chocolates.**
