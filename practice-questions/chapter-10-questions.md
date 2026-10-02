## Chapter 10: Domain 11: Incident Response and Resilience — Practice Questions

**Q1.** A security team detects a compromised API key actively being used to spin up cryptomining instances in a customer's cloud account. According to the incident response lifecycle, what should be the IMMEDIATE next action?

A) Terminate all instances in the account and file a report
B) Wait for the cloud provider to shut down the malicious instances
C) Begin a full root-cause forensic investigation before touching any resource
D) Revoke/rotate the compromised credential and isolate the affected resources

<details>
<summary>Answer</summary>

**Correct: D**

This is the containment phase — stopping ongoing damage by revoking the credential and isolating affected resources is the priority before eradication or full analysis.

**Why the others are wrong:**
- Mass termination destroys volatile evidence and may cause unnecessary outage of unrelated workloads.
- Providers do not monitor or act on customer-level credential misuse — that's the customer's responsibility.
- Delaying containment to do deep forensics first allows the attacker to cause more damage; containment and evidence preservation happen together.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** An investigator needs to preserve RAM contents from a suspected-compromised IaaS virtual machine before it is isolated. What is the BEST approach given cloud constraints?

A) Take a live memory/instance snapshot via the cloud provider's API before any shutdown
B) Physically seize the underlying host server for offline analysis
C) Ask the cloud provider to preserve the host indefinitely for law enforcement
D) Power off the VM immediately to prevent further compromise

<details>
<summary>Answer</summary>

**Correct: A**

In multi-tenant cloud environments, customers cannot access physical hardware, so snapshotting the instance/memory state via provider APIs is the accepted method to preserve volatile evidence before isolation.

**Why the others are wrong:**
- Physical seizure is impossible in shared multi-tenant infrastructure — the customer never has hardware access.
- Providers do not indefinitely preserve individual customer instances; evidence preservation is the customer's responsibility unless contractually arranged.
- Powering off immediately destroys volatile memory (RAM) evidence, which is exactly what forensic acquisition aims to capture.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** During a cross-border cloud incident investigation, legal counsel advises that data relevant to the case is stored in a provider's data centers located in two different countries. Which factor MOST complicates this forensic investigation compared to a traditional on-premises case?

A) The lack of encryption on cloud storage volumes
B) The absence of any logging capability in cloud environments
C) Jurisdictional differences requiring legal processes (e.g., MLATs, subpoenas) to compel provider cooperation across borders
D) The inability of cloud providers to ever share evidence with customers

<details>
<summary>Answer</summary>

**Correct: C**

Data residency in multiple jurisdictions means differing laws govern evidence access and disclosure, often requiring formal cross-border legal mechanisms that slow investigations — a challenge rarely present with a single on-prem data center.

**Why the others are wrong:**
- Encryption is a control, not the core complicating factor for cross-border legal cooperation.
- Cloud environments typically have extensive logging (e.g., CloudTrail-style services); the issue is access/jurisdiction, not absence of logs.
- Providers do share evidence with customers/law enforcement, but the process is governed by contracts and law, not an absolute prohibition.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q4.** In the shared responsibility model, who is responsible for detecting and responding to an incident originating from a vulnerability in the cloud provider's hypervisor?

A) The customer, since they own all data in the account
B) Both parties equally in every deployment model
C) A third-party auditor contracted by the customer
D) The cloud provider, since the hypervisor is part of the underlying infrastructure they control

<details>
<summary>Answer</summary>

**Correct: D**

The hypervisor and physical/virtualization layer sit below the customer's line of visibility and control in IaaS, so the provider owns detection and response for that layer.

**Why the others are wrong:**
- Customers cannot detect or remediate hypervisor-level issues — they have no access to that layer.
- Responsibility split shifts with service model (IaaS/PaaS/SaaS); it is not a flat 50/50 split in every case.
- Auditors assess controls but are not responsible for operational incident response.

</details>

---

**Q5.** A company requires an RTO of under 5 minutes and an RPO of near-zero for a mission-critical transactional database running in the cloud. Which architecture BEST meets these requirements?

A) Multi-region active-active deployment with continuous, synchronous or near-real-time data replication
B) Nightly automated backups stored in cold/archive storage
C) Single-region deployment with a documented but untested manual failover runbook
D) Weekly full backups with monthly restore testing

<details>
<summary>Answer</summary>

**Correct: A**

Only a multi-region active-active pattern with continuous replication can deliver sub-5-minute RTO and near-zero RPO; other options have much larger recovery windows and data-loss exposure.

**Why the others are wrong:**
- Cold/archive backups have long restore times and large RPO gaps (hours to days), failing the requirement.
- An untested runbook does not guarantee the stated RTO/RPO and introduces high execution risk during a real event.
- Weekly backups create an RPO of up to a week, far exceeding near-zero data loss requirements.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q6.** If backup snapshots of a database are taken every 4 hours and no other replication exists, what is the maximum RPO for that system?

A) 0 minutes
B) 1 hour
C) 4 hours
D) 24 hours

<details>
<summary>Answer</summary>

**Correct: C**

RPO reflects the maximum acceptable/actual data loss window, which equals the interval between backups — in the worst case, up to 4 hours of data could be lost.

**Why the others are wrong:**
- Zero RPO requires continuous/synchronous replication, not periodic snapshots.
- 1 hour would only apply if snapshots were taken hourly.
- 24 hours would only apply to a daily backup schedule, not a 4-hour interval.

</details>

---

**Q7.** An organization has a documented disaster recovery plan for its cloud workloads but has never executed a failover. What is the BEST practice to validate that the DR plan will actually work during a real event?

A) Rely on the written plan and update it annually
B) Conduct regularly scheduled failover tests (e.g., game days) that exercise the actual failover process
C) Ask the cloud provider to certify the plan is sufficient
D) Increase backup frequency instead of testing failover

<details>
<summary>Answer</summary>

**Correct: B**

A DR plan is only proven effective through regular, realistic failover testing; documentation alone does not validate operational readiness.

**Why the others are wrong:**
- A plan that is never tested may contain gaps that only surface during an actual failover attempt.
- Providers do not certify customer-specific DR plans — DR design and validation is the customer's responsibility.
- Backup frequency affects RPO, not whether the failover mechanism itself functions correctly.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q8.** What is the key difference between Recovery Time Objective (RTO) and Recovery Point Objective (RPO)?

A) RTO measures data loss tolerance; RPO measures downtime tolerance
B) RTO measures downtime tolerance; RPO measures data loss tolerance, both expressed as time
C) RTO and RPO are interchangeable terms for the same metric
D) RTO applies only to on-premises systems; RPO applies only to cloud systems

<details>
<summary>Answer</summary>

**Correct: B**

RTO is the maximum acceptable time to restore a service after disruption; RPO is the maximum acceptable amount of data loss, measured as a time interval since the last recovery point.

**Why the others are wrong:**
- This reverses the definitions of RTO and RPO.
- They measure distinct dimensions of recovery — availability vs. data loss — and are not interchangeable.
- Both concepts apply equally to on-premises and cloud architectures; they are deployment-agnostic.

</details>

---

