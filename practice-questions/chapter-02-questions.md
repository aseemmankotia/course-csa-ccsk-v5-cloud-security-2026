## Chapter 2: Domain 2: Cloud Governance and Domain 4: Organization Management — Practice Questions

**Q1.** A company wants a rule that guarantees no storage bucket can ever be made publicly accessible in ANY account across its entire cloud organization, regardless of what permissions an individual account admin grants. Which mechanism BEST achieves this?

A) An IAM policy attached to each user who manages storage
B) A written procedure instructing admins not to enable public access
C) An organization-wide guardrail (e.g., SCP or organization policy) enforced at the management/root level
D) A guideline published in the internal security wiki

<details>
<summary>Answer</summary>

**Correct: C**

Organization-wide guardrails (SCPs/organization policies) are enforced above IAM at the management account level and cannot be overridden by account-level permissions, guaranteeing the restriction organization-wide.

**Why the others are wrong:**
- IAM policies are scoped per-account/user and can be changed or bypassed by anyone with admin rights in that account.
- A procedure is a documented instruction, not a technical enforcement mechanism — it relies on human compliance.
- A guideline is explicitly non-mandatory and provides no enforcement at all.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** A cloud customer negotiating a new vendor contract wants the contractual ability to independently verify the provider's security controls after signing. Which contract element should be included?

A) A right-to-audit clause
B) A service level agreement (SLA) only
C) A non-disclosure agreement (NDA)
D) A standard data processing addendum with no audit rights

<details>
<summary>Answer</summary>

**Correct: A**

A right-to-audit clause specifically grants the customer (or a designated third party) the contractual ability to verify the provider's controls, which SLAs and NDAs do not provide.

**Why the others are wrong:**
- An SLA defines performance/uptime commitments, not audit rights.
- An NDA protects confidential information exchange; it does not grant verification access.
- A DPA without audit rights covers data processing terms but leaves the customer unable to independently verify compliance.

</details>

---

**Q3.** The CISO issues a high-level statement: 'All customer data must be encrypted at rest and in transit.' No specific algorithm or key length is specified. This document is an example of which governance artifact?

A) Procedure
B) Guideline
C) Policy
D) Standard

<details>
<summary>Answer</summary>

**Correct: C**

A policy is a high-level, mandatory statement of management intent — the 'what and why' — without operational specifics.

**Why the others are wrong:**
- A procedure would give step-by-step implementation instructions, which are absent here.
- A guideline would be optional/recommended, but this statement uses mandatory language ('must').
- A standard would specify a measurable requirement, such as a specific algorithm or key length, which is missing.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q4.** A document states: 'All data at rest must be encrypted using AES-256 or stronger.' Which governance artifact does this represent?

A) Standard
B) Policy
C) Guideline
D) Procedure

<details>
<summary>Answer</summary>

**Correct: A**

A standard is a mandatory, measurable requirement that supports and operationalizes a higher-level policy — specifying an exact algorithm and key length matches this definition.

**Why the others are wrong:**
- A policy would be broader intent-level language without a specific algorithm.
- A guideline would be phrased as a recommendation ('consider using'), not a mandatory requirement.
- A procedure would describe the step-by-step process to configure the encryption, not just state the requirement.

</details>

---

**Q5.** Which of the following governance artifacts is the ONLY one that is explicitly non-mandatory?

A) Standard
B) Procedure
C) Policy
D) Guideline

<details>
<summary>Answer</summary>

**Correct: D**

Guidelines are recommended best practices intended to inform decisions but are not enforceable requirements, unlike policies, standards, and procedures.

**Why the others are wrong:**
- Standards are mandatory measurable requirements supporting a policy.
- Procedures are mandatory step-by-step instructions for implementing standards.
- Policies are mandatory high-level statements of management intent.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q6.** A large enterprise runs workloads across three different cloud providers. Auditors ask how consistent security governance is maintained across all three. What is the BEST practice?

A) Let each cloud team independently define its own governance framework for its provider
B) Govern only the primary provider and rely on default settings for the others
C) A central GRC function defines common policies and standards, then maps them to each provider's native control implementation
D) Adopt each provider's built-in security defaults as the organization's governance framework

<details>
<summary>Answer</summary>

**Correct: C**

Effective multi-cloud governance requires a centralized policy/standard baseline mapped consistently to each provider's specific controls, ensuring uniform risk posture despite differing native tooling.

**Why the others are wrong:**
- Independent frameworks per team create inconsistent risk posture and audit gaps across the organization.
- Ignoring secondary providers leaves unmanaged risk and violates the principle of organization-wide oversight.
- Provider default settings vary widely and are not designed to reflect a specific organization's risk appetite or compliance obligations.

</details>

---

**Q7.** In AWS, which mechanism enforces preventive guardrails across all accounts within an AWS Organization, taking precedence over any IAM policy in a member account?

A) IAM Policy
B) Service Control Policy (SCP)
C) Bucket Policy
D) Resource-based policy

<details>
<summary>Answer</summary>

**Correct: B**

SCPs are applied at the AWS Organizations level and define the maximum available permissions for all accounts under them; IAM policies can only grant permissions within that boundary, never exceed it.

**Why the others are wrong:**
- IAM policies operate within a single account and cannot restrict other accounts in the organization.
- Bucket policies control access to a specific storage bucket only, not organization-wide behavior.
- Resource-based policies are attached to individual resources and do not provide organization-wide enforcement.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q8.** What is the primary purpose of cloud governance as described in cloud security frameworks?

A) To eliminate the need for vendor contracts and SLAs
B) To replace technical security controls entirely with policy documents
C) To establish accountability, decision rights, and processes ensuring cloud usage aligns with organizational objectives and risk appetite
D) To transfer all operational and security risk to the cloud provider

<details>
<summary>Answer</summary>

**Correct: C**

Cloud governance defines who is accountable for decisions and ensures cloud adoption and operations align with organizational risk tolerance and business objectives — it is a management discipline, not a technical control.

**Why the others are wrong:**
- Governance actually reinforces the need for well-defined vendor contracts, it does not eliminate them.
- Governance documents guide and require technical controls; they do not replace the need for them.
- Risk cannot be fully transferred to the provider — the customer retains accountability under the shared responsibility model.

</details>

---

