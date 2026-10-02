# Practice Test 2: CCSK v5 Exam-Focused Preparation: Cloud Security Mastery

- **Questions:** 47
- **Time limit:** 90 minutes
- **Passing score:** 70%%

> Answers are in `answer-key-2.md`. Track results in `score-tracker.md`.

---

**Q1.** A company runs its primary database on a PaaS-based managed database service. The provider makes security patches for the database engine available on a regular schedule and sends automated notifications, but requires the customer to explicitly schedule a maintenance window to apply each update. The customer ignores these notifications for 18 months. An attacker then exploits the long-unpatched, publicly known vulnerability and exfiltrates data. Under the CCSK shared responsibility model, who bears responsibility for this security failure?

A) The customer, because scheduling and applying available patches was a control retained by the customer despite the provider managing the underlying engine
B) The cloud provider, because patching the underlying platform is always a provider responsibility under PaaS
C) Responsibility is split exactly 50/50 automatically under every PaaS contract regardless of the specific control
D) Neither party is responsible; liability rests solely with the third-party database engine vendor

---

**Q2.** An organization is migrating a legacy application that requires installing custom kernel modules, modifying low-level OS security settings, and controlling the exact patch level of the operating system. The organization does not want to manage physical hardware, the hypervisor, or the virtualization layer. Which cloud service model best fits this requirement?

A) PaaS, because it provides a managed operating environment with configurable security settings
B) IaaS, because it provides OS-level and above control while the provider manages the physical infrastructure and virtualization layer
C) SaaS, because it eliminates most operational responsibility for the organization
D) Community cloud, because it allows shared control over infrastructure among trusted organizations

---

**Q3.** In the CSA logical model of cloud computing, which layer is described as the set of protocols and mechanisms used to provision, orchestrate, and monitor resources -- effectively the 'glue' binding the infrastructure layer to the application, information, and management layers -- and is considered to have no direct analog in traditional, non-cloud IT environments?

A) Infrastructure layer
B) Applistructure layer
C) Metastructure layer
D) Infostructure layer

---

**Q4.** A consortium of five independent hospitals wants a cloud environment where the underlying infrastructure is jointly funded and governed by all five organizations, accessible only to the consortium members, with a shared security policy framework the members collectively define -- but no single hospital owns or controls the environment, and it is not available to the general public. Which cloud deployment model does this describe?

A) Private cloud
B) Public cloud
C) Community cloud
D) Hybrid cloud

---

**Q5.** A retail company is finalizing a contract with a large public cloud provider. Legal wants a clause granting the company the right to conduct its own on-site security audit of the provider's infrastructure at any time. The provider refuses, citing multi-tenant isolation and the impracticality of individual customer audits, but offers to share its CSA STAR Level 2 third-party attestation report and commit to a continuous monitoring program under STAR Level 3. What is the BEST governance action for the company to take?

A) Refuse to sign until the provider agrees to unrestricted on-site audit rights, since right-to-audit clauses are a mandatory requirement for any cloud contract
B) Accept only the provider's standard SOC 2 report as sufficient assurance and remove all audit-related language from the contract
C) Accept the STAR Level 2 attestation and require the STAR Level 3 continuous monitoring commitment as a contractual compensating control in place of direct audit rights
D) Terminate the vendor relationship and select a smaller provider willing to grant full individual audit access

---

**Q6.** A cloud security team has spent months writing highly detailed technical hardening procedures for storage bucket configurations, but the organization has not yet formally defined its data classification policy or risk appetite statement. According to the CSA governance hierarchy (business objectives → risk appetite → policies → standards → procedures), what is the PRIMARY risk of this approach?

A) The procedures will require more frequent updates because they were written before the standards documentation
B) Automation tooling cannot be applied to procedures that were created before policy documents
C) The technical procedures may not align with the organization's actual risk tolerance or legal/regulatory obligations, since they were built without a governing policy foundation
D) The organization will be unable to pass a CSA STAR Level 1 self-assessment without a completed policy set

---

