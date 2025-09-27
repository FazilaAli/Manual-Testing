# BUG-004 — Product API returns all products in a single response (no pagination)

**ID:** BUG-004  
**Title:** `GET /api/products` returns entire dataset without pagination parameters or headers  
**Application / AUT:** Demo OpenCart — Product Catalog API  
**Reported By:** Fazila Ali  
**Date:** 2025-09-27  
**Environment:** API tests (curl), Chrome, Local network  
**Severity:** High  
**Priority:** P1  
**Status:** Open  
**Reproducibility:** Always  
**Regression:** Unknown

---

## Steps to Reproduce
1. Run:
```bash
curl -i "https://demo.opencart.com/api/products"
