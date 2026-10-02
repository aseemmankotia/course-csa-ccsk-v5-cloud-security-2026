## Chapter 3: Domain 3: Risk, Audit, and Compliance — Flashcards

| # | Front (Question) | Back (Answer) |
|---|-----------------|---------------|
| 1 | How many control domains and control specifications does CSA CCM v4 contain? | 17 control domains, 197 control specifications. Exam tip: CCM maps each control to multiple standards (ISO 27001, NIST 800-53, PCI DSS). |
| 2 | CCM vs CAIQ — what's the difference? | CCM = the control framework defining what controls should exist. CAIQ = the self-assessment questionnaire (yes/no) a provider completes to show whether CCM controls are implemented. |
| 3 | CSA STAR Level 1 | Self-Assessment. Provider publishes a completed CAIQ or CCM mapping to the STAR Registry. Free, no independent validation. |
| 4 | CSA STAR Level 2 | Third-Party Assessment. STAR Attestation = SOC 2 Type II + CCM mapping; STAR Certification = ISO/IEC 27001 + CCM mapping. Requires accredited auditor. |
| 5 | CSA STAR Level 3 | Continuous Auditing / Continuous Self-Assessment (STAR Continuous). Near real-time control validation rather than a point-in-time snapshot. |
| 6 | ENISA's four cloud risk categories | 1) Policy & Organizational, 2) Technical, 3) Legal, 4) Not specific to cloud (generic IT risks). |
| 7 | Which ENISA category covers vendor lock-in and loss of governance? | Policy and Organizational risks — these arise from the customer-provider relationship, not underlying technology. |
| 8 | What is compliance inheritance? | A cloud customer inherits assurance for CSP-controlled areas (e.g., physical security, hypervisor) from the provider's audits/certifications, while remaining responsible for customer-controlled controls (e.g., encryption, IAM config). |
| 9 | How do you validate a CSP's security when on-site customer audits aren't permitted? | Request independent third-party reports (SOC 2 Type II, ISO 27001 certificate) or review the CSA STAR registry entry — standard practice for multi-tenant environments. |
| 10 | CCM domain code 'CEK' stands for? | Cryptography, Encryption & Key Management — one of CCM v4's 17 control domains. |
| 11 | SOC 2 Type I vs Type II | Type I = control design assessed at a single point in time. Type II = operating effectiveness of controls tested over a period (commonly 6–12 months). Exam tip: Type II is the stronger evidence for cloud assurance. |
| 12 | How does CCM help map regulatory obligations to cloud controls? | CCM includes a 'Scope Applicability' mapping that cross-references each control specification to external standards/regulations (ISO 27001, PCI DSS, HIPAA, NIST), letting assessors translate legal requirements into concrete cloud controls. |
