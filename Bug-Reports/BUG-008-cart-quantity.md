# BUG-008 — Cart allows zero/negative quantities  

**ID:** BUG-008  
**Title:** Cart does not validate quantity field, accepts zero and negative values  
**Application / AUT:** Demo OpenCart — Cart Module  
**Reported By:** Fazila Ali  
**Date:** 2025-09-27  
**Environment:** Chrome v140 (Windows 10), Postman  
**Severity:** High  
**Priority:** P1  
**Status:** Open  
**Reproducibility:** Always  
**Regression:** No  

---

## Steps to Reproduce
1. Add a product to the cart.  
2. Update quantity to `0` or `-2` via UI or API request (`/api/cart/update`).  
3. Observe cart totals.  

## Test Data
- Product: `MacBook`  
- Quantity: `0` and `-2`  

## Expected Result
- System should prevent invalid quantities.  
- Error message: *“Quantity must be at least 1.”*  

## Actual Result
- Cart updates with zero or negative quantities.  
- Total amount shows incorrect values.  

## Frequency
Always  

## Attachments
- Screenshot: `screenshots/BUG-008-cart-quantity.png`  

## Root Cause (Hypothesis)
- Backend validation for quantity missing.  
- Only client-side validation applied (easily bypassed).  

## Suggested Fix
- Implement server-side quantity validation.  
- Enforce `quantity >= 1`.  

## Risk if Not Fixed
- Wrong cart totals, potential financial losses.  
- Broken order workflow.  

## Workaround
- None for end users.  

## Acceptance Criteria
- Cart should reject `0` or negative quantities.  
- API/UI should return error message consistently.  
