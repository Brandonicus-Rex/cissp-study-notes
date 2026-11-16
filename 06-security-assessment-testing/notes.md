# Domain 6: Security Assessment and Testing (12%)

## Design and validate assessment, test, and audit strategies

- **Internal:** within the organization. **External:** by an outside party, e.g., a customer assessing a vendor. **Third-party:** an independent auditor.
- Choose locations (on-prem, cloud, hybrid) and align with business goals and compliance requirements.

## Conduct security control testing

- **Vulnerability assessment:** identifies weaknesses (scanning). Doesn't exploit.
- **Penetration testing:** actively exploits vulnerabilities to prove impact.
  - **Phases:** planning (with **written authorization and rules of engagement**) → information gathering/discovery → vulnerability scanning → exploitation → reporting.
  - **Knowledge levels:**
    - **Zero knowledge** (black box / unknown environment)
    - **Partial knowledge** (gray box)
    - **Full knowledge** (white box / known environment)
  - **Team types:**
    - **Red team:** attackers.
    - **Blue team:** defenders.
    - **Purple team:** collaboration between red and blue.
    - **White team:** referees.
- **Log reviews.**
- **Synthetic transactions:** scripted tests that simulate user activity to check availability and performance.
- **Real user monitoring (RUM):** passive monitoring of actual users.
- **Code review and testing:**
  - **Static (SAST):** source code, without running it.
  - **Dynamic (DAST):** running application.
  - **Interactive (IAST).**
  - **Fuzzing:** sending random or malformed input. **Mutation (dumb)** fuzzing changes existing input; **generational (intelligent)** fuzzing builds input from a model of the format.
- **Misuse case testing:** tests how the system handles abuse.
- **Coverage analysis:** how much code or functionality the tests touch.
- **Interface testing:** APIs, user interfaces, physical interfaces.
- **Breach attack simulations (BAS):** automated, continuous attack simulation.
- **Compliance checks.**
- **Regression testing:** confirms changes didn't break existing functionality.

> **Exam tip:** The most important step before any penetration test is getting **written authorization from senior management**, along with agreed scope and rules of engagement.

## Collect security process data

- **Account management.**
- **Management review and approval.**
- **Key performance and risk indicators:**
  - **KPIs:** measure how well something is performing (past).
  - **KRIs:** warn of increasing risk (forward-looking).
- **Backup verification data:** test restores, not just backups.
- **Training and awareness.**
- **Disaster recovery (DR) and business continuity (BC).**

## Analyze test output and generate reports

- **Remediation.**
- **Exception handling:** documented risk acceptance when a finding can't be fixed.
- **Ethical disclosure:** responsible or coordinated disclosure of vulnerabilities to vendors.
- **CVSS** scoring to prioritize findings.

## Conduct or facilitate security audits

- **Internal audits:** independent from the area being audited.
- **External audits.**
- **Third-party audits.**
- **SOC reports (SSAE 18 / ISAE 3402):**

| Report | Audience | Content |
|--------|----------|---------|
| **SOC 1** | Auditors of the customer | Controls over **financial reporting** |
| **SOC 2** | Customers, under NDA | Controls for security, availability, processing integrity, confidentiality, privacy (Trust Services Criteria) |
| **SOC 3** | **Public** | Summary of SOC 2; seal of approval |

- **Type I:** controls are designed properly at **a point in time.**
- **Type II:** controls are operating effectively **over a period** (usually 6–12 months). Type II is stronger.
- **Location:** on-prem, cloud, hybrid.

> **Exam tip:** To verify a cloud vendor's security controls actually work over time, ask for a **SOC 2 Type II** report.

## Key terms

| Term | Definition |
|------|-----------|
| Vulnerability assessment | Finds weaknesses without exploiting them |
| Penetration test | Exploits weaknesses to prove impact |
| Black / gray / white box | Zero / partial / full knowledge testing |
| Red / blue / purple team | Attackers / defenders / collaboration |
| Synthetic transaction | Scripted simulated user activity |
| RUM | Real user monitoring |
| SAST / DAST | Static code analysis / testing a running app |
| Fuzzing | Sending random or malformed input |
| Misuse case | Testing how the system handles abuse |
| KPI / KRI | Performance measure / risk warning indicator |
| SOC 1 / 2 / 3 | Financial / detailed security / public summary reports |
| Type I / Type II | Point-in-time design / effectiveness over time |

## Questions to review

1. What is the key difference between a vulnerability assessment and a penetration test?
2. What must you have before starting a penetration test?
3. A tester gets network diagrams and source code before testing. What kind of test is this?
4. Which testing technique sends large amounts of random input to find crashes?
5. Which monitoring method uses scripts to simulate user activity?
6. Which indicator warns that risk is increasing?
7. Which SOC report is meant for public distribution?
8. Which SOC report type shows controls operating effectively over time?

<details>
<summary>Show answers</summary>

1. A vulnerability assessment **finds** weaknesses; a penetration test **exploits** them.
2. **Written authorization** (signed by senior management) with defined scope and rules of engagement.
3. A **white box / full knowledge** test.
4. **Fuzzing.**
5. **Synthetic transactions.**
6. A **KRI** (key risk indicator).
7. **SOC 3.**
8. **Type II.**

</details>
