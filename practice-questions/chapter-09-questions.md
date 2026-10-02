## Chapter 9: Domain 10: Application Security — Practice Questions

**Q1.** A developer commits a database connection string containing a plaintext password directly into the application's source code repository. What is the BEST remediation to prevent this class of issue going forward?

A) Encrypt the repository at rest so the password is not readable by attackers
B) Require code reviewers to manually check every commit for passwords before merging
C) Store the password in an environment variable file that is added to .gitignore
D) Move the credential to a centralized secrets management/vault service and inject it at runtime, combined with pre-commit secret scanning

<details>
<summary>Answer</summary>

**Correct: D**

Vaulting secrets and injecting them at runtime removes credentials from source entirely, and pairing this with automated pre-commit/pipeline secret scanning prevents recurrence — this is the CCSK-recommended secrets management approach.

**Why the others are wrong:**
- Repository encryption at rest protects against storage-level theft but does nothing to stop the credential being exposed to every developer, CI log, or git history diff
- Manual review does not scale and is unreliable — automation is required for consistent enforcement
- .gitignore only prevents future accidental commits of that specific file; it does not remove the secret from code, and the file may still be readable locally or shipped in a build artifact

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** In a shift-left DevSecOps model, at which point in the SDLC should security requirements and threat modeling FIRST be introduced?

A) During the final penetration test before production release
B) Immediately after the CI build completes, using SAST tooling
C) During the design and architecture phase, before code is written
D) During the post-incident review after a production breach

<details>
<summary>Answer</summary>

**Correct: C**

Shift-left means moving security activities as early as possible in the SDLC — threat modeling and security requirements gathering belong in design, before a single line of code is written, so defects are cheapest to fix.

**Why the others are wrong:**
- Pen testing at the end is 'shift-right' thinking — the opposite of the shift-left principle the exam tests
- SAST after build is still relatively early, but it is a code-scanning control, not the earliest possible point — design-phase threat modeling comes before this
- Post-incident review is entirely reactive and represents a failure of shift-left security, not an example of it

</details>

---

**Q3.** A security team wants to identify SQL injection vulnerabilities in application source code before it is compiled or deployed. Which testing approach should they use?

A) SAST (Static Application Security Testing) against the source code
B) DAST (Dynamic Application Security Testing) against a staging deployment
C) Software Composition Analysis (SCA) against the dependency manifest
D) Runtime Application Self-Protection (RASP) in production

<details>
<summary>Answer</summary>

**Correct: A**

SAST analyzes source code, bytecode, or binaries without executing the application, making it the correct choice to find vulnerabilities like SQL injection before build/deploy — it fits directly into the shift-left, pre-compile stage of the pipeline.

**Why the others are wrong:**
- DAST tests a running application from the outside and requires a deployed instance — it happens later in the pipeline, not pre-compile
- SCA identifies known vulnerabilities in third-party/open-source dependencies, not custom-written injection flaws in first-party code
- RASP protects a running production application in real time — it is a runtime defense, not a pre-deployment testing method

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q4.** Which tool category is specifically designed to detect known CVEs in open-source libraries and packages pulled into an application build?

A) Static Application Security Testing (SAST)
B) Dynamic Application Security Testing (DAST)
C) Interactive Application Security Testing (IAST)
D) Software Composition Analysis (SCA)

<details>
<summary>Answer</summary>

**Correct: D**

SCA inventories third-party and open-source dependencies (including transitive dependencies) and matches them against known vulnerability databases to flag CVEs and license risks.

**Why the others are wrong:**
- SAST examines first-party source code logic for security flaws, not third-party dependency versions
- DAST probes a running application's behavior externally; it does not enumerate dependency manifests
- IAST instruments the application at runtime during functional testing to find flaws, but it is not the primary tool for dependency/CVE inventory

</details>

---

**Q5.** A CI/CD pipeline currently allows any developer with repository write access to also modify the production build and deployment scripts directly. Which control BEST addresses the associated risk?

