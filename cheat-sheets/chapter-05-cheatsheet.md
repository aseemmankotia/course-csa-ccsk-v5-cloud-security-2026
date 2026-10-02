## Domain 6: Security Monitoring — Cheat Sheet (8% of exam)

### Logging Sources
| Source | Captures | Does NOT Capture | Example Services |
|---|---|---|---|
| Control plane | API calls to create/modify/delete resources | In-workload activity | Cloud audit/activity logs |
| Data plane | App/OS/data-handling activity inside workload | Resource management events | App logs, DB query logs, object access logs |
| Network flow logs | Traffic metadata: src/dst IP, port, protocol, bytes, allow/deny | Packet payload/content | VPC/vNet flow logs |

**Rule of thumb:** control plane = often on by default, low volume/cost. Data plane = usually must be explicitly enabled, high volume/cost. Multi-account environments require enabling control plane logging **per account** — the management account does not auto-capture child account activity (classic exam trap).

### Telemetry Types
| Type | What it shows | Use case |
|---|---|---|
| Metrics | Aggregated numeric time-series | Dashboards, threshold alerting (e.g., CPU%) |
| Logs | Discrete timestamped events | Forensic detail of a specific action |
| Traces | Request path + latency across services | Debugging distributed/microservice/serverless flows |

### SIEM vs SOAR vs CSPM
| Tool | Function |
|---|---|
| SIEM | Aggregates, normalizes, correlates logs → generates alerts |
| SOAR | Automates response/playbooks based on SIEM alerts |
| CSPM | Continuously evaluates resource **configuration** against baselines (misconfig/drift detection) |

**Exam distinction:** SIEM/SOAR = detection & response to events. CSPM = configuration compliance, not event correlation.

### Retention & Tamper-Evidence
- Reference model: **PCI DSS 10.5.1** — min 1 year total retention, at least 3 months immediately available (hot/searchable).
- Tiered retention pattern: hot/searchable window for active investigation → archive/cold storage for remaining compliance period.
- **Tamper-evidence** = WORM/object-lock immutable storage + hash chaining + separation of duties. Encryption ≠ tamper-evidence (protects confidentiality only, not integrity/immutability).

### Centralized Aggregation Best Practices
1. Enable logging in every account/subscription (not just management account).
2. Forward logs to a dedicated, access-restricted log archive account.
3. Normalize log formats to a common schema before SIEM ingestion.
4. Correlate across control plane, data plane, and network flow sources — no single source gives full visibility.
5. Apply consistently across all cloud providers in multi-cloud environments to avoid siloed blind spots.

### Common Exam Traps
- Assuming one log type (usually control plane) is sufficient for full detection.
- Confusing CSPM (config compliance) with SIEM (log correlation).
- Assuming root/management account logging aggregates all child accounts automatically.
- Treating encryption as equivalent to tamper-evidence.
