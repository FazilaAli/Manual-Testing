# Exploratory Testing Notes – Session 1 (UI Testing)

## Session Details

* **Application Under Test (AUT):** [Demo OpenCart](https://demo.opencart.com/)
* **Module:** User Registration & Login
* **Tester:** Fazila Ali
* **Date:** 2025-09-27
* **Session Duration:** 90 minutes
* **Charter:** Explore the User Registration and Login workflows to identify usability, functional, and validation issues.

---

## Scope

* Positive and negative scenarios in registration
* Field validation (mandatory, format, length)
* Login with valid/invalid credentials
* Navigation and error messages
* UI consistency and responsiveness

---

## Observations

1. **Registration Form**

   * Missing password strength indicator.
   * No validation for weak passwords (e.g., "12345" is accepted).
   * Error message for invalid email is generic: *"E-Mail Address does not appear to be valid"* (could be more descriptive).
   * Fields do not have inline labels; only placeholders are used, which disappear when typing.

2. **Login**

   * Incorrect credentials show a clear error message: *"Warning: No match for E-Mail Address and/or Password."*
   * After 5 invalid attempts, no account lockout or CAPTCHA appears (security risk).
   * Login button remains active even when fields are empty.

3. **UI/UX**

   * Registration and Login forms are not mobile-friendly (tested on Chrome DevTools, iPhone 12 resolution).
   * Field alignment breaks on smaller screen sizes.
   * "Forgotten Password" link redirects correctly but opens in the same tab instead of a new one.

---

## Bugs Logged

* **BUG-001:** Registration accepts weak passwords without warning.
* **BUG-002:** Login form allows unlimited invalid attempts (no account lockout).
* **BUG-003:** Mobile view – Registration form misaligned on smaller screens.

---

## Insights and Recommendations

* Add **password strength validation** to improve security and user guidance.
* Implement **account lockout or CAPTCHA** after multiple failed login attempts.
* Improve **error message specificity** to help users correct mistakes.
* Enhance **mobile responsiveness** for accessibility and better user experience.

---

## Session Summary

The exploratory session uncovered **security gaps**, **usability concerns**, and **UI responsiveness issues**. While the core functionality works, improvements in validation, mobile experience, and security controls would significantly enhance product quality.
