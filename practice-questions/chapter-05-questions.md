## Chapter 5: Domain 6: Security Monitoring — Practice Questions

**Q1.** A company must ensure security logs cannot be altered or deleted after being written, to preserve forensic integrity for an incident investigation. Which control BEST achieves this?

A) Store logs in a standard read-write bucket with IAM access restricted to admins
B) Configure the log storage in immutable/WORM (Write Once Read Many) mode with object lock enabled
C) Encrypt logs at rest using customer-managed keys
D) Rotate the log storage service account credentials every 90 days

<details>
<summary>Answer</summary>

**Correct: B**

WORM/object-lock storage prevents modification or deletion of log objects for a defined retention period, even by privileged accounts, giving true tamper-evidence.

**Why the others are wrong:**
- IAM restrictions to admins don't stop tampering if admin credentials are compromised — it's an access control, not an immutability control.
- Encryption protects confidentiality of log data, not its integrity or immutability — encrypted logs can still be deleted or overwritten.
- Credential rotation is good hygiene but does nothing to prevent an authorized (or compromised) identity from altering logs.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** A security team can see API events showing that a virtual machine was created and later deleted, but cannot see what commands were run or what files were accessed inside that VM. Which logging source is missing?

A) Control plane logs
B) Data plane logs
C) Network flow logs
D) Billing/cost usage logs

<details>
<summary>Answer</summary>

**Correct: B**

Data plane logs capture activity inside the workload itself (OS commands, application actions, file/data access), which control plane logs do not record.

**Why the others are wrong:**
- Control plane logs are exactly what the team already has — they only show resource management API calls, not in-workload activity.
- Network flow logs record traffic metadata (IPs, ports, bytes) but not application-level actions inside the VM.
- Billing logs track cost/usage, not security-relevant activity.

</details>

---

**Q3.** An organization runs workloads across three different cloud providers and wants a single, correlated view of security alerts spanning all environments. What should it implement?

A) A separate CSPM tool native to each cloud provider
B) A centralized SIEM that aggregates and normalizes logs from all providers
C) The native security dashboard provided by each cloud console
D) Manual weekly log review by analysts on each provider's console

<details>
<summary>Answer</summary>

**Correct: B**

A centralized SIEM ingests, normalizes, and correlates logs across heterogeneous sources and providers, enabling cross-cloud detection of attack patterns.

**Why the others are wrong:**
- Per-provider CSPM tools assess configuration posture individually but don't correlate security events across environments.
- Native dashboards are siloed per provider and can't correlate activity across clouds.
- Manual review across multiple consoles is slow, error-prone, and cannot scale to real-time detection.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q4.** Which telemetry type would show the end-to-end latency and path of an individual request as it moves through multiple functions in a distributed serverless application?

A) Metrics
B) Traces
C) Logs
D) Alerts

<details>
<summary>Answer</summary>

**Correct: B**

Traces follow a single request across service boundaries, showing per-segment latency and the request's path through the system.

**Why the others are wrong:**
- Metrics are aggregated numeric time-series data (e.g., average CPU%), not a per-request path view.
- Logs are discrete timestamped event records; they don't inherently link a request's path across services without correlation IDs.
- Alerts are notifications triggered by thresholds — they are an output of monitoring, not a telemetry type themselves.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q5.** Which capability is MOST associated with Cloud Security Posture Management (CSPM) tooling?

A) Real-time packet capture and deep packet inspection of network traffic
B) Correlating on-premises SIEM alerts with cloud-native log sources
C) Encrypting data at rest across cloud storage services
D) Continuous evaluation of cloud resource configurations against security baselines

<details>
<summary>Answer</summary>

**Correct: D**

CSPM continuously assesses cloud resource configurations (e.g., public storage buckets, overly permissive security groups) against benchmarks to detect drift and misconfiguration.

**Why the others are wrong:**
- Deep packet inspection is a network monitoring/IDS-IPS function, not CSPM.
- Cross-source correlation is a SIEM function, not CSPM's primary purpose.
- Encryption management belongs to KMS/encryption services, not CSPM.

</details>

---

**Q6.** To balance investigator access speed with long-term compliance obligations, how should log retention typically be configured?

A) Delete logs after 30 days to minimize storage cost
B) Keep a shorter recent window in hot/searchable storage and archive older logs to cheaper cold storage for the remainder of the retention period
C) Keep all logs in hot, fully searchable storage indefinitely
D) Retain only the logs tied to confirmed security incidents

<details>
<summary>Answer</summary>

**Correct: B**

Tiered retention (e.g., a hot window for immediate analysis plus a longer archived retention period) mirrors common compliance models such as PCI DSS 10.5.1, which requires at least 3 months immediately available and 1 year total retention.

**Why the others are wrong:**
- 30 days is far too short to satisfy most compliance frameworks or support delayed-discovery incident investigations.
- Keeping everything hot indefinitely is unnecessarily costly and not what the exam expects as the 'best' answer.
- Retaining only incident-related logs is risky — undetected incidents leave no forensic trail.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** Which configuration approach ensures control plane logs are reliably captured and centrally retained across a multi-account/multi-subscription cloud environment?

A) Enable logging only in the primary/management account, assuming it automatically aggregates all child account activity
B) Rely on each account owner to manually export logs on a monthly basis
C) Store logs only within the account/subscription where they are generated
D) Enable control plane logging in each account/subscription and forward all logs to a centralized, access-restricted log archive account

<details>
<summary>Answer</summary>

**Correct: D**

Best practice is per-account/subscription trail enablement forwarded to a dedicated, restricted logging account — this centralizes visibility and protects logs even if a workload account is compromised.

**Why the others are wrong:**
- This is a classic exam trap: many control plane logging services require explicit enablement per account/subscription and do not automatically capture child account activity from the management account alone.
- Manual monthly export is slow, unreliable, and creates detection gaps.
- Storing logs only in the originating account creates a single point of failure — if that account is compromised, logs can be tampered with or deleted.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q8.** What is the PRIMARY difference between control plane and data plane logs in a cloud environment?

A) Control plane logs are always encrypted by default while data plane logs never are
B) Control plane logs are generated by the CSP infrastructure only, while data plane logs are generated only by the customer's SIEM
C) Control plane logging is optional while data plane logging is mandatory in all cloud providers
D) Control plane logs capture management/API-level actions on cloud resources; data plane logs capture actual data-handling and workload-level activity

<details>
<summary>Answer</summary>

**Correct: D**

This is the core conceptual distinction: control plane = resource management/API actions; data plane = actual workload and data activity.

**Why the others are wrong:**
- Encryption defaults vary by provider and service — this is not the defining distinction between the two log types.
- Both log types originate from the CSP's logging services applied to customer resources; the SIEM is a downstream consumer, not the source.
- Enablement requirements vary widely by provider and service tier — neither is universally mandatory across all cloud providers.

</details>

---

