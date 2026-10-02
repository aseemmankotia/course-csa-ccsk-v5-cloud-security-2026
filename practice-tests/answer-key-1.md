# Answer Key — Practice Test 1

**Q1. Correct: D**

Across all service models—IaaS, PaaS, and SaaS—the customer never transfers ownership of their data or accountability for who can access it. Identity, access management, and data governance stay with the customer even in SaaS, where the provider manages nearly everything else in the stack.

---

**Q2. Correct: A**

IaaS gives the customer control over the OS, middleware, and runtime configuration while the provider handles the physical hardware, network, and hypervisor—exactly matching the stated requirement.

---

**Q3. Correct: C**

A community cloud is provisioned for exclusive use by a specific group of organizations that share common concerns such as compliance requirements, with infrastructure managed and shared among that community rather than the public.

---

**Q4. Correct: D**

On-demand self-service means a consumer can unilaterally provision resources, such as server time or storage, automatically without needing to interact directly with a human at the provider.

---

**Q5. Correct: B**

A data portability and exit clause ensures the organization can retrieve its data in a usable format and confirm secure deletion by the provider, directly addressing vendor lock-in and exit strategy — a core CCSK governance concern in vendor contract negotiations.

---

**Q6. Correct: C**

STAR Level 2 requires an independent third-party audit (such as an ISO/IEC 27001 certification or SOC 2 attestation combined with the CCM) that validates the provider's controls, giving the assurance the organization needs beyond a self-report.

---

**Q7. Correct: C**

RTO defines the maximum acceptable time to restore a service after a disruption, making it the direct measure of restoration capability that governance teams use to validate resiliency commitments.

---

**Q8. Correct: D**

Standards translate a high-level policy statement of intent into specific, measurable, mandatory requirements (such as the exact algorithm and key length), sitting directly below policy in the governance hierarchy.

---

**Q9. Correct: B**

CCSK guidance recognizes that individual customer audits don't scale at cloud provider size, so CSA promotes using the CAIQ (self-assessment against CCM controls) combined with independent third-party attestations like SOC 2 Type II to gain assurance without requiring physical audits.

---

**Q10. Correct: A**

STAR Level 3, based on the Cloud Trust Protocol/continuous monitoring concept, is designed to give near real-time assurance of a provider's security control effectiveness rather than a snapshot assessment.

---

**Q11. Correct: C**

The CCM is a cybersecurity control framework organized into control domains, and each control includes mappings to major standards and regulations such as NIST, ISO 27001, and PCI DSS, making it the correct tool for cross-framework mapping.

---

**Q12. Correct: D**

CUECs describe controls the customer is expected to implement to complement the provider's controls; in SaaS, this commonly includes managing user identities, roles, and access within the application itself since the provider controls the underlying platform.

---

**Q13. Correct: B**

CSA guidance recommends using separate accounts/subscriptions as the primary isolation boundary because the account itself is a hard security boundary in most cloud providers, containing IAM, billing, and resource blast radius, while still allowing centralized governance through an organizational hierarchy (e.g., management groups, organizations).

---

**Q14. Correct: B**

Preventive guardrails (organization-wide policies enforced at the management/organization level, such as SCPs or policy-based restrictions) stop non-compliant actions from occurring in the first place, which is the only control type that can 'guarantee' resources are never deployed outside approved regions.

---

**Q15. Correct: C**

The root/master account has irrevocable, unrestricted privileges over the entire organization. CSA guidance recommends enabling strong MFA, tightly securing and monitoring its credentials, and using dedicated, restricted IAM roles for routine administration instead of the root account.

---

**Q16. Correct: C**

Each cloud provider implements its own organizational hierarchy, policy engine, and terminology (e.g., differing guardrail mechanisms and IAM models), making it difficult to apply one consistent security policy or control set uniformly across providers without translation or abstraction layers.

---

**Q17. Correct: A**

CCSK guidance emphasizes that federation concentrates trust in the IdP — compromise of the IdP compromises every relying party it federates to, so the IdP must be protected as critical infrastructure (hardened, monitored, and highly available).

---

**Q18. Correct: B**

CIEM is purpose-built to analyze and right-size entitlements across multi-cloud environments, covering both human and non-human identities and flagging excessive or unused permissions.

---

**Q19. Correct: D**

FIDO2/WebAuthn uses public-key cryptography bound to the origin/domain of the relying party, making it inherently phishing-resistant — CCSK identifies it as the strongest recommended factor for privileged cloud access.

---

**Q20. Correct: D**

CCSK distinguishes SAML as an XML-based protocol built for enterprise SSO/authentication assertions, versus OAuth 2.0 (an authorization framework) combined with OIDC (which adds an authentication/identity layer) as the modern, token-based standard suited to APIs, mobile, and cloud-native apps.

---

**Q21. Correct: A**

Centralizing normalized logs from all cloud environments into a single SIEM enables cross-provider correlation, real-time alerting, and consistent detection logic — the core goal of multi-cloud security monitoring per CSA guidance.

---

**Q22. Correct: D**

Cloud audit/activity logs are the management-plane record of API calls — capturing identity, action, resource, and timestamp — and are the primary source for detecting unauthorized configuration changes.

---

**Q23. Correct: C**

WORM/immutable storage with tightly restricted deletion permissions ensures that even a compromised privileged account cannot alter or purge log history, preserving forensic integrity.

---

**Q24. Correct: A**

In IaaS, the provider owns and monitors the physical infrastructure, hypervisor, and facility-level controls; the customer's monitoring responsibility begins at the OS/guest layer and above.

---

**Q25. Correct: D**

