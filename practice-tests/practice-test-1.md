# Practice Test 1: CCSK v5 Exam-Focused Preparation: Cloud Security Mastery

- **Questions:** 47
- **Time limit:** 90 minutes
- **Passing score:** 70%%

> Answers are in `answer-key-1.md`. Track results in `score-tracker.md`.

---

**Q1.** A retail company migrates its customer relationship management (CRM) system to a SaaS provider. Per the CCSK shared responsibility model, which responsibility ALWAYS remains with the customer, regardless of the service model used?

A) Maintaining the physical hardware and network infrastructure
B) Patching the guest operating system
C) Securing the hypervisor and virtualization layer
D) Managing user identities, access controls, and data classification

---

**Q2.** A development team needs to deploy custom-built applications with full control over the operating system configuration and runtime environment, but does not want to manage physical servers or the virtualization layer. Which cloud service model BEST meets this requirement?

A) IaaS
B) SaaS
C) Community cloud
D) PaaS

---

**Q3.** Several regional hospitals with identical regulatory compliance needs want a cloud environment provisioned exclusively for their consortium, with infrastructure and costs shared only among consortium members rather than the general public. Which deployment model does this describe?

A) Public cloud
B) Hybrid cloud
C) Community cloud
D) Private cloud

---

**Q4.** Which of the five essential characteristics of cloud computing allows a customer to provision computing resources automatically as needed, without requiring human interaction with the cloud provider?

A) Rapid elasticity
B) Measured service
C) Resource pooling
D) On-demand self-service

---

**Q5.** A healthcare organization is negotiating a contract with a cloud provider for storing PHI. To minimize risk from potential vendor lock-in and ensure business continuity if the relationship ends, which contractual provision is MOST important to include?

A) A right-to-audit clause allowing quarterly security assessments
B) A defined data portability and exit clause specifying data return/deletion formats and timelines
C) A service credit clause for SLA breaches
D) An indemnification clause covering third-party claims

---

**Q6.** An organization wants an independent, third-party-audited attestation of a CSP's security controls mapped to the Cloud Controls Matrix, rather than relying on the provider's self-reported responses. Which CSA STAR program level satisfies this requirement?

A) STAR Level 1 – Self-Assessment
B) STAR Level 3 – Continuous Auditing
C) STAR Level 2 – Third-Party Certification/Attestation
D) STAR Level 1 – CAIQ submission

---

**Q7.** When defining SLA metrics for a cloud governance program, which metric BEST measures a provider's ability to restore service after an outage, and is critical for GRC teams evaluating resiliency requirements?

A) Mean Time Between Failures (MTBF)
B) Uptime percentage (e.g., 99.9%)
C) Recovery Time Objective (RTO)
D) Recovery Point Objective (RPO)

---

**Q8.** In the CSA governance hierarchy, which document type provides specific, mandatory technical requirements derived from a higher-level policy statement, such as 'all data at rest must be encrypted using AES-256'?

A) Guideline
B) Policy
C) Procedure
D) Standard

---

**Q9.** A financial services firm is evaluating a large public cloud provider but cannot secure a contractual right to perform on-site audits due to the provider's multi-tenant scale. The firm still needs verifiable assurance that the provider's controls meet CCM requirements. Which approach BEST satisfies this need?

A) Require the provider to sign a contractual clause guaranteeing annual on-site audits by the customer's own auditors
B) Obtain the provider's completed CAIQ and cross-reference it with an independent SOC 2 Type II report covering the relevant period
C) Accept the provider's public marketing and trust-center webpage as sufficient evidence of control effectiveness
D) Require the provider to obtain ISO 9001 quality management certification as proof of security control effectiveness

---

**Q10.** A procurement team wants ongoing, near real-time visibility into a cloud provider's security posture rather than a point-in-time assessment that could become outdated. Which CSA STAR Registry level is specifically designed to provide this continuous assurance?

A) STAR Level 3 (Continuous Monitoring)
B) STAR Level 1 (Self-Assessment)
C) STAR Level 2 (Third-Party Certification/Attestation)
D) CAIQ Lite submission

---

**Q11.** An assessor needs to map an organization's existing cloud security controls against multiple external frameworks — including NIST SP 800-53, ISO/IEC 27001, and PCI DSS — using a single reference document maintained by the Cloud Security Alliance. Which tool should the assessor use?

