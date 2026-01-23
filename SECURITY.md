# Security Policy

## Supported Versions

We are committed to maintaining the security of the Bank iD Wallet API documentation and ensuring that integrators have access to secure implementation guidance.
We strongly recommend always using the latest version of the API documentation and implementing the most recent security specifications.

## Reporting a Vulnerability

The security of the Bank iD Wallet infrastructure and related APIs is a top priority. If you discover a security vulnerability in the Wallet API, documentation, or related systems, please report it responsibly.

### How to Report

**DO NOT** report security vulnerabilities through public GitHub issues, discussions, or pull requests.

Instead, please report security vulnerabilities by sending an email to:

**admin@bankid.cz**
**filip@bankid.cz**

Please include the following information in your report:

- **Type of vulnerability** (e.g., authentication bypass, data exposure, injection flaw)
- **Affected component** (API endpoint, documentation section, implementation example)
- **Step-by-step instructions** to reproduce the issue
- **Potential impact** of the vulnerability
- **Suggested remediation** (if available)
- **Your contact information** for follow-up questions

### Response Timeline

- **Initial Response**: Within 3 business days of report submission
- **Status Update**: Within 7 business days with preliminary assessment
- **Resolution Timeline**: Varies based on severity and complexity
    - Critical: 7-14 days
    - High: 14-30 days
    - Medium: 30-60 days
    - Low: 60-90 days

### What to Expect

1. **Acknowledgment**: We will acknowledge receipt of your vulnerability report
2. **Investigation**: Our security team will investigate and validate the issue
3. **Communication**: We will keep you informed of our progress
4. **Resolution**: Once fixed, we will notify you and may publicly acknowledge your contribution (with your permission)
5. **Disclosure**: We follow coordinated disclosure practices

## Security Considerations for Implementers

### API Integration Security

When implementing the Bank iD Wallet API, developers must follow these critical security practices:

#### 1. Authentication & Authorization

- **Always use HTTPS/TLS 1.3** for all API communications
- **Never expose API credentials** in client-side code or public repositories
- **Rotate credentials regularly** according to your organization's security policy
- **Use strong authentication mechanisms** as specified in the ARF (Architecture and Reference Framework) and other stndards

#### 2. Data Protection

- **Encrypt sensitive data** both in transit and at rest
- **Minimize data retention** - only store data as long as legally required
- **Implement proper access controls** following the principle of least privilege
- **Pseudonymize or anonymize** personal data where possible
- **Comply with GDPR** and other applicable data protection regulations

#### 3. Cryptographic Requirements

- **Use approved cryptographic algorithms** as specified in eIDAS and ARF
- **Implement proper key management** practices
- **Validate all digital signatures** according to specification
- **Use secure random number generation** for all cryptographic operations
- **Follow ETSI standards** for qualified electronic signatures and seals

#### 4. Input Validation & Output Encoding

- **Validate all input** against strict schemas
- **Sanitize user-provided data** to prevent injection attacks
- **Encode output** appropriately for the context (HTML, JSON, etc.)
- **Implement rate limiting** to prevent abuse
- **Use parameterized queries** for database operations


#### 5. API-Specific Security

- **Validate OAuth 2.0 / OpenID Connect flows** according to specification
- **Implement PKCE** (Proof Key for Code Exchange) for mobile and SPA clients
- **Verify JWT signatures** and validate all claims
- **Check certificate validity** and revocation status (OCSP/CRL)
- **Implement proper error handling** without leaking sensitive information

### EUDI Wallet Security Requirements

Implementations must comply with:

- **eIDAS Regulation** (EU) No 910/2014 and amendments
- **ARF** (Architecture and Reference Framework) for EUDI Wallet
- **ISO/IEC 18013-5** for mobile driving license (mDL) where applicable
- **ISO/IEC 23220** series for building blocks
- **ETSI standards** for qualified trust services
- **National security frameworks** as applicable

### Common Vulnerabilities to Avoid

#### Authentication Vulnerabilities
- Broken authentication mechanisms
- Weak password policies
- Session fixation attacks
- Credential stuffing vulnerabilities

#### Authorization Vulnerabilities
- Broken access control
- Insecure direct object references (IDOR)
- Path traversal vulnerabilities
- Privilege escalation

#### Data Exposure Vulnerabilities
- Sensitive data in logs
- Unencrypted communications
- Inadequate cryptography
- Information disclosure in error messages

#### Injection Vulnerabilities
- SQL injection
- LDAP injection
- XML/JSON injection
- Command injection

#### Configuration Vulnerabilities
- Default credentials
- Misconfigured CORS policies
- Exposed debugging endpoints
- Unnecessary services enabled

## Security Best Practices

### For Service Providers

1. **Conduct regular security assessments** of your implementation
2. **Implement security monitoring** and logging
3. **Maintain an incident response plan**
4. **Keep dependencies updated** and patch vulnerabilities promptly
5. **Train development teams** on secure coding practices
6. **Perform penetration testing** before production deployment
7. **Implement defense in depth** strategies

### For Wallet Providers

1. **Implement secure key storage** using hardware security modules (HSM) or secure enclaves
2. **Protect biometric data** according to biometric protection guidelines
3. **Implement attestation** mechanisms for device and application integrity
4. **Follow mobile application security** best practices (OWASP MASVS)
5. **Implement secure backup and recovery** mechanisms
6. **Ensure secure communication** with relying parties and issuers


## Resources

### Official Documentation
- [eIDAS Regulation](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32014R0910)
- [EUDI Wallet ARF](https://github.com/eu-digital-identity-wallet/eudi-doc-architecture-and-reference-framework)
- [ETSI Standards](https://www.etsi.org/standards)

### Security Guidelines
- [OWASP API Security Top 10](https://owasp.org/www-project-api-security/)
- [OWASP Mobile Security](https://owasp.org/www-project-mobile-security/)
- [OAuth 2.0 Security Best Practices](https://datatracker.ietf.org/doc/html/draft-ietf-oauth-security-topics)

### Contact
- **General inquiries**: use this repository's Issues
- **Security issues**: filip@bankid.cz
- **Technical support**: see our Discord server

## Acknowledgments

We appreciate the security research community's efforts in responsibly disclosing vulnerabilities. Contributors who report valid security issues may be acknowledged in our security advisories (with their permission).

---

**Last Updated**: January 2025  
**Version**: 1.0

This security policy is subject to change. Please check regularly for updates.