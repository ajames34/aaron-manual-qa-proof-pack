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