**Q7.** A CISO wants a single, vendor-neutral, cloud-specific control framework that maps directly to ISO 27001, NIST CSF, and PCI DSS so the security team can streamline compliance reporting across multiple regulatory obligations for its cloud services. Which CSA resource should be selected?

A) The Consensus Assessments Initiative Questionnaire (CAIQ)
B) The Shared Responsibility Model diagram
C) The Cloud Controls Matrix (CCM)
D) The STAR Registry public listing

---

**Q8.** According to CSA guidance, cloud service contracts most commonly differ from traditional IT outsourcing contracts in that:

A) Cloud contracts always include unlimited financial liability for the provider in the event of a data breach
B) Traditional outsourcing contracts never include service level agreements, while all cloud contracts are required to include them
C) Cloud providers typically offer standardized, largely non-negotiable contract terms, giving smaller customers limited leverage to customize liability, SLA, or data handling clauses
D) Cloud contracts eliminate the need for the customer to plan an exit or data portability strategy, since providers guarantee data return

---

**Q9.** A financial services company migrates a SaaS payment application. The CSP holds ISO 27001 and SOC 2 Type II reports and is CSA STAR Level 2 certified. The company's external auditor asks how the company will demonstrate compliance for identity federation configuration and customer-defined data retention policies within the SaaS app. Which approach BEST addresses this requirement?

A) Rely solely on the CSP's SOC 2 Type II report, since it covers all shared responsibility controls including customer-configured settings
B) Request the CSP's CAIQ responses to understand the CSP's implemented controls, and separately assess and document the customer's own configuration of federation and retention settings
C) Require the CSP to obtain FedRAMP authorization before continuing to use the service
D) Accept the STAR Level 2 certification alone, since it supersedes the need to review CAIQ responses or perform any customer-side assessment

---

**Q10.** An organization wants continuous, near-real-time assurance of a CSP's security control effectiveness rather than a point-in-time attestation. Which CSA STAR program component should the organization require the CSP to implement?

A) STAR Level 1, consisting of a CSP self-assessment submission of the CAIQ
B) STAR Continuous (Level 3), which uses the CCM Continuous Monitoring specification to publish ongoing control status
C) STAR Level 2, consisting of a third-party audit certifying the CSP against ISO/IEC 27001 with CCM mapping
D) Annual resubmission of the CAIQ self-assessment questionnaire to the STAR Registry

---

**Q11.** Which statement accurately describes how the Cloud Controls Matrix (CCM) v4 is structured to support CAIQ-based assessments?

A) Each CCM control maps to exactly one regulatory framework, which prevents its use for multi-framework compliance mapping
B) CAIQ questions are structured as open-ended narrative fields only, with no standardized yes/no response option
C) CCM v4 eliminated the control ownership mapping (CSP, customer, or shared) that existed in earlier versions
D) CCM controls are organized into domains, with each control specification cross-mapped to multiple industry-recognized standards and frameworks

---

**Q12.** According to ENISA's cloud risk assessment framework referenced in CSA guidance, which factor MOST distinguishes cloud risk assessment from traditional on-premises risk assessment?

A) It must account for loss of governance arising from shared infrastructure and multi-tenancy
B) It eliminates the need to consider vendor lock-in as a risk category
C) It focuses exclusively on evaluating physical data center security controls
D) It removes the need for a business impact analysis, since the CSP assumes all liability for outages

---

**Q13.** A large enterprise is designing its cloud account/tenant hierarchy across multiple business units, each running distinct workloads with different risk profiles. The security team wants to limit the blast radius of any single compromise while still maintaining centralized visibility and policy enforcement. Which approach BEST meets these requirements?

A) Separate accounts per business unit nested under a central management/organization account, with centralized log aggregation and policy inheritance
B) Each business unit independently manages its own separate cloud provider contract with no central oversight or shared logging
C) A single shared account used by all business units, with IAM roles assigned per business unit to separate permissions
D) A single super-admin account that delegates administrative rights to designated owners in each business unit

---

