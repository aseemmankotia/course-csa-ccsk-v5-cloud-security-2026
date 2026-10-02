## Domain 11 Cheat Sheet: Incident Response & Resilience

### IR Lifecycle (PICERL)
| Phase | Focus | Cloud-Specific Note |
|---|---|---|
| Preparation | Playbooks, access, tooling ready | Pre-authorize provider support/forensic access in contracts |
| Detection | Identify anomalous activity | Rely on cloud-native logs (API/audit logs), CSPM alerts |
| Containment | Stop the damage | Revoke keys, isolate instances/security groups, snapshot first |
| Eradication | Remove root cause | Rebuild from known-good images rather than patching in place |
| Recovery | Restore normal operation | Validate via monitoring before full cutover |
| Lessons Learned | Post-incident review | Update runbooks, IAM policies, detection rules |

### Forensic Challenges Unique to Cloud
- **Volatile evidence:** RAM lost on shutdown — snapshot before isolating.
- **No physical access:** Multi-tenancy prevents hardware seizure; rely on provider APIs/logs.
- **Provider cooperation:** Evidence requests depend on contract SLAs and legal process.
- **Jurisdiction:** Data may span countries — cross-border legal mechanisms (MLAT, subpoena) required.
- **Log ownership:** Ensure audit logging (e.g., API call logs) is enabled and retained *before* an incident.

### Shared Responsibility for IR
| Layer | IaaS | PaaS | SaaS |
|---|---|---|---|
| Physical/hypervisor | Provider | Provider | Provider |
| OS/network config | Customer | Provider | Provider |
| App/data/access | Customer | Customer | Customer |

### RTO vs RPO
| Metric | Measures | Driven By |
|---|---|---|
| RTO | Downtime tolerance | Failover speed, automation |
| RPO | Data loss tolerance | Backup/replication frequency |

**Rule:** RPO ≈ interval between recovery points (worst case). Backup every 4 hrs → RPO up to 4 hrs.

### DR Architecture Patterns (relative RTO/RPO)
| Pattern | Relative RTO | Relative RPO | Cost |
|---|---|---|---|
| Backup & Restore | Highest (hours+) | Highest | Lowest |
| Pilot Light | Medium | Medium | Low-Medium |
| Warm Standby | Low | Low | Medium-High |
| Multi-Site Active-Active | Lowest (near-zero) | Lowest (near-zero) | Highest |

### Resilience Best Practices
- Test failover regularly (game days) — untested DR = unreliable DR.
- Use multi-region replication for critical, low-RTO/RPO workloads.
- Automate failover where possible to remove manual-runbook risk.

### Exam Traps
- Don't power off a compromised VM immediately — kills volatile evidence.
- Don't assume provider handles customer-level IR (credential misuse, app-layer).
- RTO ≠ RPO — know which measures downtime vs. data loss.
- DR plan without periodic testing is a common wrong-answer trap.
