# BUG-005 — Search endpoint is case-sensitive  

**ID:** BUG-005  
**Title:** Search API returns results only for exact case match  
**Application / AUT:** Demo OpenCart — Search API  
**Reported By:** Fazila Ali  
**Date:** 2025-09-27  
**Environment:** Chrome DevTools → Network tab, Postman (Windows 10)  
**Severity:** Medium  
**Priority:** P2  
**Status:** Open  
**Reproducibility:** Always  
**Regression:** Unknown  

---

## Steps to Reproduce
1. Send a GET request:  
   - `/api/search?q=iPhone`  
   - `/api/search?q=iphone`  
2. Compare results.  

## Test Data
- Query 1: `iPhone`  
- Query 2: `iphone`  

## Expected Result
- Both queries should return the same matching products.  

## Actual Result
- `iPhone` returns correct results.  
- `iphone` returns empty response.  

## Frequency
Always  

## Attachments
- Postman screenshots: `screenshots/BUG-005-search-case-sensitive.png`  

## Root Cause (Hypothesis)
- Database search is case-sensitive; missing normalization or LOWER() query handling.  

## Suggested Fix
- Normalize input queries (convert to lowercase).  
- Apply case-insensitive search in database or full-text index.  

## Risk if Not Fixed
- Users may fail to find products due to case mismatch.  
- Poor search usability.  

## Workaround
- None for end users.  

## Acceptance Criteria
- Search should return identical results regardless of input case.  
