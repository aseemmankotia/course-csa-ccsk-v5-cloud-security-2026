## Domain 3 Cheat Sheet: Risk, Audit, and Compliance

### CCM (Cloud Controls Matrix) vs CAIQ
| | CCM | CAIQ |
|---|---|---|
| What it is | Control framework | Self-assessment questionnaire |
| Structure | 17 domains, 197 control specs | Yes/No questions mapped to CCM controls |
| Purpose | Defines *what* controls should exist | Lets a CSP *report* whether controls exist |
| Maps to | ISO 27001, NIST 800-53, PCI DSS, etc. | Directly correlates to CCM control IDs |

### CCM v4 — 17 Control Domains (memorize the acronyms)
A&A (Audit & Assurance) · AIS (App & Interface Security) · BCR (Business Continuity/Resilience) · CCC (Change Control) · CEK (Cryptography, Encryption & Key Mgmt) · DCS (Datacenter Security) · DSP (Data Security & Privacy Lifecycle) · GRC (Governance, Risk & Compliance) · HRS (Human Resources) · IAM (Identity & Access Mgmt) · IPY (Interoperability & Portability) · IVS (Infrastructure & Virtualization Security) · LOG (Logging & Monitoring) · SEF (Security Incident Mgmt/eDiscovery/Forensics) · STA (Supply Chain/Transparency) · TVM (Threat & Vulnerability Mgmt) · UEM (Universal Endpoint Mgmt)

### CSA STAR Registry — 3 Levels
| Level | Name | Basis | Validated By |
|---|---|---|---|
| 1 | Self-Assessment | CAIQ or CCM | Provider (self) |
| 2 | Attestation / Certification | SOC 2 + CCM (Attestation) or ISO 27001 + CCM (Certification) | Accredited third-party auditor |
| 3 | Continuous | CCM, near real-time | Automated/continuous validation |

### ENISA Cloud Risk Categories
- **Policy & Organizational** — loss of governance, vendor lock-in, compliance risk, supply chain failure
- **Technical** — resource exhaustion, isolation failure, insecure APIs, malicious insider
- **Legal** — jurisdiction, subpoena/e-discovery, licensing risk
- **Not specific to cloud** — network outage, natural disaster, generic IT risk

### Compliance Inheritance / Shared Assessment
- Customer **inherits** assurance from CSP audits for provider-controlled layers (physical security, hypervisor, network).
- Customer remains **directly responsible** for controls they configure (IAM, encryption, data classification).
- Validate CSP claims via SOC 2 Type II, ISO 27001 certs, or STAR registry — **not** via direct on-site audit (usually disallowed in multi-tenant environments).

### Exam Traps
- Don't confuse CCM (framework) with CAIQ (questionnaire) — CCM defines controls, CAIQ assesses them.
- STAR Level 1 = free/self-reported; Level 2 = third-party validated; Level 3 = continuous, not point-in-time.
- SOC 2 **Type II** > Type I for cloud assurance (tests operating effectiveness over time, not just design).
