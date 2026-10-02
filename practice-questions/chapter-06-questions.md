## Chapter 6: Domain 7: Infrastructure and Networking — Practice Questions

**Q1.** A company runs multiple application workloads on the same subnet in their cloud VPC. Security team is concerned about lateral movement if one workload is compromised, and traditional subnet-level firewall rules are viewed as insufficient granularity. Which approach BEST addresses this requirement?

A) Implement additional NACL rules at the subnet level
B) Move the workloads into different traditional VLANs
C) Increase logging on the perimeter firewall
D) Deploy micro-segmentation with workload-level policy enforcement

<details>
<summary>Answer</summary>

**Correct: D**

Micro-segmentation enforces policy at the individual workload level regardless of subnet placement, directly limiting lateral movement between workloads even within the same subnet.

**Why the others are wrong:**
- NACLs operate at the subnet level and cannot provide per-workload granularity; traffic between hosts within the same subnet may not traverse them.
- VLANs are a traditional segmentation mechanism with the same subnet-level granularity limitation, and cloud VPCs don't map directly to physical VLANs.
- Increased logging is detective, not preventive, and does not stop lateral movement.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** Which statement correctly differentiates stateful and stateless traffic filtering in cloud network security?

A) Stateless filtering automatically permits return traffic for established connections
B) Stateful filtering requires explicit rules for both inbound and outbound directions
C) Stateless and stateful filtering provide identical security guarantees
D) Stateful filtering tracks connection state and automatically allows valid return traffic

<details>
<summary>Answer</summary>

**Correct: D**

Stateful filters (e.g., security groups) track connection state and automatically permit the associated return traffic once the initial session is allowed.

**Why the others are wrong:**
- This describes stateful behavior, not stateless — reversed.
- This describes stateless behavior (both directions must be explicit), not stateful.
- The two models have materially different behaviors and administrative overhead; they are not equivalent.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** A company needs to connect their on-premises data center to their cloud environment with predictable low-latency bandwidth for a large-scale database replication workload, and wants to minimize exposure to the public internet. Which connectivity option BEST meets this need?

A) Site-to-site VPN over the public internet
B) Point-to-site VPN for individual administrators
C) Dedicated private connectivity (e.g., a direct interconnect link)
D) Public internet access with TLS encryption only

<details>
<summary>Answer</summary>

**Correct: C**

Dedicated private connectivity provides consistent bandwidth and latency while bypassing the public internet entirely, matching the stated requirements.

**Why the others are wrong:**
- A VPN still traverses the public internet, introducing variable latency even though the traffic is encrypted.
- Point-to-site VPN is designed for individual client-to-network connections, not bulk network-to-network data replication.
- Encryption alone does not provide dedicated bandwidth or reduce reliance on shared public internet paths.

</details>

---

**Q4.** An administrator configures a stateless network ACL to allow inbound HTTPS traffic (port 443) from the internet to a web server subnet. Which additional configuration is required for the return traffic to function correctly?

A) An explicit outbound rule allowing the ephemeral port range back to the originating source
B) Nothing further — stateless filters automatically permit return traffic
C) A corresponding security group change only; the NACL doesn't need further updates
D) Enable stateful mode on the NACL configuration

<details>
<summary>Answer</summary>

**Correct: A**

Because NACLs are stateless, both the inbound rule and an explicit outbound rule (typically allowing the ephemeral port range) are required for return traffic to pass.

**Why the others are wrong:**
- This contradicts the definition of stateless filtering — nothing is automatically permitted.
- The security group is a separate, typically stateful control; the stateless NACL still independently needs its own outbound rule.
- Stateless ACLs in this model do not have a toggleable 'stateful mode' — this conflates two distinct filtering concepts.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q5.** During an architecture review, a security team identifies that their SDN controller manages all virtual network routing and policy decisions for the entire cloud environment. Which risk should be prioritized based on this finding?

A) Increased hardware costs from centralized management
B) A single compromise of the SDN controller could allow an attacker to reprogram network flows across the entire environment
C) SDN controllers cannot support micro-segmentation
D) SDN removes the need for any network security controls

<details>
<summary>Answer</summary>

**Correct: B**

SDN centralizes the control plane; compromising the controller gives an attacker broad, programmatic control over network flows across the environment, making it a high-value target.

**Why the others are wrong:**
- Hardware cost is not a security risk and is out of scope for this concern.
- SDN often enables and simplifies micro-segmentation rather than preventing it.
- SDN changes how controls are implemented but does not eliminate the need for network security controls.

</details>

---

**Q6.** An organization must isolate PCI DSS in-scope workloads from all other workloads even when they reside within the same virtual subnet due to auto-scaling constraints. Which control BEST satisfies this requirement?

A) Traditional VLAN-based network segmentation
B) Micro-segmentation with identity/workload-based policy enforcement
C) Perimeter firewall rules only
D) Increasing the subnet CIDR block size

<details>
<summary>Answer</summary>

**Correct: B**

Workload/identity-based enforcement travels with the workload regardless of dynamic IP assignment from auto-scaling, satisfying isolation requirements independent of subnet placement.

**Why the others are wrong:**
- VLAN segmentation operates at the network/subnet level and cannot isolate workloads sharing the same subnet.
- A perimeter firewall only controls north-south traffic and does not address east-west traffic between workloads in the same subnet.
- Changing the CIDR block size does not create isolation between workloads and is unrelated to the requirement.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** Which default security group configuration is recommended as a best practice baseline in cloud environments?

A) Deny all inbound and outbound traffic by default, then explicitly allow only required ports/protocols/sources
B) Allow all inbound and outbound traffic by default, then monitor logs for anomalies
C) Allow all inbound traffic, deny all outbound traffic
D) Configure security groups only for production environments

<details>
<summary>Answer</summary>

**Correct: A**

Default-deny with explicit allow rules reflects least-privilege network access, the recommended baseline for security groups.

**Why the others are wrong:**
- Allow-all defeats the purpose of the security group and relies solely on detective monitoring rather than prevention.
- Allowing all inbound traffic still exposes services broadly and violates least privilege, regardless of outbound posture.
- Non-production environments (dev/test) are common attack entry points and also require least-privilege network controls.

</details>

---

**Q8.** A cloud architect is designing security controls to protect both the compute and network planes for a multi-tier application. Which approach reflects the BEST practice for end-to-end infrastructure security?

A) Layer host-based controls, workload-level micro-segmentation, security zones, and secure connectivity controls together
B) Rely solely on the cloud provider's default network security group settings
C) Implement a single perimeter firewall and consider the environment secured
D) Use only agent-based endpoint protection on compute instances

<details>
<summary>Answer</summary>

**Correct: A**

End-to-end infrastructure security requires layered, defense-in-depth controls spanning the compute plane (host-based/agent controls) and network plane (micro-segmentation, security zones, secure connectivity).

**Why the others are wrong:**
- Relying only on provider defaults does not address workload-level isolation or east-west traffic risks.
- A perimeter-only model ignores lateral (east-west) traffic and cloud shared-responsibility considerations.
- Host-only endpoint protection ignores network-layer segmentation and secure connectivity requirements.

</details>

---