A) The Consensus Assessments Initiative Questionnaire (CAIQ)
B) The Shared Responsibility Model diagram
C) The Cloud Controls Matrix (CCM)
D) The CSA Top Threats to Cloud Computing report

---

**Q12.** A company subscribes to a SaaS application and reviews the provider's SOC 2 Type II report, which lists several Complementary User Entity Controls (CUECs). Which of the following responsibilities would typically be identified as a CUEC that the customer must implement?

A) Patching the hypervisor underlying the SaaS provider's infrastructure
B) Securing physical access to the provider's data center
C) Configuring network firewall rules for the provider's backend infrastructure
D) Managing user access and authorization within the SaaS application

---

**Q13.** A company is expanding its cloud footprint and wants to limit the blast radius of a security incident in one business unit from affecting the resources of other business units. Which organizational strategy BEST achieves this goal?

A) Use a single account or subscription with IAM roles to logically separate business units
B) Create separate accounts or subscriptions for each business unit under a centralized management structure
C) Grant all business units administrator access to one shared account for consistency
D) Rely solely on network segmentation (VPCs/VNets) within one account

---

**Q14.** An organization wants to guarantee that no cloud resources can ever be deployed outside of a set of approved regions, across every account in its organization. Which type of control BEST enforces this requirement?

A) A detective control that generates an alert after a non-compliant resource is deployed
B) A preventive, policy-based guardrail applied at the organizational level that blocks deployment outside approved regions
C) A manual quarterly audit of resource locations across all accounts
D) A corrective control that automatically terminates non-compliant workloads after they are discovered

---

**Q15.** According to CSA guidance, which practice is recommended for securing the root or master account of a cloud organization's top-level management account?

A) Use the root account for daily administrative tasks to simplify operations
B) Share the root account credentials among several senior administrators for redundancy
C) Enable MFA on the root account, secure its credentials, and avoid using it for routine operations
D) Disable the root account entirely once the cloud organization has been created

---

**Q16.** What is a primary security challenge organizations face when applying one unified organizational security policy across multiple cloud providers?

A) Cloud providers charge additional fees specifically for enforcing security policies across linked accounts
B) Multi-cloud environments are technically incapable of supporting centralized logging
C) Inconsistent native security controls, terminology, and policy mechanisms across providers complicate unified enforcement
D) Cloud providers contractually prohibit the use of third-party governance and policy tools

---

**Q17.** An organization federates its workforce identities to a cloud provider using SAML-based SSO through its on-premises Identity Provider (IdP). Which statement BEST describes the security priority this architecture creates for the organization?

A) The IdP becomes a high-value single point of failure and must be hardened as critical infrastructure
B) The cloud provider becomes solely responsible for protecting user credentials
C) Federation eliminates the need for MFA since the IdP already authenticates users once
D) SAML assertions do not need to be time-limited since they are digitally signed

---

**Q18.** A security team needs continuous visibility into which cloud identities — human and non-human (service accounts, roles) — hold excessive or unused permissions across AWS, Azure, and GCP. Which category of solution BEST addresses this requirement?

A) Cloud Access Security Broker (CASB)
B) Cloud Infrastructure Entitlement Management (CIEM)
C) Cloud Security Posture Management (CSPM) focused only on configuration
D) Traditional on-premises Identity Governance and Administration (IGA) tool

---

**Q19.** An organization wants to configure the strongest available protection against phishing attacks for privileged administrator accounts that access the cloud management plane. Which authentication method should be configured?

A) SMS-based one-time passcode as second factor
B) Knowledge-based security questions
C) Time-based one-time password (TOTP) app synced via QR code shared with helpdesk
D) FIDO2/WebAuthn hardware security keys

---

**Q20.** Which statement BEST describes the difference between SAML and OAuth 2.0/OpenID Connect (OIDC) in cloud federation architectures?

A) SAML is used for authorization delegation while OAuth is used for authentication assertions
B) SAML and OAuth are interchangeable and provide identical security guarantees
C) OAuth 2.0 requires an on-premises Active Directory server while SAML does not
D) SAML is primarily designed for authentication/SSO assertions using XML, while OAuth 2.0 with OIDC provides authorization delegation and modern token-based authentication for APIs and mobile apps

---

