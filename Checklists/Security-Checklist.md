# Security Checklist

This checklist ensures the application adheres to **basic security standards**.

## Authentication & Authorization
- [ ] Strong password policy enforced (length, complexity)
- [ ] Multi-Factor Authentication supported (if applicable)
- [ ] Session timeout after inactivity
- [ ] Role-based restrictions tested (user cannot access admin endpoints)

## Input Validation
- [ ] Inputs validated on both client and server side
- [ ] SQL injection attempts are blocked
- [ ] Cross-Site Scripting (XSS) prevented by sanitizing inputs
- [ ] File uploads restricted to safe formats and sizes

## Data Protection
- [ ] Passwords hashed (e.g., bcrypt, Argon2) before storage
- [ ] Sensitive data transmitted only over HTTPS
- [ ] No secrets (API keys, DB passwords) exposed in client-side code
- [ ] Logs do not contain sensitive info (e.g., tokens, personal data)

## Session Management
- [ ] Secure, HttpOnly, and SameSite flags set for cookies
- [ ] Logout invalidates the session completely
- [ ] No session fixation vulnerabilities

## Innovations & Edge Checks
- [ ] Brute-force login attempts blocked with account lockout or captcha
- [ ] Security headers applied (CSP, X-Frame-Options, X-Content-Type-Options)
- [ ] Audit trails available for sensitive actions
- [ ] Security monitoring/alerts configured for suspicious activity
