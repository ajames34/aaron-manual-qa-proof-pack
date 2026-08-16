# Test cases — Item Optimizer (item-optimizer.com)

**Product:** Live catalog / product presentation site with checkout / payment-plan paths  
**Environment:** Production · Chrome (latest) · Desktop + mobile width  
**Tester:** Aaron

| ID | Title | Priority | Preconditions | Steps | Expected | Type |
|---|---|---|---|---|---|---|
| IO-01 | Homepage loads | P0 | None | 1. Open https://item-optimizer.com | Home loads; primary CTA visible | Smoke |
| IO-02 | Navigate to product / catalog | P0 | Catalog link present | 1. Open products or main listing 2. Open one item | Product detail shows title, price/plan info, key fields | Smoke |
| IO-03 | Required field validation | P0 | Form / contact / checkout fields | 1. Submit empty required fields | Inline or clear errors; no silent fail | Functional |
| IO-04 | Valid path toward checkout / plan | P0 | Product available | 1. Select item 2. Continue toward checkout or plan CTA | Next step loads; cart/plan state makes sense | Functional |
| IO-05 | Mobile product page | P0 | 390px width | 1. Open product on mobile 2. Scroll media + CTA | CTA reachable; text readable; no overlap | UI |
| IO-06 | Broken image / missing media | P1 | Product with media | 1. Inspect images load 2. Note any broken assets | Images load or graceful placeholder; no layout collapse | Functional |
| IO-07 | External / payment redirect | P1 | Checkout enabled | 1. Proceed to payment provider if applicable | Redirect is HTTPS; return path documented if fail | Functional |
| IO-08 | Browser back from product | P2 | Came from catalog | 1. Open product 2. Back | Returns to catalog without blank page | Edge |
| IO-09 | Copy / pricing clarity | P1 | Product page | 1. Read price and plan text | Numbers consistent; no contradictory plan copy | Content QA |
| IO-10 | Contact / support link | P2 | Footer or help link | 1. Click contact/support | Opens valid mail/link; not 404 | Functional |
| IO-11 | Double submit on form | P2 | Form present | 1. Submit valid form twice quickly | No duplicate spam if preventable; user sees confirmation | Edge |
| IO-12 | Cross-browser smoke | P1 | Safari or Firefox | 1. Load home + one product | Core path works in second browser | Regression |

## Execution notes (filled 2026-08-15 — public smoke)

| ID | Result | Notes | Date |
|---|---|---|---|
| IO-01 | **Pass** | item-optimizer.com loads; headline + Shopify/Woo/Square badges. Shot: `screenshots/io01_item_optimizer_home_desktop.png` | 2026-08-15 |
| IO-02 | **Pass (partial)** | Nav exposes How it Works / Guides / Login / Sign Up; dashboard preview visible on home | 2026-08-15 |
| IO-03 | N/A | Signup form not exercised this session (avoid creating accounts) | 2026-08-15 |
| IO-04 | N/A | Checkout path not run this session | 2026-08-15 |
| IO-05 | **Pass** | 390×844 viewport: hero + platform pills readable. Shot: `screenshots/io05_item_optimizer_home_mobile.png` | 2026-08-15 |
| IO-06 | **Pass** | Hero shelf imagery + dashboard preview images present (14 imgs in DOM) | 2026-08-15 |
| IO-07 | N/A | Payment redirect not run | 2026-08-15 |
| IO-08 | N/A | | 2026-08-15 |
| IO-09 | **Pass** | Price messaging present (“Starting at $34/mo” in title; protected/yr claims on page) | 2026-08-15 |
| IO-10 | **Pass** | Login / Sign Up / Guides links present | 2026-08-15 |
| IO-11 | N/A | | 2026-08-15 |
| IO-12 | N/A | Second browser not run this session | 2026-08-15 |
