# BUG-006 — Special characters in search cause HTTP 500  

**ID:** BUG-006  
**Title:** Search endpoint crashes with HTTP 500 when special characters are used  
**Application / AUT:** Demo OpenCart — Search API  
**Reported By:** Fazila Ali  
**Date:** 2025-09-27  
**Environment:** Chrome DevTools → Network tab, Postman  
**Severity:** High  
**Priority:** P1  
**Status:** Open  
**Reproducibility:** Always  
**Regression:** No  

---

## Steps to Reproduce
1. Send request: `/api/search?q=%%%`  
2. Send request: `/api/search?q=<script>`  

## Test Data
- Query: `%%%` or `<script>`  

## Expected Result
- API should return 400 Bad Request with message: *“Invalid search query.”*  

## Actual Result
- API returns HTTP 500 Internal Server Error.  

## Frequency
Always  

## Attachments
- Screenshot: `screenshots/BUG-006-search-special-characters.png`  

## Root Cause (Hypothesis)
- Input not sanitized before DB query.  
- Possible SQL injection or unhandled exceptions.  

## Suggested Fix
- Apply server-side input validation and sanitization.  
- Return user-friendly error with proper HTTP status.  

## Risk if Not Fixed
- Security risk (injection attacks).  
- Service instability.  

## Workaround
- None for end users.  

## Acceptance Criteria
- API rejects special characters gracefully with 400 response.  
- No HTTP 500 should occur.  
