# BUG-010 — Credit card field accepts invalid formats  

**ID:** BUG-010  
**Title:** Checkout accepts invalid credit card numbers without validation  
**Application / AUT:** Demo OpenCart — Checkout Payment Form  
**Reported By:** Fazila Ali  
**Date:** 2025-09-27  
**Environment:** Chrome v140 (Windows 10), Postman  
**Severity:** Critical  
**Priority:** P1  
**Status:** Open  
**Reproducibility:** Always  
**Regression:** No  

---

## Steps to Reproduce
1. Go to checkout payment section.  
2. Enter `1234 5678 9999` as credit card number.  
3. Submit payment.  

## Test Data
- Card Number: `1234 5678 9999`  

## Expected Result
- System should validate credit card number (Luhn check).  
- Invalid card numbers should be rejected.  

## Actual Result
- Invalid card number accepted.  
- Payment request proceeds to next step.  

## Frequency
Always  

## Attachments
- Screenshot: `screenshots/BUG-010-credit-card.png`  

## Root Cause (Hypothesis)
- Missing Luhn algorithm validation.  
- Field validation limited to length/format only.  

## Suggested Fix
- Implement Luhn check at server-side.  
- Show clear error messages for invalid numbers.  

## Risk if Not Fixed
- Failed or fraudulent transactions.  
- Security and compliance risks.  

## Workaround
- None for end users.  

## Acceptance Criteria
- Only valid card numbers (per Luhn) should be accepted.  
- Invalid numbers must trigger error.  
