# Retest checklist (fix verification)

Use this after every bug fix before calling the ticket done.

## For the defect itself
- [ ] Re-run **exact original steps** from the bug report
- [ ] Confirm **Expected** now matches Actual
- [ ] Try once more after hard refresh (cache)
- [ ] Try once on a **second browser** or mobile width if UI-related

## Nearby regression (5 minutes)
- [ ] Smoke the parent flow (e.g. suite loads; product page loads)
- [ ] Test one related control (other filter / other CTA)
- [ ] Confirm no new console-blocking errors on that path

## Sign-off line (paste into ticket)

```
Retest PASS — <BUG-ID>
Date: <YYYY-MM-DD>
Browser: <Chrome version>
Steps: same as original repro
Result: Expected behavior restored
Regression: smoke on <flow> PASS
Tester: Aaron Jusino
```

## Sign-off when still broken

```
Retest FAIL — <BUG-ID>
Date: <YYYY-MM-DD>
Still seeing: <one-line actual>
New screenshot: <attached>
```
