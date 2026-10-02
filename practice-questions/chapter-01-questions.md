## Chapter 1: Domain 1: Cloud Computing Concepts and Architectures — Practice Questions

**Q1.** A company wants a service model where the CSP manages the operating system, middleware, and runtime, while the company retains full control over deploying its own application code. Which service model BEST fits this requirement?

A) IaaS
B) PaaS
C) SaaS
D) Community cloud

<details>
<summary>Answer</summary>

**Correct: B**

PaaS abstracts the OS, middleware, and runtime from the customer while leaving application code and data under customer control.

**Why the others are wrong:**
- IaaS still requires the customer to patch and manage the guest OS themselves.
- SaaS gives the customer no control over application code at all.
- Community cloud is a deployment model, not a service model, and does not address the responsibility split described.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** Which service model requires the customer to manage the guest operating system, middleware, and runtime environment, while the CSP manages only the underlying virtualization, servers, storage, and networking?

A) PaaS
B) SaaS
C) IaaS
D) Hybrid cloud

<details>
<summary>Answer</summary>

**Correct: C**

IaaS provides raw compute, storage, and networking; the customer owns everything from the OS upward.

**Why the others are wrong:**
- PaaS shifts OS/runtime/middleware management to the CSP.
- SaaS shifts application and data management largely to the CSP.
- Hybrid cloud is a deployment model, not a service model.

</details>

---

**Q3.** In the CSA logical model, which layer is where CSPs implement hypervisor-based multi-tenancy isolation and pool physical resources?

A) Resource abstraction and control layer
B) Physical infrastructure layer
C) Application layer
D) Orchestration layer

<details>
<summary>Answer</summary>

**Correct: A**

The resource abstraction and control layer (virtualization/hypervisor layer) is where physical resources are pooled and isolated between tenants.

**Why the others are wrong:**
- The physical infrastructure layer is the raw facility/hardware, before abstraction occurs.
- The application layer sits above abstraction and is where SaaS applications run.
- Orchestration is a cross-cutting management function, not the isolation/abstraction layer itself.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q4.** Which NIST essential characteristic of cloud computing refers to the ability of resources to scale rapidly and elastically, appearing to the consumer as unlimited and available in any quantity at any time?

A) Rapid elasticity
B) On-demand self-service
C) Broad network access
D) Measured service

<details>
<summary>Answer</summary>

**Correct: A**

Rapid elasticity specifically describes scaling capabilities up or down that appear unlimited to the consumer.

**Why the others are wrong:**
- On-demand self-service is about provisioning without human interaction with the provider, not scaling behavior.
- Broad network access refers to availability over the network via standard mechanisms.
- Measured service refers to automatic usage monitoring and billing transparency.

</details>

---

**Q5.** A consortium of five hospitals wants a shared cloud infrastructure that meets common HIPAA compliance requirements but is not available to the general public. Which deployment model BEST fits this scenario?

A) Community cloud
B) Public cloud
C) Private cloud
D) Hybrid cloud

<details>
<summary>Answer</summary>

**Correct: A**

Community cloud is provisioned for exclusive use by a group of organizations with shared concerns, such as compliance or mission requirements.

**Why the others are wrong:**
- Public cloud is open to the general public, which contradicts the exclusivity requirement.
- Private cloud is for a single organization, not multiple hospitals sharing infrastructure.
- Hybrid cloud combines two or more distinct infrastructure types; nothing in the scenario indicates a mix of deployment types.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q6.** An enterprise runs sensitive workloads on an on-premises private cloud and bursts non-sensitive workloads to a public cloud during peak demand. This scenario BEST describes which deployment model?

A) Multi-cloud
B) Community cloud
C) Hybrid cloud
D) SaaS

<details>
<summary>Answer</summary>

**Correct: C**

Hybrid cloud is a composition of two or more distinct cloud infrastructures (here, private and public) bound together with technology enabling data/application portability, such as cloud bursting.

**Why the others are wrong:**
- Multi-cloud refers to using multiple public cloud providers, not a mix of private and public deployment models.
- Community cloud involves shared infrastructure among multiple organizations with common concerns, not a private-to-public burst pattern.
- SaaS is a service model, not a deployment model, and doesn't describe the infrastructure relationship here.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** A company subscribes to a web-based CRM application, accessing it only through a browser with no access to underlying infrastructure or application code. Which service model is this?

A) IaaS
B) SaaS
C) PaaS
D) Private cloud

<details>
<summary>Answer</summary>

**Correct: B**

SaaS delivers fully managed applications to end users with no infrastructure or code-level access required.

**Why the others are wrong:**
- IaaS would require the customer to manage the OS and above, contradicting 'browser-only' access.
- PaaS would give the customer control over application code deployment, which is not the case here.
- Private cloud is a deployment model, not a service model, and doesn't describe the access pattern.

</details>

---

**Q8.** Under the shared responsibility model for IaaS, which of the following is ALWAYS the customer's responsibility regardless of the CSP used?

A) Physical security of data centers
B) Hypervisor patching
C) Network cabling infrastructure
D) Data classification and access control configuration

<details>
<summary>Answer</summary>

**Correct: D**

Data classification and configuring access controls fall under 'security in the cloud,' which remains the customer's responsibility in every service model, including IaaS.

**Why the others are wrong:**
- Physical security of data centers is the CSP's responsibility ('security of the cloud').
- Hypervisor patching is managed by the CSP in IaaS since the hypervisor sits below the customer's control boundary.
- Network cabling infrastructure is part of the physical facility, which the CSP manages.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

