# Domain 10: Application Security — Cheat Sheet

## Secure SDLC & DevSecOps
| Traditional SDLC | Cloud-Native Secure SDLC (DevSecOps) |
|---|---|
| Security review at milestones | Security checks automated on every commit/build |
| Manual pen test before release | Continuous SAST/DAST/SCA in pipeline |
| Security = separate team's job | Security = shared responsibility, shifted left |

**Shift-left** = introduce security as early as possible: threat modeling at design → secure coding standards → automated scanning in CI → pre-prod DAST → runtime monitoring.

## Testing Tool Categories
| Tool | Analyzes | When Run | Finds |
|---|---|---|---|
| SAST | Source/binary code | Pre-build (static) | Logic flaws: SQLi, XSS in custom code |
| DAST | Running app (black-box) | Post-deploy/staging | Runtime/config flaws, auth issues |
| IAST | Instrumented running app | During QA/functional tests | Combines static+dynamic insight |
| SCA | Dependency manifests | Build time | Known CVEs, license risk in OSS libs |

## CI/CD Pipeline Security Controls
- **Build integrity**: reproducible builds, signed artifacts (Sigstore/cosign) verified before deploy
- **Pipeline access control**: separate code-write rights from pipeline/deploy-config rights; least privilege service accounts; require approval for pipeline changes
- **Secrets in pipeline**: never store secrets in pipeline YAML/env vars in plaintext — pull from vault at runtime; mask secrets in logs
- **Dependency pinning**: lock file versions + SCA scan on every build
- **IaC scanning**: scan Terraform/CloudFormation templates for misconfig before apply

## Secrets Management
- Never hardcode credentials in code, config, or images
- Use vault services: HashiCorp Vault, AWS Secrets Manager, Azure Key Vault, GCP Secret Manager
- Enable automated rotation and short-lived/dynamic credentials where possible
- Use pre-commit scanners (git-secrets, truffleHog) to catch leaks before they enter history
- Deleting a secret from the latest commit ≠ removed from git history — must purge history/rotate the credential

## API Security (OWASP API Top 10, 2023 — 10 categories)
- **#1 BOLA** (Broken Object Level Authorization): enforce per-object server-side auth checks
- Broken authentication, excessive data exposure, lack of rate limiting also heavily referenced
- Rule: authentication proves *who* you are; authorization (object-level) proves *what you can access* — exam distinguishes these

## Architecture Patterns
- **Microservices**: smaller attack surface per service, but more inter-service auth (mTLS, service mesh) needed
- **Immutable infrastructure**: never patch in place — rebuild & redeploy signed artifact, destroy old instance
- **Zero trust for APIs**: authenticate + authorize every request, no implicit trust between services

## Common Exam Traps
- Confusing SAST (pre-build/code) with DAST (running app) — memory trick: **S**AST = **S**tatic = **S**ource
- Thinking secret deletion from latest commit is sufficient (history retains it)
- Believing TLS/encryption alone fixes API authorization flaws — it does not
- Assuming DevSecOps removes the security team — it redistributes, not eliminates, responsibility