Micro-segmentation applies granular, identity- and workload-aware policies at the individual host or workload level, restricting lateral (east-west) movement so a compromised instance cannot freely communicate with unrelated workloads, which is exactly the scenario described.

---

**Q26. Correct: B**

SDN abstracts and decouples the control plane from the data plane, exposing network configuration through APIs. This allows security teams to programmatically define, automate, and centrally enforce granular network security policies (segmentation, routing, filtering) across dynamic cloud environments, which is a core security advantage CCSK emphasizes.

---

**Q27. Correct: B**

A default-deny posture combined with explicit, minimal, tier-specific allow rules enforces least privilege, ensures each tier can only communicate with what it legitimately needs (e.g., database only reachable from the app tier on its required port), and limits the impact of a compromise in any single tier.

---

**Q28. Correct: C**

SDP follows a zero-trust, 'authenticate first, connect second' model: it verifies identity and device posture before the network path to a resource is even exposed, effectively hiding infrastructure from unauthenticated users. A traditional VPN typically grants broad network access to a segment once connected, without this pre-connect verification and dynamic, per-resource cloaking.

---

**Q29. Correct: A**

Pod Security Standards (restricted profile) is the runtime control that directly disallows privileged containers, host namespace/PID/IPC sharing, and enforces non-root execution, which is the specific mechanism that prevents container-to-host escape via privilege escalation.

---

**Q30. Correct: A**

Over-permissioned serverless functions are a top CCSK-cited risk. The remediation is applying least privilege by scoping the execution role narrowly to the exact resources and actions required, since a compromised function inherits its assigned permissions.

---

**Q31. Correct: A**

Admission controllers intercept API requests at deployment time and can enforce policy checks such as image signature verification and trusted-registry provenance before a workload is scheduled, making them the correct enforcement point.

---

**Q32. Correct: D**

Disabling anonymous authentication on the kube-apiserver ensures every request must present valid credentials, closing off a well-known attack surface where unauthenticated requests could otherwise reach the API server with default RBAC bindings.

---

**Q33. Correct: C**

Crypto-shredding (destroying the encryption keys) is the recommended and often only practical way to guarantee data on media you don't physically control -- including provider-managed backups, snapshots, and distributed storage -- becomes permanently unrecoverable, since without the key the ciphertext is useless.

---

**Q34. Correct: B**

Tokenization replaces sensitive data with a non-sensitive surrogate (token) that has no exploitable value outside the tokenization vault. Systems that only handle the token (and optionally a masked last-four) fall outside PCI DSS scope, since the real PAN never touches them -- this directly reduces compliance scope while still allowing partial-value display.

---

**Q35. Correct: B**

Customer-managed keys let the data owner retain control over the key lifecycle and access policy, meaning the customer can restrict or revoke the cloud provider's ability to use the key to decrypt data -- this is the standard control for ensuring provider personnel cannot access plaintext data, sometimes called 'hold your own key' or BYOK.

---

**Q36. Correct: C**

The 'Share' phase of the Data Security Lifecycle is where data moves to other parties -- users, customers, partners -- and where controls governing who can receive the data (such as DRM, access control lists, and encryption for transit) are applied to prevent unauthorized disclosure.

---

**Q37. Correct: A**

CCSK emphasizes centralized secrets management (e.g., vault-based services) with dynamic, short-lived, auto-rotated credentials to minimize exposure window and eliminate hardcoded/static secrets scattered across systems.

---

**Q38. Correct: A**

SAST examines source code, bytecode, or binaries without running the application, enabling detection of vulnerabilities (e.g., insecure coding patterns) early in development — a core 'shift left' practice covered in CCSK.

---

**Q39. Correct: A**

Immutable infrastructure principles dictate that running instances are never modified in place; instead, a new, patched image is built from source and used to replace existing instances, preserving consistency, auditability, and rollback capability.

---

**Q40. Correct: B**

'Shift left' means moving security activities (SAST, threat modeling, secure code review, dependency scanning) earlier in the SDLC — closer to design and coding phases — rather than only testing security at the end near release.

---

**Q41. Correct: C**

Snapshotting the disk and capturing memory preserves volatile and non-volatile evidence for forensic analysis, while isolating the instance via network controls contains the threat without destroying evidence — aligning with CCSK v5 guidance to use cloud-native snapshot capabilities before termination.

---

**Q42. Correct: B**

CCSK guidance emphasizes continuously exporting cloud control-plane/API audit logs into a customer-owned, centralized log repository or SIEM so correlated, timestamped evidence across multiple providers is available and not solely dependent on each provider's retention policy.

---

**Q43. Correct: C**

Object lock/WORM configurations on cloud storage enforce immutability for a defined retention period, preventing deletion or modification of logs — a control CCSK v5 highlights for preserving evidentiary integrity during incident response and forensics.

---

**Q44. Correct: B**

RTO is the target duration within which a business process must be restored after a disruption, while RPO is the maximum tolerable period in which data might be lost, measured back to the last good backup or replication point — a core distinction tested in CCSK resilience content.

---

**Q45. Correct: A**

Zero Trust's core tenet is 'never trust, always verify' — access decisions are based on continuously verified identity, device posture, and context, combined with least privilege, rather than on network location.

---

**Q46. Correct: D**

SASE is defined by CSA as the convergence of network security functions (SWG, CASB, FWaaS, ZTNA) with SD-WAN capabilities, delivered as a single cloud-native service — exactly matching the stated requirement.

---

**Q47. Correct: D**

This scenario is a textbook example of Shadow AI — unsanctioned, unapproved use of third-party AI tools — leading to sensitive data (source code, configs) being exposed to an external provider via prompts, a key AI-related risk covered in CCSK Domain 12.

---

