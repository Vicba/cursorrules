# Security Audit

## Overview
Comprehensive security review to identify and fix vulnerabilities in the codebase.  

## Steps
1. **Dependency audit**
   - Check for known vulnerabilities (e.g. via `npm audit`, `pip audit`, or equivalent)
   - Update or patch outdated and vulnerable packages
   - Review third‑party dependencies and remove unused ones

2. **Code security review**
   - Check for common vulnerabilities (XSS, SQL injection, CSRF, insecure deserialization, etc.)
   - Review authentication and authorization logic
   - Audit data handling and storage practices
   - Ensure proper input validation and output encoding

3. **Infrastructure security**
   - Review environment variables and secrets management
   - Check access controls and least‑privilege configurations
   - Audit network security: firewalls, ingress rules, TLS, etc.

## Security Checklist
- [ ] Dependencies updated and secure
- [ ] No hardcoded secrets or credentials
- [ ] Input validation implemented for external inputs
- [ ] Authentication flows are robust and secure
- [ ] Authorization properly configured on sensitive operations
- [ ] Sensitive data is encrypted in transit and at rest (where applicable)

