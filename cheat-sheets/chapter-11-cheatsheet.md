## Domain 12 Cheat Sheet: Related Technologies and Strategies (7%)

### Zero Trust Core Principles
| Principle | Meaning | Exam Trap |
|---|---|---|
| Never trust, always verify | No implicit trust from network location; verify every request | Choosing answers that trust 'internal' traffic by default |
| Least privilege | Minimum access needed for the task, continuously reassessed | Confusing with permanent role-based grants |
| Continuous verification | Trust reassessed per-session using real-time context (identity, device, behavior) | Assuming one-time login = ongoing trust |
| Micro-segmentation | Isolate workloads/resources into small zones to limit lateral movement | Confusing with simple VLAN segmentation |

### NIST SP 800-207 ZTA Components
| Component | Role |
|---|---|
| Policy Engine (PE) | Decides grant/deny using policy + trust algorithm; part of PDP |
| Policy Administrator (PA) | Executes the PE's decision, communicates with PEP |
| Policy Decision Point (PDP) | PE + PA combined |
| Policy Enforcement Point (PEP) | Enables/monitors/terminates the connection per PDP decision |

**Exam tip:** PE/PDP *decides*, PEP *enforces*. Don't swap these.

### SASE (Secure Access Service Edge)
Converges **networking** (SD-WAN) + **security** delivered from the cloud edge:
| Layer | Components |
|---|---|
| Networking | SD-WAN |
| Security | SWG, CASB, FWaaS, ZTNA |

**Exam tip:** SASE = single converged, cloud-delivered architecture — not separately managed network and security stacks.

### AI/GenAI Security Risks
| Risk | Description | Primary Mitigation |
|---|---|---|
| Data leakage into models | Sensitive data exposed via prompts/training data or memorized in outputs | Classify/redact input data, filter outputs |
| Prompt injection | Malicious input overrides model instructions, causes leakage/unintended actions | Input validation, guardrails, least-privilege tool access for agents |
| Model supply chain risk | Tampered/poisoned third-party models, datasets, or plugins | Verify signatures/hashes, check provenance, scan for anomalies |
| Training data poisoning | Malicious samples injected into training set to manipulate model | Data provenance controls, anomaly detection in training pipeline |

### Securing ML Pipelines
- Validate integrity/provenance of datasets and pretrained models before ingestion.
- Apply access controls and versioning to training data and model artifacts.
- Monitor inference endpoints for abuse (prompt injection, extraction attacks).
- Apply least privilege to any tools/APIs an AI agent can invoke.

### Cross-Cutting Nature
Zero Trust, SASE, and AI/GenAI security are **not siloed** — they reinforce controls across IAM, network security, data security, and incident response. Expect exam questions linking Domain 12 concepts back to earlier domains rather than testing them in isolation.
