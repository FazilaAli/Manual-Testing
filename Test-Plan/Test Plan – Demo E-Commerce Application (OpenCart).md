# Test Plan – Demo E-Commerce Application (OpenCart)

## 1. Introduction
This Test Plan defines the testing strategy and approach for validating the functionality, performance, usability, and security of the Demo E-Commerce application (OpenCart).  
The objective is to ensure that all critical user journeys (registration, login, product search, cart management, checkout, payment, and order confirmation) work as expected before release.  

---

## 2. Objectives
- Verify that the application meets business and functional requirements.  
- Detect defects early and ensure they are logged, tracked, and resolved.  
- Validate usability, reliability, and compatibility across devices and browsers.  
- Ensure performance and security aspects are covered at a high level.  
- Provide stakeholders with confidence in application readiness.  

---

## 3. Scope

### In-Scope
- User registration and login workflows.  
- Product browsing, filtering, and search.  
- Cart management (add, update, remove items).  
- Checkout process (shipping, billing, payment, order confirmation).  
- Order history and account management.  
- Validation of error handling and input validations.  
- Exploratory testing for usability and UX issues.  

### Out-of-Scope
- Third-party integrations (live payment gateways, shipping APIs).  
- Non-functional testing at production scale (load, stress).  
- Localisation and internationalisation testing.  

---

## 4. Test Strategy
- **Manual Testing:** Primary method for functional and exploratory coverage.  
- **Checklists:** To ensure coverage of repetitive test areas (UI, security basics, forms, navigation).  
- **Exploratory Testing:** To discover usability and edge-case defects.  
- **Bug Reporting:** Detailed bug reports with severity, priority, reproducibility, and root cause hypothesis.  
- **Regression Testing:** Retesting fixed defects and ensuring stability after changes.  

---

## 5. Test Deliverables
- Test Plan (`TestPlan.md`)  
- Test Checklists (`Checklists/`)  
- Exploratory Session Notes (`Exploratory-Notes/`)  
- Bug Reports (`Bug-Reports/`)  
- Test Summary Report (post-execution findings)  

---

## 6. Test Environment
- **Browsers:** Chrome 116, Firefox 115, Edge 116  
- **Devices:** Windows 10 desktop, Android (Chrome emulator), iPhone 12 (Safari emulator)  
- **Application URL:** [https://demo.opencart.com/](https://demo.opencart.com/)  

---

## 7. Roles & Responsibilities
- **QA Engineer (Fazila Ali):**  
  - Create test plan, checklists, and exploratory notes.  
  - Execute test cases and exploratory sessions.  
  - Log and track bugs.  
  - Provide test reports to stakeholders.  

- **Developers (Demo Assumption):**  
  - Fix reported bugs.  
  - Provide build notes and clarify requirements.  

- **Stakeholders:**  
  - Review test deliverables.  
  - Approve final release readiness.  

---

## 8. Entry & Exit Criteria

### Entry Criteria
- Application build deployed and stable.  
- Functional requirements documented.  
- Test environment ready and accessible.  

### Exit Criteria
- All critical test cases executed.  
- All P0/P1 bugs resolved or accepted by stakeholders.  
- Test summary report delivered.  

---

## 9. Risks & Mitigation
| Risk | Impact | Mitigation |
|------|--------|------------|
| Unclear requirements | Delayed test design | Use exploratory testing and clarify with stakeholders |
| Environment downtime | Blocked testing | Maintain backup test environments |
| High number of defects | Project delays | Prioritise critical defects (P0/P1) first |
| Limited time for regression | Missed defects | Use checklists and targeted regression |

---

## 10. Test Schedule
- **Test Planning & Preparation:** 2 days  
- **Test Execution (Functional + Exploratory):** 5 days  
- **Bug Reporting & Retesting:** Ongoing during execution  
- **Regression Cycle:** 2 days  
- **Test Summary Report:** 1 day  

---

## 11. Tools
- **Documentation & Planning:** Markdown (`.md` files in GitHub)  
- **Bug Tracking:** Markdown bug reports (GitHub issues for demonstration)  
- **Exploratory Notes:** Session-based `.md` files  
- **Browsers/Emulators:** Chrome DevTools, Firefox, Edge, mobile simulators  

---

## 12. Approval
**Prepared By:** Fazila Ali  
**Date:** 2025-09-27  
**Approved By:** (Stakeholder/Reviewer – demo placeholder)  

---
