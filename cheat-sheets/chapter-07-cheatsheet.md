# Domain 8: Cloud Workload Security — Cheat Sheet (9%)

## Workload Types & Hardening Focus
| Workload | Hardening Focus | Key Control |
|---|---|---|
| VM | Golden image, patch mgmt, minimal OS | Immutable rebuild > in-place patch |
| Container | Minimal base image, no root, scan pre-deploy | Image scanning + signed registry |
| Kubernetes | Namespace isolation, PSS, RBAC | NetworkPolicy + RoleBinding scoping |
| Serverless | Event-source validation, execution role scope | Least-privilege IAM role per function |

## Pod Security Standards (PSS) Levels
| Level | Behavior |
|---|---|
| Privileged | No restrictions — unrestricted policy |
| Baseline | Blocks known privilege escalation: no privileged containers, no hostPID/hostNetwork/hostIPC |
| Restricted | Baseline + non-root required, all capabilities dropped, seccomp required |

## CWPP vs CSPM
| Tool | Protects | Example Check |
|---|---|---|
| CWPP | The workload runtime (VM/container/function) | Vulnerability scan, runtime anomaly detection, hardening state |
| CSPM | Cloud account/service configuration | Public S3 bucket, overly permissive IAM policy, unencrypted resource |

## Kubernetes RBAC Scoping
| Object | Scope | Use When |
|---|---|---|
| Role | Single namespace | Team needs access only within its namespace |
| ClusterRole | Cluster-wide (or reusable) | Needed across multiple namespaces or cluster-level resources |
| RoleBinding | Binds Role/ClusterRole to subject within one namespace | Preferred for least privilege |
| ClusterRoleBinding | Binds ClusterRole cluster-wide | Reserve for true cluster admins only |

## Container Supply Chain Controls
- Scan images in CI **before** registry push (shift-left)
- Re-scan images already in registry for newly disclosed CVEs
- Enforce image signing / content trust
- Pin specific image tags/digests — never deploy `latest` to production
- Runtime protection detects anomalies scanning cannot catch pre-deployment

## Serverless Security Checklist
- Scope execution role per-function to exact resources/actions needed
- Validate/authenticate every event source (API Gateway, queue, storage trigger) independently
- Set function timeout and concurrency limits to reduce abuse/DoS surface
- Avoid embedding long-lived secrets in function code — use a secrets manager

## Immutable Infrastructure Principle
- Never patch a running instance/container in place
- Rebuild from an updated, hardened golden image
- Redeploy/replace the running workload entirely
- Eliminates configuration drift and untracked manual changes

## Common Exam Traps
- Assuming a Kubernetes **namespace alone** = security boundary (it isn't — pair with NetworkPolicy + RBAC)
- Choosing **Restricted** PSS when **Baseline** is the minimally sufficient answer for the stated requirement
- Binding `cluster-admin` via RoleBinding thinking it limits scope — it still grants full admin rights within that namespace
- Confusing CWPP (workload protection) with CSPM (configuration posture) — different exam domain, different tool
- Overlooking that serverless expands attack surface via **event sources**, not just network paths
