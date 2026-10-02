## Chapter 8: Domain 9: Data Security — Flashcards

| # | Front (Question) | Back (Answer) |
|---|-----------------|---------------|
| 1 | List the six phases of the CSA Data Security Lifecycle. | Create → Store → Use → Share → Archive → Destroy. Exam tip: each phase has distinct applicable controls (e.g., DLP applies heavily at Share, cryptographic erasure at Destroy). |
| 2 | Provider-managed keys: who controls the key? | The cloud provider generates, stores, and manages the key entirely. Lowest customer control, lowest operational overhead. Exam tip: default option for most managed encryption features. |
| 3 | BYOK — who generates the key and where is it stored? | Customer generates the key, but it is uploaded into and used from the provider's KMS/HSM. Provider retains some operational access. Exam tip: contrast with HYOK. |
| 4 | HYOK — defining characteristic? | Hold Your Own Key — key material never resides in the cloud provider's environment; provider calls out externally for crypto operations. Exam tip: highest customer control, highest operational complexity. |
| 5 | Tokenization vs Encryption — reversibility mechanism. | Tokenization: token has no mathematical relationship to original value; reversal requires the token vault. Encryption: ciphertext is reversible by anyone holding the correct key. Exam tip: tokenization commonly reduces PCI DSS scope. |
| 6 | Minimum TLS version recommended for data in transit (CCSK baseline)? | TLS 1.2 or higher (TLS 1.3 preferred). SSL and TLS 1.0/1.1 are deprecated/insecure. Exam tip: applies even to 'internal' VPC traffic under zero-trust guidance. |
| 7 | DLP — two main inspection approaches. | Content-aware (inspects actual data/patterns like regex for SSNs, PANs) and context-aware (inspects metadata — user, destination, time, channel). Exam tip: real deployments often combine both. |
| 8 | Which Data Security Lifecycle phase is most associated with DLP monitoring of outbound channels (email, USB, cloud sync)? | Share phase. Exam tip: distinguish from Store phase controls, which focus on at-rest encryption and access control. |
| 9 | Best practice for the Destroy phase in multi-tenant public cloud storage. | Cryptographic erasure — destroy the encryption keys protecting the data — since physical media sanitization isn't accessible to the customer. Exam tip: don't assume provider auto-wipes without verification. |
| 10 | Typical 4-tier data classification scheme (as used in CCSK examples). | Public → Internal → Confidential → Restricted. Labeling drives which encryption/DLP/access controls are required. Exam tip: higher tiers require stricter, layered controls. |
| 11 | Tokenization's main compliance benefit. | Reduces PCI DSS audit scope — tokens (not real PANs) exist in most systems; only the token vault holds actual cardholder data, minimizing the compliance footprint. |
| 12 | Key rotation + IAM scoping — why does the exam emphasize this for CMKs? | Limits blast radius: rotating keys reduces exposure window if compromised; scoping IAM policies restricts which identities can use a given key, containing damage from a single compromised credential. |
