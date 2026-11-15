# Test cases — Drive HUD (drive-hud-seven.vercel.app)

**Product:** Speed-first driving HUD web app + Meta Ray-Ban Display glasses app (voice control, Pro tier $10/mo)
**Environment:** Production · Chrome (latest) · Desktop 1440px + mobile/glasses-width 390px · GPS-dependent features need a live drive
**Build under test:** Live site as of proof-pack date; speed-hold fix commit 7fa75a40 (2026-11-12)
**Tester:** Aaron

| ID | Title | Priority | Preconditions | Steps | Expected | Type |
|---|---|---|---|---|---|---|
| DH-01 | HUD loads | P0 | Normal visit | 1. Open https://drive-hud-seven.vercel.app 2. Wait for UI | Page loads without blank screen or hard JS error overlay; speed, map, and track sections render | Smoke |
| DH-02 | Speed display + speed limit | P0 | GPS available or static load | 1. Read current speed 2. Read speed limit | Speed shows live value (0 MPH parked); limit shows posted limit (25 MPH in test area); no stale or blank value | Functional |
| DH-03 | Speed hold holds the set speed | P0 | Driving, speed hold available | 1. Set a hold speed while driving 2. Keep driving 3. Watch the held value | Held speed stays held until released; does not drop or reset mid-drive | Regression |
| DH-04 | Set a destination / next turn | P0 | No destination set | 1. Set a destination 2. Read NEXT TURN | Next-turn guidance appears; route state changes from NO DESTINATION | Functional |
| DH-05 | GPS no-signal state | P1 | GPS off or no fix | 1. Load HUD with GPS unavailable | Clear NO SIGNAL state; app does not crash, blank out, or show fake speed | Negative |
| DH-06 | Track mode — laps auto start/stop | P1 | Track picked | 1. Pick a track 2. Cross start/finish line | Lap timer starts and stops automatically; no manual lap tap needed | Functional |
| DH-07 | 0–60 / track timers + bests | P1 | Track timers visible | 1. Read 0–60, 0–100, 1/8, 1/4, 30–50, 50–70, brake timers 2. Read BEST rows | Timers record runs; bests persist and show; no NaN or frozen values | Functional |
| DH-08 | Pro tier upgrade path | P1 | Free tier | 1. Open DRIVE HUD PRO ($10/mo) 2. Start upgrade | Upgrade path loads (Stripe); price $10/mo shown; no dead button | Functional |
| DH-09 | Voice control | P1 | Mic available or denied | 1. Use a voice command 2. Deny mic permission and retry | Command executes when mic is on; graceful message (not a crash) when mic is denied | Functional / Edge |
| DH-10 | Mobile / glasses width — HUD readable | P0 | DevTools 390×844 | 1. Resize to mobile 2. Scroll speed, map, track sections | Layout usable; speed stays readable; no horizontal trap; no CTA hidden under browser chrome | UI / Responsive |

## Execution notes

| ID | Result | Notes | Date |
|---|---|---|---|
| DH-01 | **Pass** | Live site loads; speed, map, track, Pro sections all render. Verified via live load. | 2026-11-14 |
| DH-02 | **Pass (static)** | Parked load shows 0 MPH + 25 MPH limit as expected; live-speed check needs a drive. | 2026-11-14 |
| DH-03 | **Pass** | Speed-hold defect found in live testing, fixed (commit 7fa75a40), retested live — hold sticks. See BUG-006. | 2026-11-12 |
| DH-04 | Case written | Run pending live road test (needs GPS + destination). | — |
| DH-05 | Case written | Run pending live road test (needs GPS-off state). | — |
| DH-06 | Case written | Run pending track session. | — |
| DH-07 | Case written | Run pending live drive (timers need motion). | — |
| DH-08 | Case written | Run pending (needs Stripe checkout walkthrough). | — |
| DH-09 | Case written | Run pending live drive + mic. | — |
| DH-10 | Case written | Run pending (DevTools pass is the next step; physical phone/glasses check after). | — |

GPS-dependent cases (DH-04 through DH-07, DH-09) need a live drive by design — a parked load correctly shows zeros, not a failure. Screenshots for Drive HUD are pending the road test.
