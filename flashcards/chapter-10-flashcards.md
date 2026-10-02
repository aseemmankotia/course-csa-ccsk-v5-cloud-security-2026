## Chapter 10: Domain 11: Incident Response and Resilience — Flashcards

| # | Front (Question) | Back (Answer) |
|---|-----------------|---------------|
| 1 | Order of phases in the cloud incident response lifecycle (PICERL)? | Preparation → Detection → Containment → Eradication → Recovery → Lessons Learned. Exam tip: CCSK tests this exact sequence. |
| 2 | Biggest forensic challenge unique to a compromised IaaS VM? | Volatile evidence (RAM) is lost on shutdown/reboot — must snapshot the instance/memory before isolating or powering off. |
| 3 | How to preserve volatile evidence during a cloud incident? | Take a live snapshot/memory dump via the provider's API before isolating or terminating the instance. Never power off first. |
| 4 | Who owns incident response for a hypervisor-level compromise in IaaS? | The cloud provider — it's below the customer's line of visibility. Customer owns IR within guest OS, apps, and data. |
| 5 | SaaS vs IaaS: who carries more IR responsibility, customer or provider? | SaaS — provider handles most infrastructure/app-layer IR. Customer still owns account-level and data-misuse incidents in both models. |
| 6 | Main jurisdiction challenge in cloud forensics? | Data may reside across multiple countries; legal processes (subpoenas, MLATs) are needed to compel provider cooperation across borders, slowing investigations. |
| 7 | RTO definition | Recovery Time Objective — max acceptable time to restore service after an outage. Exam tip: measures downtime tolerance. |
| 8 | RPO definition | Recovery Point Objective — max acceptable data loss, measured in time since last recovery point. Exam tip: 1hr RPO ≈ hourly backups. |
| 9 | Backups taken every 6 hours — what is the effective RPO? | Up to 6 hours of potential data loss. RPO equals the worst-case interval between recovery points. |
| 10 | Multi-region active-active vs backup/restore for DR — which gives lowest RTO/RPO? | Multi-region active-active — near-continuous replication and failover. Backup/restore is cheapest but has the highest RTO/RPO. |
| 11 | Best practice to validate a DR plan works? | Regularly scheduled failover/game-day testing — a written plan alone does not prove operational readiness. |
| 12 | BC vs DR — what's the difference? | Business Continuity = keeping critical business functions running overall; Disaster Recovery = restoring IT systems/data after disruption. DR is a subset of BC. |
