# API Checklist

This checklist validates the **reliability, security, and usability** of APIs.

## Request/Response Basics
- [ ] All endpoints return correct HTTP status codes (200, 201, 400, 401, 404, 500)
- [ ] Response times are within SLA (e.g., < 2 seconds for standard calls)
- [ ] Error messages are descriptive and not generic (avoid "Something went wrong")

## Data Integrity
- [ ] Response data matches the request schema (data types, mandatory fields)
- [ ] No sensitive data (e.g., passwords, tokens) is returned in plain text
- [ ] Pagination works correctly (page size, next/prev links)

## Security
- [ ] Authentication required for private endpoints (401 Unauthorized if missing)
- [ ] Role-based access control enforced (user vs. admin permissions)
- [ ] Tokens/keys expire after timeout
- [ ] Rate limiting applied to prevent abuse (e.g., 429 Too Many Requests)

## Reliability
- [ ] Idempotent methods (GET, PUT) behave consistently on repeated calls
- [ ] Graceful handling of invalid inputs (meaningful error + no server crash)
- [ ] APIs handle edge cases (e.g., empty arrays, null values, special characters)

## Innovations & Edge Checks
- [ ] Versioning strategy is in place (e.g., `/v1/`, `/v2/`)
- [ ] APIs are documented with Swagger/Postman collections
- [ ] CORS headers set correctly for cross-origin requests
- [ ] Localization supported in responses (date/time formats, currency symbols)
