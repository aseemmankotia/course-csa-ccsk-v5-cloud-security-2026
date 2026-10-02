## Chapter 4: Domain 5: Identity and Access Management — Practice Questions

**Q1.** A company acquires a startup that uses a cloud-native SaaS IdP with OIDC, while the parent company's workforce uses on-prem Active Directory with SAML 2.0 for enterprise app access. The security team wants users to authenticate once and access resources across both environments without duplicating identity stores. Which approach BEST meets this requirement?

A) Migrate all startup accounts into the parent company's Active Directory and disable the SaaS IdP
B) Synchronize all identities from both directories into a single shared LDAP database nightly
C) Issue separate local accounts in each system and require users to remember two sets of credentials
D) Establish a federation trust between the two IdPs so each retains authoritative control of its own identities while trusting assertions from the other

<details>
<summary>Answer</summary>

**Correct: D**

Federation establishes a trust relationship between distinct identity providers, allowing each to remain authoritative for its own users while accepting assertions (SAML or OIDC tokens) from the other — enabling SSO across organizational and protocol boundaries without merging identity stores.

**Why the others are wrong:**
- Migrating accounts destroys the acquired company's autonomy and creates a massive, risky one-time migration project instead of a scalable trust relationship
- Directory sync copies identity data on a schedule but does not provide real-time cross-domain SSO trust and creates duplicate, drifting identity stores
- Separate local accounts is the opposite of the requirement — it increases credential sprawl and user friction

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** During an audit, the security team discovers that dozens of former contractors still have active accounts with standing administrative access to production cloud consoles, some unused for over a year. Which control gap does this scenario BEST illustrate?

A) Insufficient network segmentation between production and development environments
B) Lack of encryption at rest for the identity provider's user database
C) Failure of identity lifecycle management, specifically the deprovisioning (leaver) process
D) Missing multi-factor authentication enrollment for contractor accounts

<details>
<summary>Answer</summary>

**Correct: C**

Accounts remaining active and privileged long after a user leaves is the textbook symptom of a broken joiner-mover-leaver (identity lifecycle) process — deprovisioning was not automated or enforced, leading to entitlement sprawl and orphaned accounts.

**Why the others are wrong:**
- Segmentation controls network paths, not whether stale accounts still exist and hold privileges
- Encryption at rest protects stored credentials from disclosure but does not explain why an account remains active after offboarding
- MFA reduces the risk of credential compromise but a properly offboarded account would be disabled regardless of MFA status

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** A cloud security architect wants to reduce the attack surface of administrative accounts by ensuring engineers only hold elevated privileges for the exact duration needed to perform a specific approved task, after which access is automatically revoked. Which capability BEST supports this goal?

A) Assigning all engineers a permanent admin role and relying on quarterly access reviews
B) Implementing just-in-time (JIT) privileged access through a PAM solution
C) Enabling directory synchronization between the identity provider and the cloud provider
D) Configuring SAML single sign-on for all engineering accounts

<details>
<summary>Answer</summary>

**Correct: B**

Just-in-time privileged access, delivered via a Privileged Access Management (PAM) solution, grants time-bound elevated permissions on approval and automatically expires them, eliminating standing privileged accounts — directly addressing the stated goal.

**Why the others are wrong:**
- Permanent admin roles with periodic reviews is the standing-privilege model this scenario is trying to eliminate
- Directory sync keeps identity attributes consistent but has nothing to do with time-limiting privilege elevation
- SAML SSO addresses authentication convenience, not the scoping or expiration of privileged authorization

</details>

---

**Q4.** A development team is building a modern mobile application that needs lightweight, token-based authentication using RESTful JSON calls, with easy integration into third-party social login providers. Which protocol should they select?

A) SAML 2.0
B) OpenID Connect (OIDC)
C) Kerberos
D) LDAP

<details>
<summary>Answer</summary>

**Correct: B**

OIDC is built on OAuth 2.0, uses lightweight JSON Web Tokens over REST, and is the modern standard for mobile and social-login integration, unlike XML-based SAML.

