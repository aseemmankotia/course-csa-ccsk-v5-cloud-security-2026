## Chapter 8: Domain 9: Data Security — Practice Questions

**Q1.** A financial services firm requires that encryption keys for regulated data never be accessible to the cloud provider, even under legal compulsion or subpoena directed at the provider. Which key management model BEST meets this requirement?

A) Provider-managed keys
B) BYOK (Bring Your Own Key)
C) HYOK (Hold Your Own Key)
D) Customer-managed keys stored in the provider's HSM

<details>
<summary>Answer</summary>

**Correct: C**

HYOK keeps key material entirely outside the cloud provider's environment (typically on-premises or in a third-party key manager), so the provider can never access or be compelled to produce the key.

**Why the others are wrong:**
- Provider-managed keys are fully generated and held by the provider — the opposite of the requirement.
- BYOK lets the customer generate the key, but it is still uploaded into and operationally accessible from the provider's KMS/HSM.
- Customer-managed keys in the provider's HSM still reside within provider infrastructure, so the provider retains some access path.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** An e-commerce platform must protect stored credit card numbers used by a legacy application that expects a value in the same 16-digit format, while ensuring the real card number is never recoverable outside a secure vault. Which technique BEST satisfies this?

A) Symmetric encryption
B) Asymmetric encryption
C) Tokenization
D) Hashing

<details>
<summary>Answer</summary>

**Correct: C**

Tokenization replaces the sensitive value with a format-preserving, non-mathematically-derived token; only the token vault can map it back to the real PAN, reducing PCI DSS scope.

**Why the others are wrong:**
- Symmetric encryption is reversible by anyone holding the key, and ciphertext typically doesn't preserve the original format.
- Asymmetric encryption is computationally heavier and also reversible with the private key — not the intended isolation model.
- Hashing is one-way and cannot reproduce the original 16-digit format for the legacy app.

</details>

---

**Q3.** An organization deploys a DLP solution to inspect outbound emails for Social Security numbers before they leave the corporate network. Which stage of the Data Security Lifecycle does this control primarily protect?

A) Create
B) Share
C) Store
D) Archive

<details>
<summary>Answer</summary>

**Correct: B**

The Share phase covers data leaving the organization's control (email, external transfer, collaboration), which is exactly where egress DLP inspection applies.

**Why the others are wrong:**
- Create is the point data is generated or classified, not where it's transmitted externally.
- Store refers to data at rest controls like encryption of a database or bucket, not outbound transmission.
- Archive concerns long-term retention controls, not active outbound communication.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q4.** For encrypting data in transit between microservices within a cloud VPC, which configuration matches the CCSK baseline recommendation?

A) SSL 3.0
B) TLS 1.2 or higher
C) No encryption needed since traffic stays inside a trusted VPC
D) WEP

<details>
<summary>Answer</summary>

**Correct: B**

TLS 1.2+ (with TLS 1.3 preferred) is the minimum modern standard for encrypting data in transit, regardless of whether traffic appears to stay within a 'trusted' network boundary.

**Why the others are wrong:**
- SSL 3.0 is deprecated and cryptographically broken (POODLE vulnerability).
- Assuming internal VPC traffic doesn't need encryption ignores the cloud's shared-tenancy and zero-trust guidance the exam tests.
- WEP is a legacy Wi-Fi protocol, not applicable to service-to-service encryption and is itself insecure.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q5.** What is the primary difference between BYOK and HYOK key management models?

A) BYOK stores keys entirely offsite while HYOK keys reside in the provider's HSM
B) BYOK allows customer-generated keys to be uploaded into the provider's key management service, while HYOK keeps keys physically outside the provider's environment at all times
C) They are identical, differing only in vendor terminology
D) HYOK is only available for storage services while BYOK is only for compute services

<details>
<summary>Answer</summary>

**Correct: B**

BYOK means the customer generates the key but still imports/stores it into the CSP's KMS/HSM for use; HYOK means the key never leaves customer-controlled infrastructure, and the provider calls out to it for cryptographic operations.

**Why the others are wrong:**
- This reverses the models — BYOK keys live in provider infrastructure, HYOK keys stay external.
- The models have materially different trust and access boundaries, not just naming differences.
- Neither model is restricted to a specific service category; both can apply across storage, compute, and database services.

</details>

---

**Q6.** An HR system stores employee salary and disciplinary records. Unauthorized disclosure would cause significant legal and reputational harm to the organization. Under a typical four-tier classification scheme, which label should this data receive?

A) Restricted
B) Public
C) Internal
D) Confidential

<details>
<summary>Answer</summary>

**Correct: A**

Data whose disclosure causes significant legal/reputational harm maps to the highest sensitivity tier (Restricted), which mandates the strictest access, encryption, and DLP controls.

**Why the others are wrong:**
- Public data has no confidentiality requirement, the opposite of this scenario.
- Internal is for general business data with limited harm if disclosed, not significant legal/reputational impact.
- Confidential is a moderate-sensitivity tier below the highest-impact category described here.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** When using customer-managed keys (CMK) in a cloud KMS, which practice does the exam emphasize for limiting the blast radius of a key compromise?

A) Never rotate keys once created to avoid re-encryption overhead
B) Sharing the same key across all data stores for consistency
C) Regular key rotation combined with strict IAM policies scoping key usage
D) Storing key material directly in application source code for quick access

<details>
<summary>Answer</summary>

**Correct: C**

Rotating keys periodically and scoping which identities/roles can use a given key limits how much data is exposed if any single key is compromised.

**Why the others are wrong:**
- Never rotating keys increases long-term exposure if a key is ever compromised.
- Reusing one key across all stores maximizes blast radius — a single compromise exposes everything.
- Embedding key material in source code is a severe anti-pattern that exposes keys via repos, logs, or builds.

</details>

---

**Q8.** A company is decommissioning a virtual disk that stored regulated data in a multi-tenant public cloud. What is the best practice for the Destroy phase of the Data Security Lifecycle in this environment?

A) Cryptographic erasure by destroying the encryption keys, since physical media sanitization is not accessible in a multi-tenant public cloud
B) Physically degauss the drive before releasing it back to the provider
C) Assume the hypervisor automatically wipes data, so no customer action is needed
D) Manually overwrite blocks via SSH before requesting volume deletion

<details>
<summary>Answer</summary>

**Correct: A**

In multi-tenant public cloud, customers cannot physically access or sanitize underlying storage media, so cryptographic erasure — destroying the keys that protected the encrypted data — is the recognized substitute for physical destruction.

**Why the others are wrong:**
- Degaussing requires physical access to the media, which public cloud customers do not have.
- Relying on undocumented hypervisor behavior without verification is not an acceptable control and shifts risk to assumption.
- Manual block overwrite is unreliable in virtualized, thin-provisioned, and replicated storage and is not the recommended control.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

