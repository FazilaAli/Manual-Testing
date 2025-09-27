# BUG-002 — Unlimited invalid login attempts (no lockout/CAPTCHA)

**ID:** BUG-002  
**Title:** Login page allows unlimited invalid attempts; no account lockout or CAPTCHA after repeated failures  
**Application / AUT:** Demo OpenCart — Login module  
**Reported By:** Fazila Ali  
**Date:** 2025-09-27  
**Environment:** Chrome 116 (Windows 10)  
**Severity:** High  
**Priority:** P1  
**Status:** Open  
**Reproducibility:** Always  
**Regression:** Unknown

---

## Steps to Reproduce
1. Go to `https://demo.opencart.com/` → My Account → Login.  
2. Enter valid email and incorrect password or invalid email for 20 attempts.  
3. Observe system behavior.

## Test Data
- Email: standard_user@example.com
- Password: incorrect_password

## Expected Result
- After configurable failed attempts (e.g., 5 attempts), either:
  - Account locked for a cooldown period, or
  - CAPTCHA presented, or
  - Temporary IP throttling with 429 response for API endpoints.

## Actual Result
- No account lockout, no CAPTCHA, no rate-limiting. Repeated attempts continue to be accepted and produce the generic "No match" message.

## Frequency
Always

## Attachments
- Screenshot: `screenshots/BUG-002-login-unlimited-attempts.png`  
- Related checklist: `../Checklists/Security_Checklist.md`

## Root Cause (Hypothesis)
- Lack of server-side lockout or rate-limiting logic for authentication endpoints.

## Suggested Fix
- Implement automated lockout after n failed attempts, or progressive throttling and CAPTCHA fallback.  
- Log and alert suspicious brute-force patterns.  
- Introduce account lock/unlock flows and documented admin controls.

## Risk if Not Fixed
- High: increases risk of credential stuffing and brute-force attacks leading to account compromise.

## Workaround
- For high-risk accounts, enable MFA (if available) or enforce stricter password policies.

## Acceptance Criteria
- After X failed attempts (configurable) the system blocks further attempts for Y minutes or shows CAPTCHA.  
- Auth endpoints return appropriate status codes (429 for throttling).  
- Security tests added to CI to simulate brute force attempts.

