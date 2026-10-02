## Chapter 7: Domain 8: Cloud Workload Security — Practice Questions

**Q1.** A team's CI/CD pipeline pushes container images directly to the production registry with no pre-deployment checks. Several deployed images later turn out to contain known critical CVEs. Which control BEST addresses this supply chain gap?

A) Add network segmentation between application tiers
B) Enable Kubernetes Pod Security admission on the cluster
C) Rotate the CI/CD service account's IAM credentials
D) Integrate automated image scanning into the CI/CD pipeline before images reach the registry

<details>
<summary>Answer</summary>

**Correct: D**

Scanning images at build time (shift-left) catches known CVEs before they ever reach the registry or a runtime environment, closing the supply-chain gap directly.

**Why the others are wrong:**
- Network segmentation limits blast radius but does not prevent vulnerable images from being deployed
- Pod Security admission controls pod configuration (privilege, capabilities) but does not detect CVEs in image layers
- Credential rotation is a good hygiene practice but is unrelated to vulnerable image content

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** A Lambda-style function triggered by object-storage events has an execution role granting full administrative access to every bucket in the account. What is the correct remediation?

A) Increase the function timeout to reduce retries
B) Enable distributed tracing on the function
C) Move the function into a VPC
D) Scope the execution role to only the specific bucket and actions the function actually needs

<details>
<summary>Answer</summary>

**Correct: D**

Least-privilege scoping of the execution role to the exact bucket and actions required eliminates the over-permissioned identity, which is the actual risk.

**Why the others are wrong:**
- Timeout settings have no bearing on IAM permission scope
- Tracing improves observability but does not reduce the excessive permissions
- VPC placement affects network reachability, not the function's identity permissions

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** A multi-tenant Kubernetes cluster runs workloads for several internal teams. Before considering separate clusters, which combination provides the strongest logical isolation between teams?

A) Node taints alone, with all teams sharing one namespace
B) A single shared namespace with distinct resource labels per team
C) Separate namespaces per team combined with NetworkPolicies and namespace-scoped RBAC
D) Granting each team a ClusterRoleBinding to cluster-admin scoped by label selector

<details>
<summary>Answer</summary>

**Correct: C**

Namespaces provide the logical boundary, but only when paired with NetworkPolicies (traffic isolation) and RBAC (access isolation) do they form a meaningful multi-tenant control boundary.

**Why the others are wrong:**
- Node taints affect scheduling, not access or network isolation, and a shared namespace removes RBAC boundaries
- Labels are metadata only and enforce no actual isolation
- cluster-admin is cluster-wide by definition and cannot be meaningfully scoped by label — this defeats isolation

</details>

---

**Q4.** An organization wants a single category of tool that provides vulnerability management, runtime threat detection, and hardening checks consistently across VMs, containers, and serverless functions. Which category of tool are they describing?

A) CWPP (Cloud Workload Protection Platform)
B) CSPM (Cloud Security Posture Management)
C) SIEM (Security Information and Event Management)
D) CASB (Cloud Access Security Broker)

<details>
<summary>Answer</summary>

**Correct: A**

CWPP is defined specifically as workload-centric protection spanning VMs, containers, and serverless — combining vulnerability management, runtime protection, and hardening/posture checks.

**Why the others are wrong:**
- CSPM evaluates cloud account and service configuration, not the internals of individual workloads
- SIEM aggregates and correlates logs/events for detection, but is not itself a workload protection platform
- CASB governs SaaS/cloud service access and data control, unrelated to workload runtime protection

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q5.** A team wants to reduce configuration drift and guarantee every VM instance starts from a consistent, hardened baseline. Which approach BEST achieves this?

A) Manually patch each running instance on a recurring schedule
B) Disable automatic OS updates to avoid unplanned downtime
C) Deploy the unmodified default cloud marketplace image and rely on runtime detection
D) Build a hardened golden image and replace instances via automated rebuild/redeploy rather than in-place patching

<details>
<summary>Answer</summary>

**Correct: D**

Golden images combined with immutable, rebuild-and-replace deployment guarantee every instance is identical and hardened, eliminating drift that manual patching introduces.

**Why the others are wrong:**
- Manual per-instance patching causes drift as instances diverge over time and patch application is inconsistent
- Disabling updates leaves known vulnerabilities unpatched indefinitely
- Default marketplace images are not hardened and runtime detection only reacts after exploitation, not before

</details>

---

**Q6.** A security team wants to apply a Pod Security Standard that blocks known privilege-escalation paths (privileged containers, hostPID, hostNetwork, hostIPC) while still allowing most common application workloads to run without modification. Which PSS level should they apply?

A) Baseline
B) Privileged
C) Restricted
D) No Pod Security Admission (default open)

<details>
<summary>Answer</summary>

**Correct: A**

Baseline is specifically designed to block the well-known privilege-escalation vectors while remaining minimally disruptive and compatible with typical workloads, unlike Restricted which adds stricter, potentially workload-breaking constraints (non-root, no added capabilities).

**Why the others are wrong:**
- Privileged applies no restrictions at all and allows the exact behaviors that need blocking
- Restricted goes further than required (mandates non-root, drops all capabilities) and can break common workloads unnecessarily for this stated requirement
- No admission control leaves the cluster fully open to privileged and host-namespace pods

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** A developer requests permission to deploy an application into a single Kubernetes namespace. What is the correct RBAC configuration to grant?

A) A namespace-scoped Role containing only the required verbs/resources, bound via a RoleBinding
B) A ClusterRoleBinding granting cluster-admin, for simplicity
C) The built-in cluster-admin ClusterRole, bound via RoleBinding to limit its scope
D) Service account ownership rights on the underlying worker node

<details>
<summary>Answer</summary>

**Correct: A**

A Role scoped to the specific namespace with only necessary verbs, granted via RoleBinding, follows least privilege and matches the actual requirement.

**Why the others are wrong:**
- cluster-admin via ClusterRoleBinding grants full cluster-wide control, far exceeding the request
- Binding the cluster-admin ClusterRole via RoleBinding still grants all cluster-admin permissions within that namespace context (including secrets, RBAC changes) — it does not meaningfully limit scope to only deployment tasks
- Node-level ownership rights are unrelated to Kubernetes API-level access control

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q8.** Which statement best describes the immutable infrastructure hardening approach for cloud workloads described in CCSK guidance?

A) Patch running production instances in place via direct SSH access
B) Never modify running instances; rebuild from an updated golden image and replace the running workload
C) Allow long-lived servers to persist indefinitely with periodic manual audits
D) Use a configuration management agent to continuously reconfigure live production servers

<details>
<summary>Answer</summary>

**Correct: B**

Immutable infrastructure means workloads are never modified after deployment — updates happen by rebuilding a new hardened image and replacing the instance/container, eliminating configuration drift and unauthorized change.

**Why the others are wrong:**
- In-place SSH patching is exactly the mutable pattern immutable infrastructure is designed to avoid
- Long-lived, manually audited servers accumulate drift and unpatched vulnerabilities over time
- Continuous live reconfiguration via agents still mutates running production state, which contradicts the immutability principle

</details>

---