**Q14.** An organization's cloud environment uses a single root/organization management account to create and govern all subordinate accounts. Which practice is MOST critical to prevent this account from becoming a single point of catastrophic compromise?

A) Enforce hardware-based MFA on the root account, restrict its use to account creation and emergency break-glass scenarios only, and continuously monitor all activity performed under it
B) Share the root account credentials among several senior security team members to ensure availability during incidents
C) Use the root account for routine day-to-day administrative tasks so the team stays familiar with its permissions
D) Disable MFA on the root account so administrators are never locked out during an emergency

---

**Q15.** An organization operates a multi-cloud environment spanning three different cloud providers, each with its own native IAM model and policy engine. Per CSA guidance, which approach BEST achieves consistent security guardrails across all three providers?

A) Define provider-agnostic security policies mapped to a common control framework, then translate and enforce them via each provider's native guardrail mechanisms and/or a centralized CSPM/CNAPP tool
B) Rely solely on each provider's native policy engine without any independent normalization, since native tools are always functionally equivalent across providers
C) Enforce guardrails only during initial account/workload provisioning, since cloud configurations do not drift after deployment
D) Require identical IAM role and policy implementations across all three providers to guarantee uniform enforcement

---

**Q16.** An organization configures an automated rule that blocks the creation of any publicly accessible storage bucket at the moment a resource is requested, across its entire cloud environment. Which type of guardrail control does this represent?

A) Preventive control
B) Detective control
C) Corrective control
D) Compensating control

---

**Q17.** A multinational enterprise federates its on-premises Active Directory (acting as Identity Provider) with a SaaS CRM platform using SAML 2.0 for SSO. The security team notes that SAML assertions are digitally signed but not encrypted, relying on TLS to protect the channel. The assertion is posted back to the service provider via the user's browser (browser POST binding). Which statement BEST describes the residual risk in this configuration?

A) There is no residual risk because TLS fully protects the assertion contents from disclosure and tampering during the browser redirect
B) Signing alone is sufficient and encryption is never required for SAML assertions under any circumstance defined by the SAML 2.0 specification
C) The risk only exists if the Identity Provider uses SAML 1.1 instead of 2.0, since 2.0 mandates end-to-end assertion encryption
D) Because the assertion transits through the user's browser as an intermediary, sensitive attributes could still be exposed via browser cache, history, developer tools, or a compromised endpoint, even though the transport channel is encrypted

---

**Q18.** A company operates workloads across AWS, Azure, and GCP and wants to enforce consistent, fine-grained, attribute-based access policies for thousands of identities and continuously discover excessive or unused permissions across all three environments. Per CCSK guidance on identity and access management in multi-cloud, which approach BEST meets this requirement?

A) Manage entitlements independently in each provider's native console, reconciling permissions manually via quarterly spreadsheet audits
B) Issue a single shared root/owner credential across all three providers so one team can manage access uniformly
C) Restrict access exclusively through network-layer security group and firewall rules, since IAM policies are redundant once network segmentation is in place
D) Deploy a Cloud Infrastructure Entitlement Management (CIEM) solution that aggregates identity and permission data across providers and applies attribute-based policies with continuous least-privilege analysis

---

**Q19.** An organization wants to minimize standing privileged access for cloud administrators who only need elevated rights occasionally for emergency changes. Which privileged access configuration BEST aligns with CCSK recommendations for minimizing standing privilege risk?

A) Assign a permanent Administrator role to each on-call engineer, protected only by MFA at login
B) Configure just-in-time (JIT) privilege elevation through a PAM solution requiring approval, granting time-bound access that auto-expires, with the session fully logged
C) Maintain a single shared break-glass admin account with a static password known to the on-call team, used only during outages
D) Disable MFA for the admin role so that emergency access is not delayed during outages, compensating with strict network ACLs instead

---

**Q20.** In a standard enterprise-to-cloud-provider SAML 2.0 federation used for SSO into a SaaS application, which entity functions as the Relying Party (Service Provider), and which functions as the asserting party?

