# Exploratory Testing Notes – Session 3 (Checkout & Payment Workflow)

## Session Details

* **Application Under Test (AUT):** [Demo OpenCart](https://demo.opencart.com/)
* **Module:** Checkout and Payment Workflow
* **Tester:** Fazila Ali
* **Date:** 2025-09-27
* **Session Duration:** 120 minutes
* **Charter:** Explore the end-to-end checkout process including cart management, shipping details, payment methods, and order confirmation to identify usability, functional, and reliability issues.

---

## Scope

* Cart behavior with multiple products.
* Validation of shipping and billing information.
* Payment method selection and error handling.
* Order summary correctness.
* Edge cases in the checkout flow.

---

## Observations

1. **Cart Management**

   * Adding and removing items works correctly.
   * Cart does not auto-update quantity when typing numbers manually (requires clicking “Update”).
   * No confirmation prompt when removing items.

2. **Shipping Information**

   * Mandatory fields (address, city, postal code) correctly enforced.
   * Postal code accepts alphabets and special characters, no validation.
   * Dropdown for country/state is functional but not searchable, making it inconvenient for users.

3. **Payment Selection**

   * Available methods: “Cash on Delivery” and “Credit Card”.
   * Invalid credit card numbers pass client-side form validation but fail only after submission.
   * No support for modern payment options (PayPal, digital wallets).

4. **Order Summary**

   * Product details, quantities, and prices displayed correctly.
   * Taxes not itemized; shown only in final total.
   * Discount codes accepted but no clear confirmation if applied successfully.

5. **Confirmation Page**

   * Confirmation message displayed with order ID.
   * No order confirmation email received during testing.
   * Page reload duplicates the order submission.

---

## Bugs Logged

* **BUG-008:** Cart quantity does not update automatically when values are typed manually.
* **BUG-009:** Postal code field accepts invalid characters.
* **BUG-010:** Invalid credit card numbers bypass client-side validation.
* **BUG-011:** Order confirmation email not sent.
* **BUG-012:** Reloading confirmation page duplicates the order.

---

## Insights and Recommendations

* Add **real-time validation** for cart updates and postal code fields.
* Strengthen **credit card validation** at client-side to prevent invalid submissions.
* Ensure **confirmation emails** are consistently triggered after order placement.
* Prevent **duplicate orders** by restricting order submission on page reload.
* Enhance user experience with **searchable dropdowns** for country/state fields.

---

## Session Summary

The checkout exploratory session revealed gaps in **input validation**, **order reliability**, and **user experience**. While the flow works for standard cases, addressing issues like duplicate orders, weak validations, and missing confirmations is critical for ensuring trust and smooth transactions in a live e-commerce environment.