**Q21.** A financial services company operates workloads across three different cloud providers and needs a unified view of security events for real-time correlation and alerting. Which approach BEST satisfies this requirement?

A) Ingest logs from all three cloud providers' native logging services into a centralized SIEM with normalized event schemas
B) Rely exclusively on each cloud provider's built-in security dashboard without aggregation
C) Deploy a CASB solution configured only for SaaS application discovery
D) Export logs to local storage on each cloud provider and review them manually each quarter

---

**Q22.** Which type of cloud log captures the API calls made against a cloud provider's management plane, recording who performed an action, what action was taken, and when it occurred?

A) Network flow logs
B) Application performance logs
C) Vulnerability scan reports
D) Cloud audit/activity logs

---

**Q23.** An organization wants to prevent an attacker who compromises an administrator account from being able to delete or alter security logs to cover their tracks. Which control should be configured?

A) Store all logs only on the monitored instance's local disk
B) Set the log retention period to the shortest value allowed
C) Immutable, write-once-read-many (WORM) log storage with restricted deletion permissions
D) Grant the monitoring service account full administrative rights over the log storage

---

**Q24.** Under the cloud shared responsibility model for an IaaS deployment, who is responsible for monitoring the security of the underlying physical data center infrastructure?

A) The cloud service provider
B) The customer's security operations team
C) A third-party compliance auditor
D) The end users of the customer's application

---

**Q25.** A company is migrating a multi-tier application to the cloud. During a tabletop exercise, the security team wants to ensure that if a single compute instance is compromised, an attacker cannot easily pivot to other instances within the same subnet. Which control BEST addresses this requirement?

A) Place all instances in a single flat network segment with one shared security group for ease of management
B) Deploy a traditional perimeter firewall only at the network edge to inspect north-south traffic
C) Enable a cloud provider DDoS protection service on the load balancer
D) Implement micro-segmentation with per-workload security policies enforcing least-privilege east-west traffic rules

---

**Q26.** Which characteristic of Software-Defined Networking (SDN) provides the greatest security benefit to cloud tenants, as described in CCSK guidance?

A) Physical separation of control plane and data plane hardware at each network device
B) A programmable control plane decoupled from the data plane, enabling centralized, API-driven policy enforcement across the virtual network
C) Elimination of the need for any network-level security controls since the provider secures all traffic
D) Exclusive reliance on static VLAN tagging to isolate tenant traffic

---

**Q27.** A security architect is configuring cloud provider security groups (stateful virtual firewalls) for a three-tier web application consisting of web, application, and database tiers. Which configuration approach BEST aligns with CCSK least-privilege guidance for cloud network security?

A) Allow all inbound and outbound traffic by default, and add explicit deny rules only for known malicious IP ranges
B) Deny all traffic by default and create tier-specific rules, restricting the database tier to accept traffic only from the application tier on the required port
C) Apply one broad security group with identical rules to the web, application, and database tiers to simplify operations
D) Disable cloud-native security groups entirely and rely only on operating system host-based firewalls

---

**Q28.** According to CCSK guidance, what fundamentally distinguishes a Software Defined Perimeter (SDP) from a traditional site-to-site or remote-access VPN in a cloud environment?

A) SDP requires a dedicated physical hardware appliance to be installed at every client endpoint
B) SDP operates exclusively at Layer 2 of the OSI model, while VPNs operate exclusively at Layer 3
C) SDP authenticates and authorizes the identity and posture of a user or device before granting any network-level visibility to protected resources, effectively cloaking infrastructure from unauthorized entities
D) SDP removes the need to encrypt traffic between the client and the protected resources

---

**Q29.** A company runs containerized microservices on Kubernetes. They want to prevent a compromised container from running as root or gaining privileged access that could allow escape to the underlying host. Which control BEST addresses this requirement?

A) Enforce Pod Security Standards using the 'restricted' profile to block privileged containers, host namespace sharing, and root execution
B) Enable Kubernetes Network Policies to restrict pod-to-pod traffic
C) Scan container images for known CVEs before deployment
D) Deploy a service mesh to provide mutual TLS between pods

---

**Q30.** A serverless function that processes user-uploaded files has been granted permissions to an entire storage account because the developer was unsure which specific permissions were needed. According to CCSK guidance on serverless workload security, what is the PRIMARY risk here and the BEST remediation?

