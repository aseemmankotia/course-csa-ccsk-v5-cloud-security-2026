# Answer Key — Practice Test 2

**Q1. Correct: A**

The shared responsibility model is control-specific, not model-specific by blanket rule. Even in PaaS, some operational controls (like scheduling maintenance/patch windows) remain with the customer. The provider fulfilled its obligation by making the patch available and notifying the customer; the customer's failure to act on a control they owned caused the breach.

---

**Q2. Correct: B**

IaaS gives the customer control from the OS layer upward -- including kernel modules and OS patch levels -- while the provider retains responsibility for hardware, virtualization, and facilities. This exactly matches the stated requirement.

---

**Q3. Correct: C**

The metastructure is the management plane and API layer that ties the infrastructure to everything running on top of it (orchestration, provisioning, monitoring). CCSK material specifically highlights it as a cloud-unique concept, since traditional data centers lack this programmable orchestration/API layer connecting physical resources to applications.

---

**Q4. Correct: C**

A community cloud is provisioned for exclusive use by a specific group of organizations with shared concerns (e.g., compliance, mission, security requirements), with governance and infrastructure shared among the community members -- exactly matching the joint governance, restricted membership, and shared policy framework described.

---

**Q5. Correct: C**

In multi-tenant public cloud, individual customer audits are generally impractical and pose isolation/security risks to other tenants. CSA guidance recommends relying on third-party attestations (STAR Level 2) and continuous monitoring/self-assessment (STAR Level 3) as compensating controls, formalized contractually, rather than insisting on traditional on-site audit rights.

---

**Q6. Correct: C**

CSA's governance model is top-down: business objectives and risk appetite inform policy, which informs standards, which informs procedures. Procedures created before policy risk being technically sound but disconnected from actual business risk tolerance, legal requirements, or data sensitivity — meaning controls may be over-engineered in some areas and insufficient in others.

---

**Q7. Correct: C**

The Cloud Controls Matrix (CCM) is CSA's cloud-specific control framework, organized into control domains and cross-mapped to major standards including ISO 27001, NIST, and PCI DSS, making it the correct tool for streamlining multi-framework compliance in a cloud context.

---

**Q8. Correct: C**

CSA guidance emphasizes that, unlike bespoke traditional outsourcing agreements, most public cloud providers use standardized, take-it-or-leave-it contracts with limited room for negotiation — particularly for smaller customers — which shifts significant governance burden onto the customer's own risk assessment and compensating controls.

---

**Q9. Correct: B**

Under the shared responsibility model, controls that are customer-configurable (IAM federation setup, retention policy settings) remain the customer's accountability even in SaaS. CAIQ responses clarify what the CSP has implemented, but the customer must still assess and evidence its own configuration choices — compliance inheritance only covers the CSP-owned portion of the stack.

---

**Q10. Correct: B**

STAR Continuous (Level 3) is the only STAR tier designed to deliver ongoing, near-real-time validation of security control status using the CCM Continuous Monitoring specification rather than a periodic snapshot.

---

**Q11. Correct: D**

The CCM organizes controls into domains, and each individual control is cross-referenced against multiple frameworks (e.g., ISO 27001, NIST, PCI DSS), which is precisely what allows CAIQ responses to support compliance mapping across several regulatory obligations simultaneously.

---

**Q12. Correct: A**

ENISA's cloud risk assessment framework specifically highlights loss of governance as a top-tier risk unique to cloud environments, since customers cede direct control over infrastructure and share it with other tenants, requiring risk assessment approaches that traditional on-premises models don't need.

---

**Q13. Correct: A**

The account-per-workload/business-unit model is the core multi-account strategy CCSK recommends: it uses hard isolation boundaries (separate accounts) to contain blast radius from a compromise, while a parent organization/management account still enables centralized logging, billing, and guardrail policy inheritance across all child accounts.

---

**Q14. Correct: A**

CCSK guidance treats the root/organization management account as the highest-value target in the environment — compromising it can compromise every subordinate account. Best practice is hardware MFA, near-zero routine use (break-glass only), and full activity logging/alerting so any use is immediately visible.

---

**Q15. Correct: A**

CSA guidance recognizes that native IAM/policy models differ significantly across providers, so consistent governance requires abstracting policy intent into a common control framework (e.g., mapped to CCM) and then translating that intent into each provider's native controls, typically operationalized through centralized CSPM/CNAPP tooling for unified visibility and enforcement.

---

**Q16. Correct: A**

