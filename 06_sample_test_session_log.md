# Sample test session log

**Date:** 2026-08-15  
**Tester:** Aaron Jusino (session executed with Cursor browser QA assist)  
**Build:** Production  
**Scope:** Public smoke — CareerSnipe landing, Item Optimizer landing (desktop + mobile), Automation Edge landing  
**Browsers:** Chromium (Cursor browser) · Desktop ~1440 + Mobile 390×844  

## Summary
- **CS-01 Pass** — CareerSnipe home loads with CTAs  
- **CS-06 Pass*** — Browse Active Jobs opens guest auth / get-started gate (correct product behavior)  
- **Owner-suite cases (CS-02–05, 07–09, 12, 15) Blocked** — need Aaron signed-in owner session (not run publicly)  
- **IO-01 / IO-05 / IO-06 / IO-09 / IO-10 Pass** — Item Optimizer marketing + mobile hero OK  
- **AE-01 Pass** — theautomationedge.co loads articles / filters  

## Results

| Case | Result | Notes |
|---|---|---|
| CS-01 | PASS | `screenshots/cs01_careersnipe_home_desktop.png` |
| CS-06 | PASS* | Guest auth modal after Browse Active Jobs |
| CS-02–05, 07–09, 12, 15 | BLOCKED | Owner suite requires login |
| IO-01 | PASS | `screenshots/io01_item_optimizer_home_desktop.png` |
| IO-05 | PASS | `screenshots/io05_item_optimizer_home_mobile.png` |
| IO-06 / IO-09 / IO-10 | PASS | Images + pricing + nav links |
| AE-01 | PASS | `screenshots/ae01_automation_edge_home.png` |

## Defects logged this session
- None new S1/S2 on public pages  
- Note only: CS-06 modal screenshot timing was dark once; behavior still confirmed via accessibility snapshot  

## Time spent
~25 minutes automated public smoke + evidence capture  

## What’s left for Aaron (optional, ~10 min when signed in)
1. Open CareerSnipe **owner suite** while logged in  
2. Mark CS-03 / CS-05 / CS-15 Pass/Fail with one screenshot of Newest → Hybrid → 4-Day left pins  
3. That’s it — pack is already usable for Manual QA applications as-is  

## Screenshots folder
See [`screenshots/`](./screenshots/)
