# How I test (Manual QA process)

I treat every live site like a product under release. No automation required for this lane — clear eyes, clear notes, retest discipline.

## Loop I use on every change

1. **Smoke** — Does the page load? Can I click the main path without a hard stop?
2. **Functional** — Does each control do what the label says (filters, links, forms, export)?
3. **Negative / edge** — Empty inputs, double-clicks, mobile width, back button, expired/empty states.
4. **Defect log** — Steps, expected, actual, severity, environment (browser + URL + date).
5. **Retest** — Same steps after a fix; then a short regression on nearby flows.
6. **Sign-off** — Only mark done when retest passes and I didn’t create a new break nearby.

## Severity I use

| Sev | Meaning | Example |
|---|---|---|
| S1 Blocker | Can’t complete core job | Apply button dead; checkout won’t load |
| S2 Major | Core path broken with workaround | Filter works but wrong count shown |
| S3 Minor | Wrong UI / copy / non-blocking | Typo; misaligned button on mobile |
| S4 Cosmetics | Polish | Spacing / icon color |

## Tools I use for Manual QA

- Browser (Chrome + Safari or Firefox for a second look)
- Screenshots / short screen recording for hard repros
- Spreadsheet or markdown table for cases and results
- Cursor only to **write clearer defect notes** — not as a substitute for clicking the product

## What I do *not* claim in Manual QA applications

- Building Selenium/Playwright frameworks (that’s automation / SDET)
- Owning CI test orchestration
- Salesforce admin certification

I’m applying for **hands-on Manual QA / Software Tester** roles: execute cases, document defects, retest fixes.
