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
4.  **Clean Ingredients:** Premium dual-card comparison (Organic Cream vs Warm Copper hero) replacing the "Decadent Flavors" section — highlights Morito's 3-ingredient purity vs. 15+ conventional ingredients.
5.  **Best Sellers Polish:** Luxury product cards with edited transparent-background images, drop-shadow levitation, and refined desktop typography (price 1.4rem, button 1.1rem bold).

### 🎨 Design Sprint — March 2026
All 5 optimization pillars executed: corporate marquee logos, clean ingredients comparison, mobile carousel zoom optimization, text overlay transparency refinements, and best sellers luxury polish.

**Latest (2026-03-24):** Slideshow Slide 1 repositioned to top-right to reveal product photography, glassmorphism opacity reduced to `0.30`, Slides 2 & 3 headline +25%. Clean Ingredients section elevated to premium dual-card layout (Organic Cream left card + Warm Copper hero right card with cream text, enlarged Playfair Display `3.6rem` counts, Montserrat `1.2rem` lists). Icon strip disabled for cleaner flow.

---

### ⚠️ Security Protocol
* **Private Repository:** Access limited to authorized Impulsa Lab personnel and Client Admins.
* **No Credentials:** API Keys and Secrets are stored in `.env` variables, never in this code.

**© 2025 Impulsa Lab for Morito Chocolates.**
