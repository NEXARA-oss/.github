# Security Policy

## Supported Versions

| Version | Supported |
|---|---|
| Latest `0.x` release | ✅ Active patches |
| Older releases | ❌ No security patches |

We strongly recommend always running the latest release.

## Reporting a Vulnerability

**Do not open a public GitHub issue for security vulnerabilities.**

Email **security@nexara.dev** with:

- A clear description of the vulnerability
- Steps to reproduce
- Potential impact assessment
- Your suggested severity (Critical / High / Medium / Low)

**Response timeline:**
- Acknowledgment: within **48 hours**
- Status update: within **7 days**
- Patch + disclosure: coordinated with reporter

We follow [Coordinated Vulnerability Disclosure](https://en.wikipedia.org/wiki/Coordinated_vulnerability_disclosure). We will work with you privately, release a patch, and credit you in the security advisory (unless you prefer anonymity).

## Security Scope

**In scope:**
- Remote code execution or command injection
- Authentication/authorization bypass in Nexara Studio
- Plugin sandbox escapes
- Data exfiltration via crafted workflow definitions
- Dependency vulnerabilities with known active exploits

**Out of scope:**
- Vulnerabilities requiring physical device access
- Issues in unsupported versions
- Theoretical vulnerabilities with no demonstrated impact

## PGP Key

Available at [nexara.dev/security.asc](https://nexara.dev/security.asc) for encrypted reports.

## Hall of Fame

Responsible disclosures are recognized at [nexara.dev/security/hall-of-fame](https://nexara.dev/security/hall-of-fame).
