# Sample test session log

**Date:** 2026-08-15 (screenshots refreshed 2026-08-15 evening)  
**Build:** Production  
**Scope:** Public smoke — CareerSnipe landing + guest auth gate, Item Optimizer (desktop + mobile), Automation Edge  
**Browsers:** Chromium · Desktop ~1440 · Mobile 390×844  

## Summary
- **CS-01 Pass** — CareerSnipe home loads with CTAs  
- **CS-06 Pass*** — Browse Active Jobs opens guest sign-in gate (expected)  
- **CS-10 Pass** — CareerSnipe home usable at mobile width  
- **Logged-in suite cases** — not in this public smoke (auth-gated); pack stays valid without them  
- **IO-01 / IO-05 Pass** — Item Optimizer desktop + mobile  
- **AE-01 Pass** — theautomationedge.co loads  

## Results

| Case | Result | Notes |
|---|---|---|
| CS-01 | PASS | `screenshots/cs01_careersnipe_home_desktop.png` |
| CS-06 | PASS* | Guest sign-in modal: `screenshots/cs06_browse_jobs_modal.png` |
| CS-10 | PASS | `screenshots/cs10_careersnipe_home_mobile.png` |
| IO-01 | PASS | `screenshots/io01_item_optimizer_home_desktop.png` |
| IO-05 | PASS | `screenshots/io05_item_optimizer_home_mobile.png` |
| AE-01 | PASS | `screenshots/ae01_automation_edge_home.png` |

## Defects logged this session
- None new S1/S2 on public pages  

## Screenshots folder
See [`screenshots/`](./screenshots/)

---

## Session 2 — Drive HUD speed-hold retest

**Date:** 2026-11-12
**Build:** Production (speed-hold fix commit 7fa75a40)
**Scope:** Drive HUD speed hold, live road test
**Browsers:** Chrome · Mobile

## Summary
- **DH-03 Pass** — Speed hold sticks after fix (was failing in live testing; see BUG-006)
- **DH-01 / DH-02 Pass (static)** — HUD loads; parked values read 0 MPH + 25 MPH limit as expected

## Results

| Case | Result | Notes |
|---|---|---|
| DH-03 | PASS | Speed hold retested live after fix commit 7fa75a40 |
| DH-01 | PASS | Live site loads; all sections render |
| DH-02 | PASS (static) | Parked load; live-speed check needs a drive |

## Defects logged this session
- BUG-006 (speed hold) — found in live testing, fixed, retested Pass
- GPS-dependent cases (DH-04 through DH-07, DH-09) still pending a full road test
