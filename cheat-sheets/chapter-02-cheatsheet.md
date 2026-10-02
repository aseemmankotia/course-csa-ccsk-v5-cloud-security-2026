# Domain 2 & 4 Cheat Sheet: Cloud Governance & Organization Management

## Governance Document Hierarchy
| Level | Mandatory? | Purpose | Example |
|---|---|---|---|
| Policy | Yes | High-level statement of management intent (WHAT/WHY) | "All customer data must be encrypted" |
| Standard | Yes | Specific, measurable requirement supporting the policy | "Use AES-256 or stronger" |
| Procedure | Yes | Step-by-step instructions to implement the standard | "Steps to enable KMS encryption on volume creation" |
| Guideline | No (optional) | Recommended best practice | "Consider rotating keys every 90 days" |

**Exam trap:** Guideline is the ONLY non-mandatory artifact. Watch for distractors that make a guideline sound compulsory.

## Roles & Responsibilities
| Role | Typical Responsibility |
|---|---|
| Board / Executive (CISO/CIO) | Approves Policy |
| GRC / Security team | Defines Standards, oversees compliance |
| IT Operations / Engineers | Execute Procedures |
| All staff | Encouraged to follow Guidelines |

## Vendor & Contract Management Essentials
- **Shared responsibility mapping** — explicitly define provider vs customer duties in the contract.
- **Right-to-audit clause** — contractual ability to verify provider's controls (distinct from SLA/NDA).
- **SLA** — defines uptime/performance commitments, not audit rights.
- **Exit strategy / data portability** — must be agreed BEFORE signing to avoid lock-in.
- **Due diligence** — assess financials, certifications (SOC 2, ISO 27001), track record — done at onboarding AND periodically thereafter.

## Organization-Wide Guardrails
| Mechanism | Provider | Scope | Precedence |
|---|---|---|---|
| SCP | AWS | All accounts in an Organization | Overrides IAM; sets max permission boundary |
| Organization Policy | GCP | All projects in an Org | Same concept as SCP |
| Azure Policy | Azure | Management groups/subscriptions | Same concept as SCP |

**Rule:** A guardrail at the org/management level ALWAYS takes precedence over an account-level IAM policy — IAM can only grant permissions within the guardrail's boundary, never exceed it.

## Multi-Account / Multi-Tenant Structure
- Use separate accounts per environment (dev/test/prod) and per business unit for **blast-radius isolation**.
- A "landing zone" or "account factory" pattern standardizes account creation with baseline guardrails pre-applied.

## Multi-Cloud Governance
- Central GRC function defines **common policies/standards**, then maps them to each provider's native controls (SCP, Org Policy, Azure Policy).
- Do NOT let each cloud team build an independent governance framework — this creates inconsistent risk posture.

## Quick Memory Trick
"**P-S-P-G**": **P**olicy sets intent, **S**tandard sets the bar, **P**rocedure sets the steps, **G**uideline is just a suggestion.
