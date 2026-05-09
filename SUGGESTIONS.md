# Suggested Improvements for `home.html`

## Priority 1 — Correctness
1. **Recompute prayer times at local midnight** so daily solar declination/equation-of-time values update automatically.
2. **Handle next-prayer rollover explicitly** with robust date-aware scheduling instead of modulo-only minute comparisons.
3. **Add calculation-method options** (MWL, Umm al-Qura, ISNA, etc.) and juristic variants for Asr.

## Priority 2 — Product Usability
1. **Make location configurable** (manual lat/lng input + optional browser geolocation).
2. **Show exact clock time of the upcoming prayer** beside the relative countdown.
3. **Add timezone and city label** in the UI so users can verify context at a glance.

## Priority 3 — Accessibility & Reliability
1. **Respect reduced motion** (`prefers-reduced-motion`) by disabling animated transitions.
2. **Increase contrast guardrails** for all prayer palettes (WCAG AA target).
3. **Add offline fallback font stack** and avoid hard dependency on Google Fonts for rendering consistency.

## Priority 4 — Maintainability
1. **Split single-file app** into `index.html`, `styles.css`, and `app.js`.
2. **Extract constants/config** (angles, coordinates, palettes) into a dedicated object/module.
3. **Add lightweight tests** for date math and prayer time calculations (edge times near midnight, DST boundaries).

## Suggested Execution Plan
- **Step A:** Midnight recomputation + safer next-prayer selection.
- **Step B:** Configurable location and calculation method selector.
- **Step C:** Accessibility pass (reduced motion + contrast fixes).
- **Step D:** File split/refactor and test harness.
