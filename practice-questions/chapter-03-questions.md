## Chapter 3: Domain 3: Risk, Audit, and Compliance — Practice Questions

**Q1.** A mid-market SaaS company wants to evaluate a prospective cloud provider's security posture quickly and at no cost, before committing to a formal contract. The provider has published to the CSA STAR Registry. Which STAR level should the company review first?

A) STAR Level 3 – Continuous Auditing
B) STAR Level 2 – Attestation
C) STAR Level 1 – Self-Assessment
D) STAR Level 2 – Certification

<details>
<summary>Answer</summary>

**Correct: C**

STAR Level 1 is a free, publicly available self-assessment (CAIQ or CCM submission) requiring no third-party auditor — ideal for a quick initial screen with no cost.

**Why the others are wrong:**
- Level 3 (Continuous Auditing) is the most rigorous and least commonly available level, not a quick first check.
- Level 2 Attestation requires an accredited third-party auditor (SOC 2 + CCM), which involves cost and time, not a free quick review.
- Level 2 Certification requires an accredited auditor (ISO/IEC 27001 + CCM), also not free or immediate.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** Which document should an organization use to conduct a detailed, control-by-control self-assessment of a cloud provider's implemented security controls?

A) The provider's SOC 2 Type II report
B) The Consensus Assessments Initiative Questionnaire (CAIQ)
C) The provider's published SLA
D) The provider's penetration test results

<details>
<summary>Answer</summary>

**Correct: B**

CAIQ is a standardized set of yes/no questions directly correlated to CCM control specifications, purpose-built for structured self-assessment.

**Why the others are wrong:**
- SOC 2 reports are third-party attestations, not a self-assessment questionnaire structure mapped 1:1 to CCM.
- An SLA defines service commitments, not security control implementation status.
- Penetration test results address technical vulnerabilities, not a structured control assessment.

</details>

---

**Q3.** Which statement best describes the relationship between the CSA Cloud Controls Matrix (CCM) and CAIQ?

A) CCM defines the control specifications; CAIQ operationalizes those controls as a yes/no self-assessment questionnaire
B) CCM and CAIQ are competing frameworks published by different organizations
C) CAIQ replaces CCM for cloud providers seeking ISO 27001 certification
D) CCM is used only by auditors, while CAIQ is used only by regulators

<details>
<summary>Answer</summary>

**Correct: A**

CCM is the control framework (17 domains, 197 control specifications); CAIQ translates those controls into assessable questions a provider answers to demonstrate implementation.

**Why the others are wrong:**
- Both are published by CSA and are designed to work together, not compete.
- CAIQ does not replace CCM for certification — STAR Certification pairs ISO 27001 with CCM mapping, not CAIQ alone.
- Both are used by customers, providers, and auditors — neither is restricted to a single audience.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q4.** How many control domains does the CSA Cloud Controls Matrix (CCM) v4 organize its control specifications into?

A) 14
B) 17
C) 20
D) 12

<details>
<summary>Answer</summary>

**Correct: B**

CCM v4 organizes 197 control specifications across 17 control domains (e.g., IAM, DSP, CEK, GRC).

**Why the others are wrong:**
- 14 is not the correct domain count for CCM v4.
- 20 overstates the number of domains defined in CCM v4.
- 12 understates the number of domains in CCM v4.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q5.** A customer relies on its cloud provider's ISO/IEC 27001 certification to satisfy physical datacenter security requirements, but independently implements its own encryption key management controls for data it stores in the cloud. This scenario best illustrates which concept?

A) Vendor lock-in mitigation
B) Continuous auditing via STAR Level 3
C) Compliance inheritance under a shared responsibility model
D) Regulatory arbitrage

<details>
<summary>Answer</summary>

**Correct: C**

The customer inherits assurance for provider-controlled areas (physical security) from the CSP's certification, while retaining responsibility for customer-controlled areas (encryption/key management) — the core of compliance inheritance.

**Why the others are wrong:**
- This scenario has nothing to do with switching costs between providers.
- STAR Level 3 refers to continuous self-assessment/auditing methodology, not this inheritance split.
- Regulatory arbitrage refers to exploiting jurisdictional differences, unrelated to this scenario.

</details>

---

**Q6.** A financial services customer wants to validate its cloud provider's security controls but the provider will not permit customer-led on-site audits due to multi-tenant infrastructure. What should the customer do instead?

A) Terminate the contract, since the provider cannot be audited
B) Accept the provider's marketing materials as sufficient evidence
C) Require the provider to grant root access to underlying hypervisors for inspection
D) Request third-party audit reports such as SOC 2 Type II or ISO 27001 certification, or review the CSA STAR registry entry

<details>
<summary>Answer</summary>

**Correct: D**

Because direct customer audits are typically impractical in multi-tenant cloud environments, industry practice relies on independent third-party attestations (SOC 2, ISO 27001) or CSA STAR entries as substitute assurance.

**Why the others are wrong:**
- Refusing on-site audits is standard industry practice, not grounds alone for termination.
- Marketing materials provide no independent assurance and are not audit evidence.
- Providers never grant customers hypervisor-level access; this violates isolation and security boundaries.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** Under the ENISA cloud computing risk assessment approach, which category of risk includes vendor lock-in and loss of governance?

A) Technical risks
B) Legal risks
C) Risks not specific to the cloud
D) Policy and organizational risks

<details>
<summary>Answer</summary>

**Correct: D**

ENISA classifies loss of governance and vendor lock-in as policy and organizational risks, since they stem from the customer-provider relationship and contractual/operational dependency rather than technology itself.

**Why the others are wrong:**
- Technical risks in ENISA's model cover issues like resource exhaustion, isolation failure, and insecure APIs.
- Legal risks cover jurisdictional and regulatory exposure, not governance/lock-in dynamics.
- Risks not specific to cloud are generic IT risks (e.g., network outages) that exist regardless of deployment model.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q8.** What best distinguishes STAR Level 3 (Continuous Auditing/Self-Assessment) from STAR Level 2 (Attestation/Certification)?

A) Level 3 is free while Level 2 always requires payment
B) Level 3 does not use the CCM framework, while Level 2 does
C) Level 3 is only available to government cloud providers
D) Level 3 provides near real-time/ongoing validation of controls rather than a point-in-time audit snapshot

<details>
<summary>Answer</summary>

**Correct: D**

STAR Continuous is designed to validate security control effectiveness on an ongoing/near-continuous basis, addressing the limitation that traditional point-in-time audits (Level 2) can become outdated.

**Why the others are wrong:**
- Cost is not the defining distinction between the two levels; both can involve fees depending on scope.
- STAR Continuous still uses CCM as its control baseline, same as Level 2.
- STAR Level 3 is available to any cloud provider meeting its requirements, not restricted to government providers.

</details>

---

