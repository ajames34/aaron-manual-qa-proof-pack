# Sample bug reports (Manual QA format)

These are **real-style defect writeups** from testing my own live products.  
Format matches what Manual QA teams expect: clear repro, expected vs actual, severity, environment.

---

## BUG-001 — Suite filter pill order not obvious after market reshuffle (Historical / process example)

| Field | Value |
|---|---|
| **Title** | Owner suite profession pills reorder by market stats; Newest / Hybrid / 4-Day not glued left |
| **Product** | CareerSnipe owner suite |
| **Severity** | S2 Major (usability of primary apply lanes) |
| **Environment** | Chrome · macOS · production |
| **Status** | Fixed (pinned order shipped) |

**Steps to reproduce**
1. Open owner suite as Aaron.
2. Observe profession filter bar with “More filters” open.
3. Note position of Newest, Hybrid / Remote desk, and 4-Day Week pills.

**Expected**  
Newest → Hybrid / Remote desk → 4-Day Week stay leftmost so highest-priority apply lanes are always visible.

**Actual**  
Pills reshuffled by market hire %; Hybrid and 4-Day could appear far right (#11 / #28 style), easy to miss.

**Evidence**  
Screenshot of filter bar before pin fix; commit notes for leftmost pin sort.

**Workaround**  
Scroll horizontally / use More filters (poor UX).

---

## BUG-002 — Job card apply opens search hub instead of employer posting

| Field | Value |
|---|---|
| **Title** | Apply CTA on hub-only card looks like direct apply |
| **Product** | CareerSnipe suite cards |
| **Severity** | S2 Major |
| **Environment** | Chrome · production |

**Steps to reproduce**
1. Open a card labeled as hunt hub / “Find posting”.
2. Click primary Apply-style CTA.
3. Land on LinkedIn/Indeed/4dayweek search results, not a single employer JD.

**Expected**  
CTA label and summary make hub vs direct apply obvious (“Find posting ↗” vs “Apply”).

**Actual**  
User can think the role is one-click apply when it is a search hub.

**Suggested fix**  
Distinct button label + `apply_hub_only` badge in summary (implemented on curated hubs).

---

## BUG-003 — Mobile filter row hard to reach primary lanes

| Field | Value |
|---|---|
| **Title** | On narrow viewports, high-priority filter pills require long horizontal scroll |
| **Product** | CareerSnipe suite |
| **Severity** | S3 Minor |
| **Environment** | Chrome DevTools 390×844 |

**Steps to reproduce**
1. Set viewport to 390px wide.
2. Open suite filter row.
3. Try to reach Hybrid / 4-Day without knowing they are left-pinned.

**Expected**  
Priority lanes visible with minimal scroll or sticky left group.

**Actual**  
Before pin fix, priority lanes could sit mid/right of a long pill list.

---

## BUG-004 — Empty filter stack shows confusing blank area

| Field | Value |
|---|---|
| **Title** | Aggressive filter combo yields blank area without clear empty state |
| **Product** | CareerSnipe suite |
| **Severity** | S3 Minor |
| **Environment** | Chrome · production |

**Steps to reproduce**
1. Enable multiple exclusive filters until zero jobs match.
2. Observe main panel.

**Expected**  
Message like “No jobs match — clear filters” + reset control.

**Actual**  
Sparse/blank feeling; user may think the app broke.

---

## BUG-005 — Item Optimizer product CTA overlap risk on small phones

| Field | Value |
|---|---|
| **Title** | Primary CTA sits under sticky chrome on very small heights |
| **Product** | item-optimizer.com product page |
| **Severity** | S3 Minor |
| **Environment** | Mobile Safari / Chrome 390×700-ish |

**Steps to reproduce**
1. Open a product page on a short mobile viewport.
2. Scroll to buy / plan CTA.
3. Check if browser chrome covers the button.

**Expected**  
CTA fully tappable with padding above browser UI.

**Actual**  
On short viewports, CTA can sit too close to the bottom edge (watch on device QA).

**Retest focus**  
After CSS padding change, re-run IO-05 on a physical phone, not only DevTools.
