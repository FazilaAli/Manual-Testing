# Exploratory Testing Notes – Session 2 (API Testing)

## Session Details

* **Application Under Test (AUT):** [Demo OpenCart](https://demo.opencart.com/) – Public API Endpoints
* **Module:** Product Catalog API
* **Tester:** Fazila Ali
* **Date:** 2025-09-27
* **Session Duration:** 90 minutes
* **Charter:** Explore API endpoints for product retrieval, categories, and search functionality to assess correctness, performance, and error handling.

---

## Scope

* Validate API responses against expected business logic.
* Check input validation for query parameters.
* Verify response structure (JSON schema, data types).
* Assess error handling for invalid/missing parameters.
* Explore performance with repeated/parallel requests.

---

## Observations

1. **Product Retrieval Endpoint** (`GET /api/products`)

   * Returns product list with correct fields: `id`, `name`, `price`, `category`.
   * Response time under 500ms for up to 20 products.
   * No pagination implemented; API returns all products in a single response (scalability issue).

2. **Category Filtering** (`GET /api/products?category=electronics`)

   * Works as expected for valid categories.
   * Invalid category returns empty array without warning (could return a clearer error message).

3. **Search Functionality** (`GET /api/products?search=phone`)

   * Search is case-sensitive (searching "Phone" returns results, "phone" does not).
   * Special characters in query (`?search=phone%20case`) return HTTP 500 error instead of a safe error response.

4. **Error Handling**

   * Missing required parameter returns 200 with empty array instead of 400 Bad Request.
   * Invalid endpoint path returns 404 with generic message *"Not Found"*.

5. **Performance/Load**

   * 50 concurrent requests: ~20% of requests exceeded 1 second.
   * No rate limiting or throttling observed.

---

## Bugs Logged

* **BUG-004:** No pagination in product retrieval; API may fail with large datasets.
* **BUG-005:** Search endpoint is case-sensitive; expected behavior is case-insensitive search.
* **BUG-006:** Special characters in search query cause HTTP 500 error.
* **BUG-007:** Missing parameters return 200 instead of proper error code (400).

---

## Insights and Recommendations

* Implement **pagination** to improve scalability.
* Standardize **error responses** with proper HTTP status codes.
* Make **search functionality case-insensitive** for better usability.
* Introduce **input sanitization** to avoid server errors with special characters.
* Add **rate limiting/throttling** to handle abusive requests gracefully.

---

## Session Summary

The exploratory session highlighted key **functional issues** (case-sensitive search, poor error handling), **scalability concerns** (lack of pagination), and **performance gaps** (slow responses under load). Addressing these findings will make the API more reliable, user-friendly, and production-ready.