A) Violation of least privilege is the primary risk; remediate by scoping the function's IAM role to only the specific bucket/resource and actions it actually requires
B) Cold start latency is the primary risk; remediate by pre-warming function instances
C) Excessive execution timeout is the primary risk; remediate by reducing the maximum runtime
D) Lack of network isolation is the primary risk; remediate by placing the function inside a VPC

---

**Q31.** An organization wants to ensure that only container images pulled from a trusted registry, signed and verified, can ever be deployed to its production Kubernetes clusters. Which mechanism BEST enforces this requirement?

A) An admission controller (policy-as-code webhook) that verifies image signatures and registry provenance before allowing pod creation
B) A Kubernetes Network Policy restricting egress to the registry endpoint
C) A Horizontal Pod Autoscaler configured on the deployment
D) Encryption of etcd data at rest

---

**Q32.** Which Kubernetes API server configuration hardens the cluster by preventing unauthenticated, anonymous requests from being processed?

A) Enabling a PodDisruptionBudget on critical workloads
B) Setting CPU and memory resource requests/limits on all pods
C) Enabling Horizontal Pod Autoscaling on deployments
D) Setting --anonymous-auth=false on the kube-apiserver

---

**Q33.** A healthcare provider stores encrypted patient records (PHI) in a cloud provider's object storage. The contract with the cloud provider is ending, and the company wants absolute assurance that no readable copies of the data remain accessible to the provider after migration, including in backups and snapshots the provider controls. Which approach BEST achieves this?

A) Ask the provider to run a secure delete (multi-pass overwrite) on all storage volumes that held the data
B) Rely on the provider's data retention policy to automatically purge the data after the contractual retention period expires
C) Destroy the encryption keys used to protect the data, rendering all copies of the ciphertext permanently unreadable (crypto-shredding)
D) Move the data to a different storage tier within the same provider to force deletion of the original copies

---

**Q34.** An e-commerce company processes credit card payments and wants customer service representatives to be able to view the last four digits of a card number for verification purposes, while minimizing the number of systems that fall under PCI DSS scope. Which data protection technique BEST meets this requirement?

A) Format-preserving encryption applied to the full card number in every system that touches it
B) Tokenization, replacing the full card number with a token and storing the real number only in a separate, tightly controlled vault
C) One-way hashing of the card number so representatives can compare hash values
D) Full-disk encryption on the database servers that store the card numbers

---

**Q35.** A financial services firm is deploying a SaaS application and wants to ensure the cloud provider's own personnel cannot access the customer's decrypted data, even though the provider manages the underlying infrastructure. Which key management configuration should the firm require?

A) Provider-managed keys stored in the provider's default key management service with provider-controlled access policies
B) Customer-managed keys (CMK) held in a key management service where the customer, not the provider, controls key access policies and can revoke provider access
C) Client-side symmetric keys hard-coded into the application source code for simplicity
D) Shared keys distributed via email to all application administrators for convenience

---

**Q36.** According to the CSA Data Security Lifecycle, which phase specifically involves determining who else, beyond the original creator or owner, is permitted to access or receive the data, and applying controls such as DRM or access restrictions accordingly?

A) Store
B) Use
C) Share
D) Archive

---

**Q37.** A DevOps team's CI/CD pipeline needs database credentials and third-party API keys available to build agents during deployment. Per CCSK guidance on secrets management, which approach BEST meets this requirement?

A) Integrate a centralized secrets management service that issues short-lived, dynamically generated credentials injected at runtime
B) Store the credentials in environment variables configured directly in the CI/CD tool's UI, visible to anyone with pipeline access
C) Hardcode the credentials into build scripts, encrypted with a key stored in the same repository
D) Distribute the credentials to team members via a shared internal spreadsheet with restricted read access

---

**Q38.** Which application security testing methodology analyzes source code or binaries WITHOUT executing the application, and is typically integrated early in the SDLC to catch vulnerabilities before build or deployment?

A) Static Application Security Testing (SAST)
B) Dynamic Application Security Testing (DAST)
C) Fuzz testing
D) Manual penetration testing

---

**Q39.** A security scan discovers a critical vulnerability in a container image currently running in production as part of an immutable infrastructure deployment model. What is the BEST remediation approach per CCSK guidance?

