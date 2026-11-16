# Domain 7: Security Operations (13%)

## Understand and comply with investigations

- **Evidence collection and handling:**
  - **chain of custody:** who, what, when, where, why
  - **order of volatility:** registers/cache → RAM → swap → disk → remote logs → archives
- **Evidence types:**
  - **real:** physical
  - **documentary**
  - **testimonial**
  - **demonstrative**
- **Admissibility:** relevant, reliable, legally obtained. **Best evidence rule** (originals preferred), **hearsay rule.**
- **Reporting and documentation.**
- **Investigative techniques:** interviewing, forensic imaging (work on a **bit-for-bit copy**, verify with **hashes**).
- **Digital forensics tools, tactics and procedures:** write blockers, imaging tools.
- **Artifacts:** computer, network, mobile device.
- **Locard's exchange principle:** every contact leaves a trace.

> **Exam tip:** Never analyze original evidence. Make a **forensic image**, use a **write blocker**, and **hash** both to prove integrity.

## Conduct logging and monitoring activities

- **Intrusion detection and prevention (IDS/IPS):** network or host; signature, anomaly or behavior-based.
- **SIEM.**
- **Continuous monitoring.**
- **Egress monitoring:** DLP, detecting exfiltration and steganography.
- **Log management:** centralized, protected, time-synchronized (NTP), retained.
- **Threat intelligence:** threat feeds, threat hunting.
- **User and entity behavior analytics (UEBA).**

## Perform configuration management

- **Provisioning**, **baselining** and **automation** (IaC).
- **Configuration management database (CMDB).**

## Apply foundational security operations concepts

- **Need to know / least privilege.**
- **Separation of duties (SoD) and responsibilities.**
- **Privileged account management.**
- **Job rotation.**
- **Service level agreements (SLAs).**
- **Two-person control:** two people required to perform a task together. **Split knowledge:** no one person holds the whole secret.

## Apply resource protection

- **Media management:** labeling, handling, storage, destruction.
- **Media protection techniques.**
- **Data at rest and data in transit protection.**

## Conduct incident management

- **ISC2 incident management steps:**
  1. **Detection.**
  2. **Response:** activate the team.
  3. **Mitigation:** containment.
  4. **Reporting.**
  5. **Recovery.**
  6. **Remediation:** root cause.
  7. **Lessons learned.**
- NIST SP 800-61 equivalent: preparation → detection and analysis → containment, eradication and recovery → post-incident activity.

> **Exam tip:** Containment (mitigation) comes before remediation. Stop the damage first, then fix the root cause.

## Operate and maintain detection and preventative measures

- **Firewalls:** NGFW, WAF.
- **IDS/IPS.**
- **Allow lists and deny lists.**
- **Third-party provided security services:** MSSP, MDR.
- **Sandboxing.**
- **Honeypots/honeynets:** enticement is legal; **entrapment** is not.
- **Anti-malware.**
- **Machine learning and AI-based tools.**

## Implement and support patch and vulnerability management

- Inventory → identify vulnerabilities → prioritize (CVSS plus business context) → test patches → deploy → verify.
- Have an emergency patching process for critical vulnerabilities.

## Understand and participate in change management

- **Request → review/impact analysis → approve (change advisory board) → test → implement → document → review.** Include a rollback plan.

## Implement recovery strategies

- **Backup types:**

| Type | Backs up | Clears archive bit? | Restore needs |
|------|----------|---------------------|---------------|
| **Full** | Everything | Yes | Last full |
| **Incremental** | Changes since last backup of **any** kind | Yes | Last full + **all** incrementals |
| **Differential** | Changes since last **full** | No | Last full + **last** differential |

- **Storage strategies:** offsite, cloud, electronic vaulting (bulk transfer), remote journaling (transaction logs), **3-2-1 rule** (3 copies, 2 media types, 1 offsite).
- **Recovery site strategies:**

| Site | Readiness | Cost |
|------|-----------|------|
| **Hot** | Minutes to hours; fully equipped with current data | Highest |
| **Warm** | Hours to days; equipment but not current data | Medium |
| **Cold** | Days to weeks; space and power only | Lowest |
| **Mobile** | Trailer-based | Varies |
| **Reciprocal agreement** | Another organization hosts you | Low, but hard to enforce |
| **Cloud** | Scalable, on demand | Pay as you go |

- **Multiple processing sites.**
- **System resilience, high availability (HA), quality of service (QoS) and fault tolerance:** RAID, clustering, redundancy.
  - **RAID 0:** striping; no redundancy.
  - **RAID 1:** mirroring.
  - **RAID 5:** striping with parity; survives one disk loss.
  - **RAID 6:** double parity; survives two.
  - **RAID 10:** mirror plus stripe.

## Implement and test disaster recovery processes

- **Response**, **personnel**, **communications** (including media), **assessment**, **restoration**, **training and awareness**, **lessons learned.**
- **DRP test types**, from least to most disruptive:
  1. **Read-through / checklist:** review the plan.
  2. **Walkthrough / tabletop:** team discusses a scenario.
  3. **Simulation:** practice a scenario without moving operations.
  4. **Parallel:** recovery site runs alongside production.
  5. **Full interruption:** production shut down and moved to the recovery site. Most disruptive and risky.

> **Exam tip:** A **parallel test** activates the recovery site **without** stopping production. **Full interruption** is the only test that stops production; it needs senior management approval.

## Participate in business continuity planning and exercises

- Keep the BCP current and test regularly.

## Implement and manage physical security

- **Perimeter:** fences, gates, lighting, guards, bollards.
- **Internal security:** badges, mantraps, locks, escorts, CCTV.

## Address personnel safety and security concerns

- **Travel security.**
- **Security training and awareness:** e.g., insider threat, social media impacts, two-factor authentication fatigue.
- **Emergency management.**
- **Duress:** duress codes, panic buttons.
- **Life safety always comes first.**

## Key terms

| Term | Definition |
|------|-----------|
| Chain of custody | Record of evidence handling |
| Order of volatility | Collect most volatile evidence first |
| Best evidence rule | Original evidence preferred |
| Write blocker | Prevents changes to evidence media |
| Egress monitoring | Watching outbound traffic for exfiltration |
| Two-person control / split knowledge | Two people required / no one holds the whole secret |
| Enticement / entrapment | Legal lure / illegal inducement |
| Full / incremental / differential backup | All data / since any backup / since last full |
| Electronic vaulting / remote journaling | Bulk backup transfer / transaction log transfer |
| Hot / warm / cold site | Recovery site readiness levels |
| RAID 5 / RAID 6 | Single parity / double parity |
| Parallel / full interruption test | Recovery site alongside / instead of production |

## Questions to review

1. What should you collect first during a forensic investigation: RAM or the hard disk?
2. How do you prove a forensic image matches the original drive?
3. Placing a honeypot to observe attackers is legal. What would make it illegal?
4. Which backup type requires the last full backup plus all subsequent backups to restore?
5. Which backup type doesn't clear the archive bit?
6. Which RAID level can survive two simultaneous disk failures?
7. Which DR test runs the recovery site without stopping production?
8. What's the top priority in any emergency?

<details>
<summary>Show answers</summary>

1. **RAM** (more volatile).
2. **Compare hashes** of the image and the original.
3. **Entrapment** (inducing someone to commit a crime they otherwise wouldn't).
4. **Incremental.**
5. **Differential.**
6. **RAID 6.**
7. A **parallel test.**
8. **Life safety** (protecting people).

</details>
