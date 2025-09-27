# BUG-009 — Postal code field accepts alphabets  

**ID:** BUG-009  
**Title:** Checkout allows non-numeric postal codes  
**Application / AUT:** Demo OpenCart — Checkout Form  
**Reported By:** Fazila Ali  
**Date:** 2025-09-27  
**Environment:** Chrome v140 (Windows 10)  
**Severity:** Medium  
**Priority:** P2  
**Status:** Open  
**Reproducibility:** Always  
**Regression:** No  

---

## Steps to Reproduce
1. Go to checkout page.  
2. Enter `ABCD123` in Postal Code field.  
3. Proceed to payment.  

## Test Data
- Postal Code: `ABCD123`  

## Expected Result
- System should only accept valid numeric postal codes.  
- Invalid postal codes should be rejected.  

## Actual Result
- Field accepts alphabets mixed with numbers.  
- Checkout process continues.  

## Frequency
Always  

## Attachments
- Screenshot: `screenshots/BUG-009-postal-code.png`  

## Root Cause (Hypothesis)
- Input field allows free text without regex validation.  

## Suggested Fix
- Add regex validation (e.g., numeric-only pattern).  
- Apply both client-side and server-side validation.  

## Risk if Not Fixed
- Invalid addresses may cause delivery issues.  
- Poor data quality in system.  

## Workaround
- Manual user discipline (not reliable).  

## Acceptance Criteria
- Postal code field must reject alphabets.  
- Error message should be displayed clearly.  