A) Rebuild the container image with the fix applied, then redeploy to replace the running instances
B) SSH into the running container and manually apply a patch to the affected package
C) Execute a hotfix script through the orchestrator's exec command against the live container
D) Modify the running container's filesystem directly and commit the changes as a new image layer

---

**Q40.** In the context of DevSecOps, what does the term 'shift left' refer to?

A) Migrating application workloads to a cloud provider's westernmost or left-positioned data center region
B) Integrating security testing, controls, and reviews earlier in the software development lifecycle
C) Transitioning application deployment timelines to occur earlier than originally scheduled
D) Reorganizing the development team structure to report to a security-first leadership hierarchy

---

**Q41.** During an incident investigation of a suspected compromised virtual machine in an IaaS environment, the responder needs to preserve evidence for forensic analysis while limiting further attacker activity. Which action BEST meets these requirements?

A) Immediately terminate the instance to prevent the attacker from causing additional damage
B) Request that the cloud service provider perform the forensic investigation on the customer's behalf
C) Snapshot the volume and capture a memory image, then isolate the instance using security group/network ACL rules
D) Leave the instance running unmodified until law enforcement provides written authorization to proceed

---

**Q42.** A security team responding to an incident spanning workloads across two different cloud providers needs to reconstruct a timeline of API calls and administrative actions. Which capability BEST supports this requirement?

A) Relying on each provider's support staff to verbally summarize account activity during a support call
B) Centralized aggregation of provider-native control-plane audit logs into a customer-controlled SIEM with continuous export
C) Packet captures taken only at the customer's on-premises network perimeter
D) Manual screenshots of the cloud console taken by administrators during business hours

---

**Q43.** An organization wants to ensure that cloud audit logs required for a potential incident investigation cannot be altered or deleted before the investigation concludes. Which configuration BEST achieves this?

A) Enable aggressive log rotation to minimize storage costs
B) Disable logging on the affected resource as soon as the incident is detected
C) Configure the log storage bucket with object lock/WORM (write-once-read-many) and a retention period that exceeds the expected investigation timeframe
D) Store logs only in the memory of the application server generating them

---

**Q44.** In cloud business continuity and disaster recovery planning, what is the primary distinction between Recovery Time Objective (RTO) and Recovery Point Objective (RPO)?

A) RTO and RPO both measure the same thing but are expressed in different units of currency
B) RTO defines the maximum acceptable downtime before a system must be restored; RPO defines the maximum acceptable amount of data loss measured in time
C) RTO applies only to on-premises systems, while RPO applies only to cloud-hosted systems
D) RPO defines how long a backup takes to complete, while RTO defines how often backups are scheduled

---

**Q45.** A financial services company is redesigning its cloud security architecture and wants to eliminate implicit trust based on network location. Employees, contractors, and partners will access cloud applications from a variety of untrusted networks. Which approach BEST aligns with Zero Trust principles as described in CSA guidance?

A) Enforce continuous verification of identity, device posture, and context for every access request, regardless of network location, using least privilege
B) Deploy a stronger perimeter firewall and require all traffic to pass through a corporate VPN before reaching cloud resources
C) Grant broad access to cloud resources based on a single successful login to the corporate directory using strong passwords
D) Segment the network into a trusted internal zone and an untrusted external zone, allowing unrestricted access within the trusted zone

---

**Q46.** An organization has a growing remote workforce accessing SaaS applications and private data center resources. The security team wants to consolidate secure web gateway, CASB, firewall-as-a-service, and zero trust network access into a single cloud-delivered service integrated with SD-WAN. Which architecture model BEST fits this requirement?

A) Cloud Access Security Broker (CASB) deployed as a standalone service
B) Traditional hub-and-spoke VPN architecture
C) Software-Defined Perimeter (SDP) deployed alone
D) Secure Access Service Edge (SASE)

---

**Q47.** A software development team has begun using public generative AI chatbots to troubleshoot code and draft documentation without the security team's knowledge or approval. Employees are pasting internal source code and configuration details directly into prompts. Which risk does this scenario BEST illustrate, per CSA guidance on AI security?

A) Model poisoning through adversarial training data injected by an external attacker
B) Insecure API rate limiting on the AI provider's inference endpoints
C) Hallucination causing the AI to generate factually inaccurate output for developers
D) Shadow AI resulting in sensitive data leakage through unsanctioned use of public AI services

---