A) The SaaS application is the asserting Identity Provider, and the enterprise directory is the Relying Party consuming assertions
B) Both the enterprise directory and the SaaS application act simultaneously as Identity Provider and Relying Party in a peer-to-peer trust model
C) Neither entity holds a distinct role; SAML 2.0 uses a broker service that issues assertions independently of both parties
D) The enterprise's on-premises directory acts as the Identity Provider (asserting party), issuing signed assertions about the user, while the SaaS application acts as the Relying Party (Service Provider), consuming and validating those assertions to grant access

---

**Q21.** A company relies solely on its IaaS provider's default logging configuration. After an incident, the investigation team discovers that critical administrative API calls were never captured because the relevant service does not log by default. What is the BEST way to prevent this gap going forward?

A) Increase log retention period across all services to at least one year
B) Rely on the CSP's published shared responsibility matrix to confirm which logs are captured automatically
C) Explicitly enable and validate logging for every in-scope service during deployment, treating it as a build requirement rather than assuming provider defaults are comprehensive
D) Wait until a security incident triggers a support ticket to the CSP requesting additional logging be enabled

---

**Q22.** In a large-scale IaaS environment, which log source is MOST critical to centralize immediately to a separate, isolated account outside the monitored environment, to preserve its integrity if the account itself is fully compromised?

A) Management plane (control plane) API/audit activity logs
B) Application-level transaction logs
C) Operating system syslog/event logs from compute instances
D) Network flow logs between subnets

---

**Q23.** To satisfy CCSK guidance on maintaining an immutable, tamper-resistant audit trail for cloud logs, which combination of controls should be applied to the central log storage?

A) Encrypt all logs at rest with a customer-managed key and increase logging verbosity
B) Grant all workload service accounts write access to the central log store so any service can push logs directly
C) Apply object-lock/WORM storage settings on the log store, restrict log-deletion permissions to a separate isolated account, and enable automated replication to that account
D) Configure log rotation policies with a 90-day local retention limit before deletion

---

**Q24.** A multi-cloud enterprise wants to detect a coordinated attack spanning workloads in an IaaS provider and a separate SaaS application. Per CCSK guidance, what is the PRIMARY monitoring challenge in this scenario?

A) Insufficient encryption in transit between the IaaS provider and the SaaS application
B) Storage capacity limits that prevent collection of SaaS audit logs
C) SaaS providers do not offer any audit logs, making cross-platform detection impossible
D) Lack of standardized log schemas and telemetry formats across providers, requiring normalization before correlation in a central SIEM

---

**Q25.** A financial services company runs a three-tier application (web, app, database) across a single VPC in a public cloud IaaS environment. A penetration test reveals that if the web tier is compromised, an attacker can directly reach the database tier over the network with no restrictions. Which change BEST addresses this finding while aligning with CCSK guidance on cloud network segmentation?

A) Move the database tier to a separate on-premises data center connected via a site-to-site VPN
B) Implement micro-segmentation using security groups or a distributed firewall to restrict inter-tier traffic based on least privilege
C) Enable DDoS protection on the public-facing load balancer
D) Increase the CIDR block size of the VPC to create larger, more isolated address ranges

---

**Q26.** According to CCSK guidance, what is the PRIMARY security advantage that software-defined networking (SDN) provides in cloud environments compared to traditional physical networking?

A) It eliminates the need to encrypt data in transit between virtual machines
B) It automatically guarantees compliance with data residency and sovereignty requirements
C) It removes the customer's responsibility for configuring security groups or network ACLs
D) It separates the control plane from the data plane, enabling centralized, programmatic policy enforcement and rapid reconfiguration of network security controls

---

**Q27.** When configuring security groups and network ACLs for a new production subnet, which default configuration aligns with CCSK best practice for the cloud network security perimeter?

A) Default allow all inbound and outbound traffic, then add deny rules for known malicious IP ranges
B) Default deny all inbound and outbound traffic, then explicitly allow only the specific ports, protocols, and sources required (least privilege)
C) Default allow all traffic within the VPC/VNet and deny only traffic destined to the public internet
D) Configure NACLs to log all traffic while leaving security groups in their default allow-all state for troubleshooting

