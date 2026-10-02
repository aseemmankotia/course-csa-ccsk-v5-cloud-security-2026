## Domain 7 Cheat Sheet: Infrastructure and Networking (9%)

### Segmentation vs Micro-Segmentation
| Aspect | Traditional Segmentation | Micro-Segmentation |
|---|---|---|
| Enforcement point | Network/subnet (VLAN, perimeter FW) | Individual workload/host |
| Granularity | Coarse (whole segment) | Fine (per-workload) |
| Handles same-subnet lateral movement? | No | Yes |
| Common mechanism | VLANs, subnet ACLs | Hypervisor/agent policy, identity-based rules |
| Exam trap | Picking VLAN/subnet answer for workload-level isolation requirement | — |

### Stateful vs Stateless Filtering
| Aspect | Stateful (e.g., Security Group) | Stateless (e.g., NACL) |
|---|---|---|
| Tracks connection state | Yes | No |
| Return traffic | Auto-allowed | Requires explicit rule (both directions) |
| Typical scope | Instance/interface level | Subnet level |
| Exam trap | Forgetting outbound ephemeral port rule for stateless ACL | — |

### SDN Security Implications
- SDN separates **control plane** (policy/routing decisions) from **data plane** (packet forwarding).
- Enables centralized, API-driven, programmable network security.
- **Risk**: SDN controller = single high-value target; compromise = network-wide reprogramming.
- Exam tip: prioritize protecting the controller/control-plane API over individual devices.

### Secure Connectivity Patterns
| Pattern | Use Case | Traverses Public Internet? |
|---|---|---|
| Site-to-site VPN | Network-to-network (on-prem ↔ cloud) | Yes (encrypted) |
| Point-to-site VPN | Single client-to-network | Yes (encrypted) |
| Dedicated private connectivity | Predictable bandwidth/latency, reduced exposure | No |

- IPsec/IKE uses **UDP 500** (control channel) and **UDP 4500** (NAT-T).

### Security Zones
- Logical grouping by trust level (e.g., DMZ, app tier, data tier).
- Controlled connectivity points enforce policy between zones.
- Map zones to subnets/VPCs with explicit ingress/egress rules.

### Default Baseline Practices
- Default-deny inbound AND outbound on security groups/NACLs.
- Explicitly allow only required ports/protocols/sources — least privilege for network rules.
- Layer host controls + network controls + secure connectivity = defense in depth across compute and network planes.

### Common Exam Traps
1. Choosing VLAN/subnet-level answers when the scenario requires workload-level (micro-segmentation) isolation.
2. Confusing stateful (auto return traffic) with stateless (explicit both-direction rules).
3. Assuming SDN removes the need for security controls — it changes *how* controls are applied, not *whether* they're needed.
