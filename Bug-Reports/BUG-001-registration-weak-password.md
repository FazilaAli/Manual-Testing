# BUG-001 — Registration accepts weak passwords without warning

**ID:** BUG-001  
**Title:** Registration accepts weak passwords (e.g., "12345") without server-side validation or password strength feedback  
**Application / AUT:** Demo OpenCart (or any demo e-commerce) — Registration module  
**Reported By:** Fazila Ali  
**Date:** 2025-09-27  
**Environment:** Chrome 116 (Windows 10), Firefox 115, Mobile (Chrome Android emulator iPhone 12)  
**Severity:** High  
**Priority:** P1  
**Status:** Open  
**Reproducibility:** Always  
**Regression:** Unknown

---

## Steps to Reproduce
1. Navigate to `https://demo.opencart.com/` → My Account → Register.  
2. Fill required fields. Use `Password: 12345` and `Confirm Password: 12345`.  
3. Submit the registration form.

## Test Data
- First Name: Test
- Last Name: User
- Email: testuser+weakpass@example.com
- Password: `12345`

## Expected Result
- Registration should be blocked with a validation message: "Password does not meet minimum strength requirements" (policy e.g., min 8 characters, 1 uppercase, 1 number).  
- A password strength meter or guidance should be visible.

## Actual Result
- Account is created successfully. No client-side or server-side rejection for weak password. No strength indicator present.

## Frequency
Always

## Attachments
- Screenshot: `screenshots/BUG-001-registration-weak-password.png`
- Reference exploratory note: `../Exploratory-Notes/Session1_UI.md`

## Root Cause (Hypothesis)
- Missing server-side password policy enforcement. Client-side validation is incomplete or absent.

## Suggested Fix
- Enforce a robust password policy on server-side (minimum length, complexity) and reflect same checks on client-side.  
- Add a password strength meter and inline guidance.  
- Ensure compliance with industry best practices (NIST/OWASP recommendations).

## Risk if Not Fixed
- High security risk: weak passwords can be easily guessed or brute-forced, exposing user accounts and potentially sensitive data.

## Workaround
- No workaround for users; consider manual user education (not viable long-term).

## Acceptance Criteria
- Registration attempts using passwords that violate policy should return HTTP 400 with a clear descriptive message.  
- Password strength meter visible on registration form.  
- Unit/integration tests added to verify server-side password policy.

