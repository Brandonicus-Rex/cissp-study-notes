# Domain 2: Asset Security (10%)

## Identify and classify information and assets

- **Data classification:** based on value, sensitivity and the impact of disclosure.

| Government / military | Commercial / private |
|-----------------------|----------------------|
| Top Secret (exceptionally grave damage) | Confidential / Proprietary |
| Secret (serious damage) | Private |
| Confidential (damage) | Sensitive |
| Unclassified (CUI / sensitive but unclassified) | Public |

- **Classification process:**
  1. Identify the data owner.
  2. Set criteria.
  3. Classify.
  4. Label.
  5. Apply controls.
  6. Review periodically.
  7. Declassify when appropriate.
- **Asset classification:** hardware and systems take the classification of the most sensitive data they hold.

## Establish information and asset handling requirements

- **Marking and labeling:** human-readable labels plus system metadata.
- **Handling, storage and transport:** based on classification, e.g., encryption and approved couriers.

## Provision information and assets securely

- **Information and asset ownership.**
- **Asset inventory:** tangible and intangible assets. Asset management includes configuration and change management.

## Manage data life cycle

- **Data roles:**

| Role | Responsibility |
|------|---------------|
| **Data owner / controller** | Accountable; classifies data and sets protection requirements |
| **Data custodian** | Day-to-day protection: backups, controls |
| **Data processor** | Processes data on behalf of the controller (GDPR) |
| **Data steward** | Data quality and business use |
| **Data subject** | Person the personal data is about |
| **Data administrator** | Grants access per the owner's direction |

- **Data life cycle:** create/collect → store → use → share → archive → destroy.
- **Data collection:** collect only what you need (**data minimization**).
- **Data location:** data residency and sovereignty.
- **Data maintenance.**
- **Data retention:** keep as long as legally or business-required, no longer.
- **Data remanence:** residual data left after deletion.
- **Data destruction** (from weakest to strongest):

| Method | Notes |
|--------|-------|
| **Erasing / deleting** | Only removes pointers; data is recoverable |
| **Clearing (overwriting)** | Protects against casual recovery; media can be reused |
| **Purging** | Stronger: degaussing (magnetic media) or crypto-erase; protects against lab recovery |
| **Destruction** | Shredding, disintegration, pulverizing, incineration; most secure |

- **SSDs:** degaussing **doesn't work.** Use crypto-erase (cryptographic erasure) or physical destruction.
- **Media sanitization guidance:** NIST SP 800-88.

> **Exam tip:** Degaussing doesn't work on **SSDs** or optical media. For SSDs, the answer is **cryptographic erasure** or **physical destruction.**

## Ensure appropriate asset retention

- **End of life (EOL)** and **end of support (EOS):** plan replacement, because security patches stop.
- Retention schedules should follow legal, regulatory and business requirements.

## Determine data security controls and compliance requirements

- **Data states:**
  - **At rest:** full-disk, file and database encryption.
  - **In transit:** TLS, IPsec, VPN.
  - **In use:** secure enclaves, memory protection, homomorphic encryption.
- **Scoping and tailoring:**
  - **Scoping:** choosing which baseline controls apply to your environment.
  - **Tailoring:** modifying controls to fit the organization.
- **Standards selection:** NIST SP 800-53, ISO 27002, CIS Controls, PCI DSS.
- **Data protection methods:**
  - **DLP:** data loss prevention, at network, endpoint and cloud.
  - **DRM:** digital rights management.
  - **CASB:** cloud access security broker.
  - **Tokenization.**
  - **Masking.**
  - **Anonymization:** irreversible.
  - **Pseudonymization:** reversible with a key.

> **Exam tip:** **Anonymized** data falls outside GDPR's scope; **pseudonymized** data is still personal data under GDPR because it can be re-identified.

## Key terms

| Term | Definition |
|------|-----------|
| Data classification | Labeling data by sensitivity and value |
| Data owner | Accountable for classification and protection |
| Data custodian | Implements day-to-day protection |
| Data processor | Processes data on the controller's behalf |
| Data remanence | Residual data after deletion |
| Clearing / purging / destruction | Overwrite / degauss or crypto-erase / physically destroy |
| Crypto-erase | Destroying encryption keys to make data unreadable |
| Scoping / tailoring | Selecting applicable controls / adjusting them |
| DLP / DRM / CASB | Data loss prevention / rights management / cloud broker |
| Anonymization / pseudonymization | Irreversible / reversible de-identification |
| Data minimization | Collecting only what's needed |

## Questions to review

1. Who is responsible for deciding the classification of a data set?
2. Which government classification level applies when disclosure would cause "exceptionally grave damage"?
3. What is data remanence?
4. Which sanitization method is ineffective on SSDs?
5. What's the best way to sanitize an SSD that will be reused?
6. Removing controls from a baseline that don't apply to your environment is called what?
7. Which de-identification method can be reversed with a key?
8. A server stores both public and Secret data. What classification does the server get?

<details>
<summary>Show answers</summary>

1. The **data owner.**
2. **Top Secret.**
3. **Residual data** that remains after deletion or erasure.
4. **Degaussing.**
5. **Cryptographic erasure** (crypto-erase).
6. **Scoping.**
7. **Pseudonymization.**
8. **Secret** (the highest classification of data it holds).

</details>
