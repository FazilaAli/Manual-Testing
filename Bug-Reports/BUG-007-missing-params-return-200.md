# BUG-007 — Missing parameters return 200 instead of 400  

**ID:** BUG-007  
**Title:** API returns HTTP 200 with empty response instead of 400 when required parameters are missing  
**Application / AUT:** Demo OpenCart — Search API  
**Reported By:** Fazila Ali  
**Date:** 2025-09-27  
**Environment:** Postman, Chrome DevTools (Windows 10)  
**Severity:** Medium  
**Priority:** P2  
**Status:** Open  
**Reproducibility:** Always  
**Regression:** No  

---

## Steps to Reproduce
1. Send GET request: `/api/search` (no `q` parameter).  
2. Observe response.  

## Test Data
- Request: `/api/search`  

## Expected Result
- API should return:  
  - HTTP 400 Bad Request  
  - Error message: *“Missing required parameter: q.”*  

## Actual Result
- API returns HTTP 200 with an empty JSON response.  

## Frequency
Always  

## Attachments
- Screenshot: `screenshots/BUG-007-missing-param.png`  

## Root Cause (Hypothesis)
- Backend does not enforce required parameter checks.  

## Suggested Fix
- Add parameter validation at controller level.  
- Ensure missing params return 400 response with descriptive error.  

## Risk if Not Fixed
- Misleading responses.  
- Difficult for client applications to debug.  

## Workaround
- None for API consumers.  

## Acceptance Criteria
- API should return 400 error when required params are missing.  
- Response should clearly specify missing parameter.  
