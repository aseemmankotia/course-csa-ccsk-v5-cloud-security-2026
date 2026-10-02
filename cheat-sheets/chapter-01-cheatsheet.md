# Domain 1 Cheat Sheet: Cloud Computing Concepts and Architectures (8%)

## NIST 5 Essential Characteristics (SP 800-145)
| Characteristic | Meaning |
|---|---|
| On-demand self-service | Provision resources without human interaction with provider |
| Broad network access | Available over network via standard mechanisms (thin/thick clients) |
| Resource pooling | Multi-tenant model; dynamic allocation; abstracted location |
| Rapid elasticity | Scale up/down, appears unlimited to consumer |
| Measured service | Usage automatically metered → billing transparency |

## Service Models & Responsibility Shift
| Model | CSP Manages | Customer Manages |
|---|---|---|
| IaaS | Virtualization, servers, storage, network | OS, middleware, runtime, app, data |
| PaaS | + OS, middleware, runtime | App code, data |
| SaaS | + Application | Data, users/IAM config, endpoint |

**Rule:** Responsibility line moves UP the stack from IaaS → PaaS → SaaS. CSP's share of responsibility increases; customer's share shrinks but NEVER hits zero.

## Deployment Models (NIST)
| Model | Definition |
|---|---|
| Private | Exclusive use by single org |
| Community | Exclusive use by group of orgs with shared concerns (compliance, mission) |
| Public | Open to general public |
| Hybrid | 2+ distinct infrastructures bound for portability (e.g., cloud bursting) |
| Multi-cloud | Use of 2+ public cloud providers simultaneously (not an official NIST term, but tested in CCSK) |

**Exam trap:** Private vs Community — Community = shared among MULTIPLE orgs; Private = ONE org only.
**Exam trap:** Hybrid ≠ Multi-cloud. Hybrid mixes deployment TYPES (private+public); Multi-cloud mixes PROVIDERS (AWS+Azure), both public.

## CSA Logical (Stack) Model — bottom to top
1. Facility
2. Network
3. Hardware
4. Resource Abstraction & Control (hypervisor/virtualization — multi-tenancy isolation happens here)
5. Applications
(Orchestration cuts across all layers for automation/management)

**Rule:** Lower layers = CSP control dominant. Upper layers = customer control increases (depending on service model).

## Shared Responsibility — The Exam's Central Lens
- **Security OF the cloud** = CSP (physical infra, hardware, virtualization)
- **Security IN the cloud** = Customer (data, identities, access config, in SaaS also endpoints)
- This split exists in EVERY service model — only the boundary/line shifts depending on IaaS/PaaS/SaaS.
- Customer is NEVER 100% relieved of responsibility, even in SaaS (data classification, access management remain).

## Quick Memory Tricks
- NIST characteristics mnemonic: **O-B-R-R-M** (On-demand, Broad network, Resource pooling, Rapid elasticity, Measured service)
- Service model responsibility shift: 'IaaS = most customer work, SaaS = least customer work, PaaS = middle ground'
- Community cloud = 'private cloud for a group,' not a public offering
