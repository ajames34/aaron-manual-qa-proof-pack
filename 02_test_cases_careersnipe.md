# Test cases — CareerSnipe (careersnipe.com)

**Product:** Live job-search / owner suite web app  
**Environment:** Production · Chrome (latest) · Desktop 1440px + iPhone-width 390px  
**Build under test:** Live site as of proof-pack date  
**Tester:** Aaron

| ID | Title | Priority | Preconditions | Steps | Expected | Type |
|---|---|---|---|---|---|---|
| CS-01 | Home / app loads | P0 | Cleared cache or normal visit | 1. Open https://careersnipe.com 2. Wait for UI | Page loads without blank screen or hard JS error overlay | Smoke |
| CS-02 | Navigate to job suite / saved area | P0 | Logged-in or guest path available | 1. Open suite / jobs view from main nav or hash 2. Confirm job cards or empty state | Suite view renders; user is not stuck on a broken route | Smoke |
| CS-03 | Workplace filter — Remote | P0 | Suite has jobs | 1. Enable Remote filter 2. Scan first 5 cards | Cards shown are remote (or empty state if none); no crash | Functional |
| CS-04 | Workplace filter — Hybrid | P1 | Suite has jobs | 1. Enable Hybrid 2. Confirm location/policy text | Hybrid jobs only (or empty); filter can be cleared | Functional |
| CS-05 | Newest / profession filter pills | P0 | Owner suite visible | 1. Click Newest 2. Click Hybrid / Remote desk 3. Click 4-Day Week | Each pill updates the visible set; active pill is obvious | Functional |
| CS-06 | Job card — Apply / open posting | P0 | At least one job with apply URL | 1. Click Apply / View on a card 2. Confirm destination | Opens employer apply URL or expected hub; no `about:blank` | Functional |
| CS-07 | Broken / hub-only cards labeled | P1 | Suite includes hunt hubs if any | 1. Find a “Find posting” / hub card 2. Read CTA | User can tell hub vs direct apply; CTA matches | Functional |
| CS-08 | Search box on suite | P1 | Suite search present | 1. Type a known company or title 2. Clear search | Results narrow then restore when cleared | Functional |
| CS-09 | Resume / document download | P0 | Owner docs available | 1. Open resume download for a role type 2. Save/open file | PDF or text downloads; file opens; name is sensible | Functional |
| CS-10 | Mobile width — suite usable | P0 | DevTools 390×844 | 1. Resize to mobile 2. Scroll filters and cards 3. Tap Apply | Layout usable; filters not permanently hidden; no horizontal trap | UI / Responsive |
| CS-11 | Double-click Apply | P2 | Job with apply URL | 1. Double-click Apply quickly | One navigation or controlled behavior; no duplicate broken tabs storm | Edge |
| CS-12 | Empty filter combination | P1 | Filters available | 1. Stack filters until zero jobs 2. Read empty state 3. Reset | Friendly empty state; reset restores jobs | Negative |
| CS-13 | Back button after Apply tab | P2 | Apply opened in new tab if applicable | 1. Open apply 2. Return to suite tab | Suite still works; state not corrupted | Regression |
| CS-14 | Auth / session edge | P1 | Login available | 1. Refresh while on suite 2. Confirm still authorized or clean guest | No infinite spinner; clear logged-in vs guest | Functional |
| CS-15 | Smoke after filter order change | P0 | Newest / Hybrid / 4-Day left-pinned | 1. Confirm leftmost pills 2. Switch between them twice | Order stable; counts update; no console-blocking error | Regression |

## Execution notes (public smoke)

| ID | Result | Notes | Date |
|---|---|---|---|
| CS-01 | **Pass** | careersnipe.com loads; hero + Initialize Scanner / Browse Active Jobs visible. Shot: `screenshots/cs01_careersnipe_home_desktop.png` | 2026-08-15 |
| CS-02 | **Blocked (auth)** | Owner suite / logged-in job board not available in public guest session | 2026-08-15 |
| CS-03 | **Blocked (auth)** | Needs owner suite session | 2026-08-15 |
| CS-04 | **Blocked (auth)** | Needs owner suite session | 2026-08-15 |
| CS-05 | **Blocked (auth)** | Needs owner suite session (Newest / Hybrid / 4-Day pills) | 2026-08-15 |
| CS-06 | **Pass*** | Browse Active Jobs opens guest Sign in modal (expected). Shot: `screenshots/cs06_browse_jobs_modal.png` | 2026-08-15 |
| CS-07 | **Blocked (auth)** | Hub cards live in owner suite | 2026-08-15 |
| CS-08 | **Blocked (auth)** | Suite search | 2026-08-15 |
| CS-09 | **Blocked (auth)** | Owner resume downloads | 2026-08-15 |
| CS-10 | **Pass** | Public home usable at mobile width. Shot: `screenshots/cs10_careersnipe_home_mobile.png` | 2026-08-15 |
| CS-11 | N/A | Skip until owner apply CTA available in session | 2026-08-15 |
| CS-12 | **Blocked (auth)** | | 2026-08-15 |
| CS-13 | N/A | | 2026-08-15 |
| CS-14 | **Pass (partial)** | Guest landing stable after refresh; Sign In / Get Started present | 2026-08-15 |
| CS-15 | **Blocked (auth)** | Filter pin order is owner-suite only | 2026-08-15 |

\*Pass with note = product behaved correctly for a guest (auth gate), not a broken Apply.