A preventive control stops a non-compliant action (public bucket creation) from ever succeeding in the first place — the request is blocked at creation time, before any resource with the violating configuration exists.

---

**Q17. Correct: D**

Because the browser acts as the transport intermediary for the assertion (POST binding), TLS only protects the wire; a compromised endpoint, malicious browser extension, or cached page could expose the plaintext assertion contents, including any sensitive attributes bundled in it. This is why CCSK guidance recommends encrypting assertions with sensitive attributes in addition to signing and TLS.

---

**Q18. Correct: D**

CIEM tools are purpose-built to normalize entitlement data across heterogeneous cloud IAM models, surface excessive permissions, and enable attribute-based, continuously-enforced least-privilege policies at scale — exactly the gap native per-provider consoles and manual review cannot close.

---

**Q19. Correct: B**

JIT elevation via a PAM solution enforces least privilege by granting access only when needed, for a bounded time window, with an approval workflow and full session logging — directly reducing the attack surface of standing privileged accounts, which is the core CCSK recommendation for privileged access management.

---

**Q20. Correct: D**

In SAML federation, the Identity Provider (here, the enterprise directory) authenticates the user and issues signed assertions; the Service Provider/Relying Party (the SaaS application) trusts and consumes those assertions to authorize access without directly authenticating the user itself.

---

**Q21. Correct: C**

Many cloud services (especially PaaS/serverless and managed services) do not log every action by default. CCSK guidance stresses that logging coverage must be explicitly designed, enabled, and validated as part of deployment/build processes rather than assumed from defaults.

---

**Q22. Correct: A**

An attacker with account-level or privileged API access can disable, alter, or delete any logs stored within that same account, including OS and application logs. Control plane/API audit logs specifically record privilege escalation, IAM changes, and tampering actions, making them the highest-priority log to protect via immediate off-account centralization per CCSK guidance.

---

**Q23. Correct: C**

This combination directly satisfies the CCSK integrity goals: immutability via WORM/object-lock, separation of duties by isolating deletion rights from the workload account, and resilience via replication to a separate trust boundary, so a compromised workload account cannot tamper with the evidence.

---

**Q24. Correct: D**

CCSK highlights the heterogeneity of log formats, field names, and timestamp conventions across CSPs and SaaS providers as the core obstacle to cross-platform correlation, requiring a normalization/parsing layer feeding a centralized SIEM before meaningful detection can occur.

---

**Q25. Correct: B**

CCSK emphasizes micro-segmentation as the core control for limiting lateral movement in flat cloud networks. Security groups/distributed firewalls enforce least-privilege, tier-to-tier rules independent of physical topology, directly addressing the pen-test finding.

---

**Q26. Correct: D**

CCSK material identifies the control/data plane separation in SDN as the key architectural shift that enables software-based, API-driven network security policy — including rapid segmentation, dynamic firewall updates, and consistent policy at scale — impossible with static physical networking.

---

**Q27. Correct: B**

CCSK consistently reinforces default-deny/least-privilege as the baseline posture for cloud network controls. Only explicitly required traffic should be permitted; everything else is denied by default, which also directly supports micro-segmentation objectives.

---

**Q28. Correct: D**

CCSK highlights that in IaaS the customer has no access to the physical network fabric or hypervisor, so hardware-based taps/SPAN ports cannot be deployed. Visibility must instead come from provider-native tools such as VPC/VNet flow logs, mirroring services, and virtual appliances designed for the SDN layer.

---

**Q29. Correct: A**

Default Kubernetes networking is flat, meaning any pod can reach any other pod across namespaces unless restricted. NetworkPolicies enforce microsegmentation at the pod/namespace level, which is the direct preventive control against lateral movement between tenants sharing a cluster.

---

**Q30. Correct: A**

Serverless workload security relies heavily on scoping permissions per-function to the principle of least privilege, since functions are ephemeral, event-triggered, and highly interconnected — a single over-privileged role turns any one compromised function into a full-account compromise.

---

**Q31. Correct: B**

Admission controllers intercept API requests before objects are persisted/scheduled, allowing policy-as-code enforcement (image scanning results, signature verification) at the cluster ingress point — the only control in the list that can universally block noncompliant images regardless of submitter.

---

**Q32. Correct: D**

Immutable infrastructure's core security value is eliminating configuration drift: every deployment originates from a version-controlled, tested artifact (golden image/container), so the running state always matches a known, auditable baseline rather than accumulating undocumented in-place changes.

---

**Q33. Correct: B**

