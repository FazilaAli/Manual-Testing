# BUG-003 — Registration/Login form misaligned on mobile view

**ID:** BUG-003  
**Title:** Registration/Login forms break layout and misalign on small screens (iPhone 12 resolution)  
**Application / AUT:** Demo OpenCart — Registration/Login UI  
**Reported By:** Fazila Ali  
**Date:** 2025-09-27  
**Environment:** Chrome DevTools (iPhone 12 resolution), Chrome 116 (Windows)  
**Severity:** Medium  
**Priority:** P2  
**Status:** Open  
**Reproducibility:** Always on small viewport  
**Regression:** No

---

## Steps to Reproduce
1. Open `https://demo.opencart.com/` in Chrome.  
2. Toggle DevTools to iPhone 12 resolution (or open on an actual mobile).  
3. Navigate to Register or Login page.

## Test Data
N/A (UI rendering issue)

## Expected Result
- Form fields and labels align vertically and the page is scrollable without overlap.  
- No horizontal scrollbars, placeholders not clipping.

## Actual Result
- Fields overlap or overflow; “Register” button is partially off-screen; label alignment breaks.

## Frequency
Always on smaller viewports tested.

## Attachments
- Screenshot: `screenshots/BUG-003-mobile-form-misaligned.png`  
- Related exploratory note: `../Exploratory-Notes/Session1_UI.md`

## Root Cause (Hypothesis)
- CSS media queries missing or an element with fixed width is forcing overflow.

## Suggested Fix
- Review responsive CSS rules, remove fixed widths, use flexible box/grid layouts.  
- Add visual regression tests to cover popular mobile breakpoints.

## Risk if Not Fixed
- Medium: poor mobile UX leads to lost conversions & customer dissatisfaction.

## Workaround
- None user-friendly; recommend using desktop view.

## Acceptance Criteria
- UI renders correctly on major breakpoints (mobile, tablet, desktop).  
- No horizontal scrollbars, and all interactive elements visible without overlap.