---

**Q28.** According to CCSK guidance, why do traditional network-based intrusion detection tools that rely on physical network taps or SPAN ports often fail to provide adequate visibility in a public cloud IaaS environment?

A) Cloud providers do not support any form of network traffic logging or flow monitoring
B) Encryption of all cloud traffic by default makes any form of packet inspection legally prohibited
C) Intrusion detection systems are architecturally incompatible with the TCP/IP protocol stack used in virtualized cloud networks
D) Cloud customers lack access to the underlying physical network and hypervisor layer where such taps would need to be placed, requiring cloud-native flow logs and virtual network security tools instead

---

**Q29.** A multi-tenant Kubernetes cluster hosts workloads from two business units in separate namespaces, sharing the same underlying nodes. A pod in Namespace A is compromised via a vulnerable application dependency. Which control BEST prevents the attacker from moving laterally to workloads in Namespace B?

A) Enforcing Kubernetes NetworkPolicies that restrict cross-namespace pod traffic to only explicitly required flows
B) Increasing pod CPU/memory limits to prevent resource exhaustion
C) Enabling audit logging on the Kubernetes API server only
D) Using a single shared service account across all namespaces to simplify RBAC management

---

**Q30.** A serverless application consists of 15 functions, each performing a distinct task (e.g., image resize, DB write, notification send). Security review finds every function currently uses the same broad execution role with full account access. Which change BEST mitigates the risk of a compromised function accessing unintended resources?

A) Assigning least-privilege, function-specific IAM execution roles scoped only to the resources each function actually needs
B) Increasing each function's memory allocation to reduce cold start latency
C) Enabling versioning and aliases for each function
D) Keeping a single shared execution role across all functions for consistency and easier auditing

---

**Q31.** An organization wants to guarantee that no container image with critical CVEs or missing a valid signature can ever be scheduled to run in production Kubernetes namespaces, regardless of who submits the deployment manifest. Which control should be implemented?

A) Configuring a Horizontal Pod Autoscaler on the production deployments
B) Deploying a policy-enforcing admission controller (e.g., OPA/Gatekeeper or a native validating webhook) that rejects pod creation for unscanned, unsigned, or vulnerable images
C) Increasing the replica count in the Deployment specification
D) Setting liveness and readiness probes on the container spec

---

**Q32.** In cloud workload hardening, what is the primary security benefit of an immutable infrastructure model (replacing whole instances/containers on update) compared to patching running instances in place?

A) It eliminates the need for vulnerability scanning of workload images
B) It removes the requirement for network segmentation between workloads
C) It guarantees zero downtime during every single deployment
D) It reduces configuration drift by replacing the entire instance/container with a known-good build from a versioned artifact, producing a consistent and auditable state

---

**Q33.** A financial services firm wants strict separation of duties between itself and its cloud provider for encrypted data at rest. The requirement states that the customer must be able to instantly revoke the provider's ability to decrypt data, even though the provider controls the storage infrastructure. Which key management approach BEST meets this requirement?

A) Provider-managed encryption keys (default managed keys), where the CSP retains full control over key generation, storage, and lifecycle
B) Hold Your Own Key (HYOK) — the key is generated and stored within an external key manager under customer control, and the CSP must call out to it for every cryptographic operation
C) Bring Your Own Key (BYOK) — the customer generates the key but imports it into the CSP's key management service for storage and use
D) Tokenization of all data prior to upload, removing the need for encryption keys entirely

---

**Q34.** A payment processor stores credit card Primary Account Numbers (PANs) alongside non-sensitive transaction metadata in a cloud database. It must minimize PCI DSS audit scope for that database while still allowing analytics queries on the non-sensitive fields. Which approach BEST achieves this goal?

