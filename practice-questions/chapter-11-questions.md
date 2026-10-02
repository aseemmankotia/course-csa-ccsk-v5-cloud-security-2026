## Chapter 11: Domain 12: Related Technologies and Strategies — Practice Questions

**Q1.** A company wants to implement Zero Trust for remote employees accessing internal apps. Which principle is most fundamental to this design?

A) Never trust, always verify — authenticate and authorize every request regardless of location
B) Trust internal network traffic by default since it's already behind the firewall
C) Use VPN concentrators to grant full network access after initial login
D) Segment the network via VLANs only, with no additional authentication needed

<details>
<summary>Answer</summary>

**Correct: A**

Zero Trust's foundational principle rejects implicit trust from network location; every request must be authenticated and authorized based on real-time context.

**Why the others are wrong:**
- Assumes internal network location implies trust — the exact assumption Zero Trust eliminates
- VPN-granted full network access after one login is the legacy perimeter model Zero Trust replaces
- VLAN segmentation alone doesn't verify identity or continuously reassess trust per request

</details>

---

**Q2.** An organization deploys a GenAI chatbot using RAG (retrieval-augmented generation) over internal knowledge base documents. Security is concerned about sensitive data leaking into responses. What is the BEST mitigation?

A) Disable logging of chatbot conversations
B) Rely solely on the LLM vendor's built-in safety filters
C) Classify and redact sensitive data before indexing documents, and apply output filtering on responses
D) Restrict chatbot availability to business hours only

<details>
<summary>Answer</summary>

**Correct: C**

Data leakage from GenAI systems is mitigated at the source (classification/redaction of ingested data) and at the output (filtering responses) — a layered control approach.

**Why the others are wrong:**
- Disabling logs hides evidence but does nothing to prevent leakage in real time
- Vendor safety filters are not a substitute for organizational data governance controls
- Time restrictions have no bearing on data leakage risk

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** A security architect is designing a SASE deployment for a multinational retailer with many branch offices. Which combination best reflects true SASE convergence?

A) SD-WAN plus a traditional VPN concentrator and on-prem firewall appliances only
B) SD-WAN networking converged with cloud-delivered security services such as SWG, CASB, FWaaS, and ZTNA
C) An MPLS backbone with static routing and no security integration
D) A CASB deployed independently of the network layer, managed by a separate team

<details>
<summary>Answer</summary>

**Correct: B**

SASE's defining feature is converging SD-WAN networking with a full stack of cloud-delivered security services into a single, cloud-native edge architecture.

**Why the others are wrong:**
- This describes legacy perimeter architecture, not SASE convergence
- MPLS with no security integration is the opposite of SASE's design goal
- Separately managed CASB with no network integration fails the 'convergence' requirement of SASE

</details>

---

**Q4.** In the NIST Zero Trust Architecture model (SP 800-207), which component makes the actual access decision by evaluating policy against contextual signals for each session?

A) Policy Enforcement Point (PEP)
B) Data plane switch
C) SIEM correlation engine
D) Policy Engine (PE), part of the Policy Decision Point

<details>
<summary>Answer</summary>

**Correct: D**

The Policy Engine evaluates identity, device posture, and other signals against policy to render the grant/deny decision, functioning as part of the Policy Decision Point.

**Why the others are wrong:**
- The PEP enforces the decision (allows/blocks/terminates the connection) — it does not make the decision itself
- A data plane switch has no role in policy decision-making
- A SIEM aggregates and correlates logs; it is not a formal ZTA policy decision component

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q5.** Which of the following is the PRIMARY risk introduced by prompt injection attacks against LLM-based applications?

A) Increased GPU compute costs due to longer prompts
B) Malicious input manipulates the model into ignoring its instructions, leaking data, or performing unintended actions
C) Slower response latency due to token limits
D) Model weights are permanently corrupted on the vendor's servers

<details>
<summary>Answer</summary>

**Correct: B**

Prompt injection is an attack technique where crafted input overrides or subverts the model's intended instructions, causing data leakage or unauthorized actions.

**Why the others are wrong:**
- Compute cost is a performance/cost concern, not the security risk being tested
- Latency is unrelated to the security impact of prompt injection
- Prompt injection affects runtime behavior, not the underlying stored model weights

</details>

---

**Q6.** When securing an ML training pipeline against supply chain risks, which control provides the strongest assurance regarding the integrity of third-party pretrained models and datasets?

A) Rely on the informal reputation of the model's publisher
B) Use models from any public repository without verification
C) Retrain the entire model from scratch on every deployment
D) Validate cryptographic signatures/hashes of models and datasets and scan for known poisoning indicators before ingestion

<details>
<summary>Answer</summary>

**Correct: D**

Cryptographic validation and provenance/integrity scanning are concrete, verifiable controls against tampered or poisoned third-party artifacts.

**Why the others are wrong:**
- Reputation alone is not a verifiable technical control and can be spoofed
- Using unverified models directly maximizes supply chain risk
- Retraining from scratch every time is impractical and doesn't address poisoned source data

</details>

---

**Q7.** Under Zero Trust, which access control principle should govern how much access an authenticated identity is granted to a resource?

A) Least privilege — grant only the minimum access needed for the specific task, continuously reassessed
B) Broadest access to minimize support tickets
C) Role-based access granted permanently upon hire, never re-reviewed
D) Full administrative access to reduce friction for frequent users

<details>
<summary>Answer</summary>

**Correct: A**

Least privilege combined with continuous reassessment is a core Zero Trust tenet, ensuring access scope shrinks to only what is needed and is never assumed permanent.

**Why the others are wrong:**
- Broad access directly contradicts least privilege and increases attack surface
- Permanent, never-reviewed access violates the continuous verification requirement of Zero Trust
- Full admin access for convenience is the opposite of least privilege

</details>

---

**Q8.** Why does CCSK treat Zero Trust, SASE, and AI/GenAI security as 'cross-cutting' strategies rather than a standalone domain equivalent to IAM or Data Security?

A) Because they only apply to network security teams
B) Because they are legacy technologies being phased out
C) Because they are irrelevant to cloud computing
D) Because their principles and controls intersect with and reinforce practices across nearly all other CCSK domains

<details>
<summary>Answer</summary>

**Correct: D**

Domain 12 concepts reinforce and depend on controls from IAM, network security, data security, and incident response, making them cross-cutting rather than isolated.

**Why the others are wrong:**
- These strategies span identity, data, network, and application security — not just networking
- These are current, actively growing areas of cloud security practice, not deprecated technologies
- They are directly relevant and increasingly central to cloud security architecture

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