**Why the others are wrong:**
- SAML uses verbose XML assertions and browser redirects, better suited to enterprise web SSO than mobile/native apps
- Kerberos is a ticket-based protocol used primarily for on-prem network authentication, not internet-facing app auth
- LDAP is a directory access protocol for querying/authenticating against a directory service, not a federated token-based auth protocol for apps

</details>

---

**Q5.** An organization needs access decisions that dynamically consider the user's department, device compliance status, time of day, and data classification simultaneously, rather than relying on a fixed set of predefined roles. Which authorization model should they adopt?

A) Role-Based Access Control (RBAC)
B) Attribute-Based Access Control (ABAC)
C) Discretionary Access Control (DAC)
D) Mandatory Access Control (MAC)

<details>
<summary>Answer</summary>

**Correct: B**

ABAC evaluates multiple contextual attributes (user, resource, environment) at request time to make fine-grained, dynamic access decisions — exactly the requirement described.

**Why the others are wrong:**
- RBAC ties permissions to static predefined roles and cannot easily factor in dynamic context like time or device posture without creating an explosion of roles
- DAC lets resource owners grant access at their discretion; it doesn't provide centralized policy-driven contextual evaluation
- MAC enforces access based on fixed classification labels set by a central authority, not flexible multi-attribute evaluation

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q6.** According to standard multi-factor authentication guidance, which THREE categories of authentication factors are combined to strengthen identity assurance?

A) Something you own, something you share, something you remember
B) Something you know, something you have, something you are
C) Password, username, security question
D) Network location, device type, browser fingerprint

<details>
<summary>Answer</summary>

**Correct: B**

The classic MFA factor categories are knowledge (something you know, e.g., password/PIN), possession (something you have, e.g., token/phone), and inherence (something you are, e.g., biometric).

**Why the others are wrong:**
- This option renames concepts loosely but is not the recognized industry terminology
- These are all knowledge-based artifacts — using multiple knowledge factors does not constitute true MFA
- These are contextual/behavioral signals used in adaptive/risk-based authentication, not the core recognized MFA factor categories

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** A cloud security team is configuring a Privileged Access Management (PAM) solution to reduce risk from long-lived administrative credentials in their cloud environment. Which configuration BEST reflects PAM best practice?

A) Broker privileged sessions through the PAM vault, rotate credentials automatically after each checkout, and record sessions for audit
B) Store all admin passwords in a shared spreadsheet accessible to the operations team
C) Grant every DevOps engineer a permanent IAM admin policy to avoid workflow delays
D) Disable logging on privileged accounts to reduce storage costs

<details>
<summary>Answer</summary>

**Correct: A**

Core PAM configuration practices include credential vaulting, session brokering, automatic rotation after use, and session recording — eliminating shared standing credentials and enabling accountability.

**Why the others are wrong:**
- Shared spreadsheets are a severe anti-pattern that eliminates accountability and credential security entirely
- Permanent admin policies reintroduce the standing-privilege risk PAM is designed to eliminate
- Disabling logging on privileged accounts removes the audit trail needed to detect and investigate misuse

</details>

---

**Q8.** What is the key architectural difference between identity federation and directory synchronization?

A) Federation copies user account data into a second directory on a schedule; synchronization establishes a real-time trust relationship between two identity providers
B) Federation and synchronization are two names for the exact same process with no technical difference
C) Federation establishes a trust relationship allowing one IdP to accept assertions from another without copying credentials; synchronization replicates identity data between directories
D) Federation only works with SAML while synchronization only works with OIDC

<details>
<summary>Answer</summary>

**Correct: C**

Federation is a trust-based mechanism where one party accepts authentication assertions issued by another IdP, avoiding duplicate credential stores. Directory synchronization instead copies/replicates identity attributes (and sometimes hashed credentials) between two directories on a periodic basis.

**Why the others are wrong:**
- This reverses the definitions of the two mechanisms
- They differ fundamentally in trust model versus data replication — treating them as identical is a common exam trap
- Federation is protocol-agnostic and can use SAML, OIDC, or WS-Federation; synchronization is unrelated to a specific auth protocol

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