HYOK keeps the key material entirely outside the CSP's environment in an external key manager. The CSP must request the key for each cryptographic operation, so the customer can instantly cut off provider access by disabling that external connection — the strongest separation-of-duties model discussed in CCSK guidance.

---

**Q34. Correct: B**

Tokenizing just the PAN field removes the actual sensitive card data from the database entirely, isolating it in a separate token vault. This is the classic PCI DSS scope-reduction technique cited in CSA guidance because the database itself no longer stores in-scope cardholder data, while non-sensitive fields remain fully queryable.

---

**Q35. Correct: C**

Cryptographic erasure (destroying the key rather than the data itself) is the standard practical destruction method for cloud environments, since the customer cannot control shared physical media. Once the key is irrecoverably deleted, the ciphertext is permanently unreadable, satisfying destruction requirements without needing physical access.

---

**Q36. Correct: D**

Masking is typically used to obscure or substitute sensitive values (commonly in non-production/test/analytics environments) and is often irreversible by design. Encryption, in contrast, is explicitly built to be reversible by an authorized key holder. This reversibility distinction is the key conceptual difference tested on the exam.

---

**Q37. Correct: C**

Cryptographic image signing (e.g., via Sigstore/cosign or an equivalent notary service) combined with admission control verification provides a tamper-evident, automatable chain of custody. The admission controller cryptographically proves the image originated from the trusted pipeline and passed required attestations (scans, provenance) before it can run, which is the CCSK-recommended approach to supply chain integrity in CI/CD.

---

**Q38. Correct: C**

Dynamic secrets generation (as provided by tools like HashiCorp Vault's database secrets engine) issues unique, short-TTL credentials per client request and revokes them automatically on expiry. This eliminates standing, shared credentials entirely, drastically reduces the blast radius of a leak, and removes the human/process dependency of manual rotation — the recommended pattern CCSK v5 highlights for cloud secrets management maturity.

---

**Q39. Correct: D**

SCA scans dependency manifests (e.g., package.json, requirements.txt, resolved lockfiles) and container layers against known-vulnerability and license databases, identifying vulnerable open-source components and transitive dependencies. This is precisely the control gap described — detecting risk introduced by third-party libraries — and CCSK v5 identifies SCA as the dedicated technique for supply-chain dependency risk in the pipeline.

---

**Q40. Correct: B**

Immutable infrastructure eliminates drift by design: instead of mutating running systems, a new hardened, patched image is built and validated, then deployed to replace old instances wholesale. This guarantees every running instance matches a known-good, version-controlled state and removes the class of problem entirely rather than detecting or reacting to it — a core cloud application architecture principle emphasized in CCSK v5.

---

**Q41. Correct: A**

Cloud-native snapshotting via CSP APIs is the standard forensic technique in cloud environments — it captures the running state (including volatile memory on many hypervisors) without powering down the system, and does so without physically isolating shared hardware that hosts other tenants.

---

**Q42. Correct: B**

Only a multi-region architecture with automated failover and replication protects against the loss of an entire region, while still enabling low RTO/RPO through automation rather than manual recovery from backups.

---

**Q43. Correct: C**

Retention periods should be driven by the organization's own IR playbooks, compliance obligations, and realistic dwell-time assumptions for undetected threats — CSP defaults are generic and not tailored to any specific organization's forensic or legal needs.

---

**Q44. Correct: A**

CSA guidance treats redundancy as a specific engineering technique (duplicating components/paths) that is one of several mechanisms contributing to the broader, system-wide property of resilience, which also includes detection, adaptation, and recovery capabilities.

---

**Q45. Correct: B**

In the NIST SP 800-207 Zero Trust model, the Policy Decision Point (comprising the Policy Engine and Policy Administrator) evaluates the trust algorithm against contextual signals to decide access. The Policy Enforcement Point is a purely mechanical component that enables, monitors, and terminates the connection based on the decision it receives — it does not make the decision itself.

---

**Q46. Correct: A**

SASE converges networking (SD-WAN) and security service edge functions — SWG, CASB, ZTNA, FWaaS — into a single, cloud-delivered platform with unified, identity-aware policy enforcement. This directly eliminates dependence on on-premises appliances and applies consistent policy regardless of user or branch location.

---

**Q47. Correct: D**

In RAG architectures, the LLM itself has no concept of user authorization — the vector database retrieval step is the actual security boundary. Applying authorization filtering at retrieval time (returning only chunks the requesting identity is permitted to access) directly prevents unauthorized data from ever entering the prompt context, which is the root cause of this leakage risk.

---

