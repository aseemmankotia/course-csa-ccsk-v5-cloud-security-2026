## Domain 5: Identity and Access Management — Cheat Sheet (9% weight)

### Federation vs Directory Sync
| | Federation | Directory Synchronization |
|---|---|---|
| Mechanism | Trust relationship between IdPs | Periodic replication of identity data |
| Credentials | Never copied, assertions trusted | Attributes/hashes copied to 2nd store |
| Real-time? | Yes (assertion at login time) | No — batch/scheduled |
| Protocols | SAML, OIDC, WS-Fed | LDAP sync, AD Connect-style tools |

### SAML vs OIDC
| | SAML 2.0 | OIDC |
|---|---|---|
| Format | XML | JSON / JWT |
| Transport | Browser redirect/POST | REST/HTTPS |
| Built on | Standalone protocol | Layer on top of OAuth 2.0 |
| Best fit | Enterprise web SSO, legacy apps | Mobile, SPA, API-driven, social login |

### RBAC vs ABAC
| | RBAC | ABAC |
|---|---|---|
| Basis | Predefined static roles | Dynamic attributes (user/resource/env) |
| Flexibility | Low — role explosion risk | High — context-aware |
| Use when | Stable org structure | Need context (time, device, location, classification) |

### MFA Factors (NIST-aligned)
1. Something you **know** — password/PIN
2. Something you **have** — token/phone/smartcard
3. Something you **are** — biometric
> Two factors from the *same* category ≠ MFA.

### PAM / Just-in-Time Access
- Vault privileged credentials centrally — never shared/static passwords
- Broker sessions — user never sees raw credential
- Auto-rotate credential after each checkout
- Record/audit privileged sessions
- **JIT**: grant elevation only for task duration, auto-revoke after
- Anti-pattern (exam trap): permanent standing admin roles "for convenience"

### Identity Lifecycle (Joiner-Mover-Leaver)
- **Joiner**: provision on hire
- **Mover**: adjust entitlements on role/dept change
- **Leaver**: deprovision on termination — #1 tested failure point (orphaned privileged accounts)
- **Entitlement sprawl**: unused/excess permissions accumulating over time → mitigate with periodic access reviews + least privilege

### Cross-Provider Federation Challenges
- Inconsistent attribute schemas across IdPs
- Mixed protocol support (SAML vs OIDC vs proprietary)
- Trust configuration complexity in multi-cloud
- Common mitigation: centralized identity broker/hub pattern

### Exam Traps
- Confusing federation (trust) with synchronization (replication)
- Assuming RBAC handles dynamic/contextual scenarios (it doesn't — that's ABAC)
- Treating standing admin access as acceptable if MFA is enabled (PAM/JIT still required)
- Forgetting deprovisioning is part of lifecycle management, not just onboarding