A) Format-preserving encryption (FPE) applied to the entire database
B) Tokenization of the PAN field only, replacing it with a non-sensitive token stored in a separate, isolated token vault
C) Homomorphic encryption applied to all fields
D) Masking the PAN field only during data export in reports

---

**Q35.** During the 'Destroy' phase of the cloud data security lifecycle, an organization needs to render objects encrypted with a customer-managed key permanently unrecoverable. The organization does not control the underlying physical storage media, which is shared multi-tenant infrastructure owned by the CSP. Which method is the FASTEST and MOST reliable way to achieve this?

A) Requesting the CSP perform certified physical destruction of the underlying drives
B) Overwriting the data multiple times using the DoD 5220.22-M standard
C) Cryptographic erasure — deleting/destroying the encryption key so the ciphertext becomes permanently unreadable
D) Relying on the CSP's default data retention policy to delete the data after the retention period expires

---

**Q36.** Which statement BEST distinguishes data masking from encryption as data-centric security controls, per CSA guidance?

A) Masking is reversible using a decryption key, while encryption is one-way and cannot be undone
B) Masking and encryption are functionally identical, differing only in the algorithm used
C) Masking always requires a hardware security module (HSM), while encryption does not
D) Masking permanently or temporarily obscures data (often irreversibly, e.g., for non-production/test environments), while encryption is designed to be reversible using an authorized key

---

**Q37.** A cloud-native company enforces a policy that container images may only be deployed to production if they were produced by the official CI/CD pipeline. Developers occasionally push images directly to the registry for 'quick fixes', bypassing the pipeline's security scans. Which control BEST enforces the policy while allowing automation to scale?

A) Require developers to name manually pushed images with a '-manual' suffix and configure the orchestrator to reject any image with that suffix
B) Segment the production network so that only the CI/CD server's IP address can reach the container registry
C) Have the pipeline cryptographically sign each image it builds and configure an admission controller to verify the signature and attestation before allowing deployment
D) Require a peer code review approval in the version control system before any commit can trigger a build

---

**Q38.** An application needs credentials to connect to a cloud database. The security team wants to eliminate long-lived, shared database passwords entirely. Which secrets management configuration BEST achieves this?

A) Store the database password in an encrypted configuration file bundled with the application deployment artifact
B) Inject the database password as an environment variable at container runtime using the orchestrator's built-in secret object
C) Use a secrets management engine to issue short-lived, per-session database credentials dynamically at request time, with automatic expiration
D) Rotate the shared database password manually every 90 days according to the corporate password policy

---

**Q39.** A DevSecOps team wants to add a pipeline stage specifically to detect known vulnerabilities in third-party open-source libraries pulled in as application dependencies, before the build artifact is promoted. Which testing technique should be added to the pipeline?

A) Dynamic Application Security Testing (DAST) against the running staging environment
B) Static Application Security Testing (SAST) against the application's own source code
C) Interactive Application Security Testing (IAST) instrumented into the QA test suite
D) Software Composition Analysis (SCA) against the dependency manifest and resolved package tree

---

**Q40.** A team currently patches running virtual machine instances in place using configuration management scripts whenever a vulnerability is disclosed, leading to configuration drift and inconsistent patch levels across the fleet. Which architectural principle from CCSK guidance BEST addresses this problem?

A) Increase the frequency of the configuration management scripts from weekly to daily to catch drift faster
B) Adopt immutable infrastructure: rebuild a new image with the patch applied and redeploy, replacing running instances rather than modifying them in place
C) Add more detailed logging to the configuration management tool so drift can be identified after it occurs
D) Grant the configuration management tool broader administrative privileges so it can enforce patches more forcefully

---

**Q41.** During a suspected breach investigation of a compromised VM in a multi-tenant IaaS environment, the incident responder needs to preserve volatile memory evidence without alerting the attacker or disrupting co-tenants on the shared physical host. What is the BEST approach?