A) Enforce role-based access control that separates code contribution rights from pipeline/deployment configuration rights, with approvals required to change pipeline definitions
B) Enable branch protection rules requiring pull request approval for the application repository only
C) Require all developers to use multi-factor authentication when logging into their laptops
D) Encrypt all pipeline logs to prevent credential leakage

<details>
<summary>Answer</summary>

**Correct: A**

Pipeline access control requires separating who can write application code from who can modify the pipeline/deployment logic itself, with least privilege and change approval on pipeline definitions — this directly closes the privilege escalation path described.

**Why the others are wrong:**
- Branch protection on the app repo alone does not restrict changes to the separate pipeline/deployment scripts described in the scenario
- MFA on laptops is a general identity control but does not address the lack of separation of duties within the pipeline itself
- Log encryption protects log confidentiality but does not prevent an authorized developer from tampering with the deployment pipeline

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q6.** Which practice provides the strongest assurance that a container image running in production is the exact, unmodified artifact that passed the security pipeline's testing stages?

A) Tagging the image with a version number such as v1.2.3
B) Storing the image in a private container registry
C) Scanning the image for vulnerabilities immediately after it is pulled at runtime
D) Cryptographically signing the artifact at build time and verifying the signature before deployment

<details>
<summary>Answer</summary>

**Correct: D**

Artifact/build signing (e.g., via Sigstore/cosign or equivalent) cryptographically binds an artifact to its build provenance; verifying that signature at deploy time proves the artifact was not tampered with after it left the trusted pipeline.

**Why the others are wrong:**
- Version tags are metadata only — they can be reapplied to a different, tampered image with no cryptographic guarantee
- Registry privacy limits who can pull the image but does not prove integrity or unaltered provenance
- Runtime scanning checks for known vulnerabilities but does not verify that the artifact matches what was originally built and tested

</details>

---

**Q7.** What is the fundamental distinction between traditional DevOps and DevSecOps?

A) DevSecOps replaces automated testing with manual security sign-off gates before every release
B) DevSecOps eliminates the need for a security team entirely by giving developers full autonomy
C) DevSecOps integrates security as a shared, automated responsibility embedded throughout the pipeline, rather than as a separate gate applied only at the end
D) DevSecOps only applies to on-premises environments, while DevOps applies to cloud-native environments

<details>
<summary>Answer</summary>

**Correct: C**

DevSecOps embeds security controls (SAST, SCA, secrets scanning, IaC checks) directly and automatically into the existing CI/CD workflow so security is continuous and shared across teams, instead of a late-stage manual gate.

**Why the others are wrong:**
- DevSecOps actually reduces reliance on manual, end-of-cycle sign-off gates by automating checks earlier — this option describes the opposite
- DevSecOps redistributes security responsibility to developers but does not eliminate the security team's role in governance and tooling
- Both DevOps and DevSecOps apply equally to cloud-native and on-prem environments; this distinction is invented and not part of the model

</details>

---

**Q8.** An API allows any authenticated user to retrieve another user's order details simply by changing the numeric order ID in the request URL. Which control category BEST addresses this vulnerability?

A) Rate limiting on the API gateway
B) TLS encryption for all API traffic
C) Object-level authorization checks that verify the requesting user owns or is entitled to the specific resource ID
D) Input validation on the order ID field to ensure it is numeric

<details>
<summary>Answer</summary>

**Correct: C**

This describes Broken Object Level Authorization (BOLA), the top-ranked risk in the OWASP API Security Top 10 — the fix is enforcing per-object authorization checks on every request, not just authenticating the user.

**Why the others are wrong:**
- Rate limiting slows abuse volume but does not stop a single unauthorized request from succeeding
- TLS protects data in transit from interception but does not prevent an authenticated user from accessing another user's authorized data
- Validating that the ID is numeric confirms format only — it does nothing to check whether the authenticated user is entitled to that specific ID

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