A) Take a live snapshot of the VM instance (including memory state) using the CSP's native snapshot/API capabilities, then analyze the snapshot in an isolated forensic environment
B) Immediately power off the VM instance to preserve the disk state for forensic imaging
C) Request the CSP's legal team to physically seize the underlying hardware hosting the VM for chain-of-custody purposes
D) Install a forensic memory-capture agent directly on the live compromised VM to dump RAM in real time

---

**Q42.** An organization wants its cloud-native application to remain available even if its primary cloud provider suffers a complete regional outage, while keeping RTO and RPO as low as possible. Which architecture BEST satisfies this resilience requirement per CSA guidance?

A) Rely on the CSP's published SLA guarantee of 99.99% regional availability as the primary control
B) Implement a multi-region active-passive architecture with automated failover and near-real-time data replication
C) Deploy the application across multiple Availability Zones within the primary region using auto-scaling groups
D) Increase backup frequency to hourly snapshots stored within the same primary region

---

**Q43.** An organization is configuring log retention settings as part of its cloud incident response readiness. Per CSA guidance, what should PRIMARILY drive the chosen retention period rather than simply accepting the CSP's out-of-the-box default?

A) The CSP's default retention setting, since it is pre-optimized for the majority of customer use cases
B) The maximum retention period offered before the logging service begins charging additional storage fees
C) The organization's incident response, legal, and regulatory requirements, including how far back an incident might need to be traced for detection and investigation
D) A fixed 30-day retention window, matching common baseline practice for perimeter network logs

---

**Q44.** Per CSA cloud resilience guidance, which statement BEST distinguishes the concept of "resilience" from "redundancy"?

A) Redundancy involves duplicating components to remove single points of failure, while resilience is the broader system-level capacity to absorb disruption, adapt, and recover functionality — of which redundancy is only one contributing factor
B) There is no meaningful distinction; the CCM and CSA guidance use the two terms interchangeably
C) Redundancy applies only to the CSP's underlying infrastructure, while resilience applies only to customer-managed application workloads
D) Redundancy refers strictly to data backup copies, while resilience refers strictly to the robustness of application source code

---

**Q45.** A security architect is implementing a Zero Trust Architecture per NIST SP 800-207 across a multi-cloud environment. A colleague states: 'The Policy Enforcement Point (PEP) calculates the trust score using the trust algorithm and decides whether to grant access, while the Policy Engine just carries out the connection.' Which statement correctly identifies the flaw in this description?

A) The colleague is correct — PEPs run the trust algorithm while Policy Engines only open or close connections
B) The roles are reversed: the Policy Engine applies the trust algorithm to render the access decision, and the PEP only enforces that decision by enabling or terminating the connection
C) Zero Trust architectures do not use trust algorithms; access decisions are made using static, pre-assigned role tables
D) The PEP and Policy Engine are the same logical component in NIST SP 800-207 and can be used interchangeably

---

**Q46.** A global retail company wants to consolidate branch-office network security and cloud access security controls into a single cloud-delivered service, remove reliance on on-premises security appliances, and enforce identity-aware policies for users connecting from any location. Which architecture BEST meets these requirements?

A) A SASE architecture combining SD-WAN with cloud-delivered SWG, CASB, ZTNA, and FWaaS under a unified policy framework
B) A regional MPLS backbone terminating at a centralized on-premises next-generation firewall for inline inspection of all branch traffic
C) A standalone CASB deployed via API-based integration with sanctioned SaaS applications only
D) A traditional hub-and-spoke VPN design backhauling all branch traffic to a central data center firewall

---

**Q47.** An organization deploys a Retrieval-Augmented Generation (RAG) GenAI chatbot that queries an internal vector database containing sensitive customer records to augment LLM responses. Which control MOST directly mitigates the risk of the chatbot leaking sensitive data to unauthorized users through crafted prompts?

A) Fine-tuning the LLM further on additional customer records to improve the relevance of retrieved context
B) Increasing the LLM's context window size so more retrieved documents can be included per response
C) Enabling verbose logging of all prompts and generated responses for post-incident forensic review
D) Enforcing document- and record-level access controls at the retrieval layer so vector search only returns content the requesting user is authorized to view

---

