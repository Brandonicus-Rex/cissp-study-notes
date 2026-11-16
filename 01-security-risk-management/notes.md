# Domain 1: Security and Risk Management (16%)

## Professional ethics

- **ISC2 Code of Ethics canons, in priority order:**
  1. Protect society, the common good, necessary public trust and confidence, and the infrastructure.
  2. Act honorably, honestly, justly, responsibly and legally.
  3. Provide diligent and competent service to principals.
  4. Advance and protect the profession.
- Organizational codes of ethics also apply.

> **Exam tip:** When canons conflict, the **higher canon wins**. Protecting society beats serving your employer.

## Security concepts and governance

- **CIA triad** plus **authenticity** and **non-repudiation.** The opposite is **DAD:** disclosure, alteration, destruction.
- **Security governance:**
  - aligns security with business strategy, goals, mission and objectives
  - organizational processes: acquisitions, divestitures, governance committees
  - roles and responsibilities
  - control frameworks: **ISO 27001/27002**, **NIST CSF**, **NIST SP 800-53**, **COBIT**, **SABSA**, **PCI DSS**
- **Due care vs due diligence:**
  - **Due care:** doing what a reasonable person would do; acting responsibly. "Doing the right thing."
  - **Due diligence:** investigating and verifying, such as assessments and audits. "Knowing it's being done right."
- **Senior management** is ultimately accountable for security.

| Role | Responsibility |
|------|---------------|
| **Senior management** | Ultimately accountable; approves policy |
| **Data owner** | Classifies data, decides access (a business role) |
| **Data custodian** | Implements controls day to day (often IT) |
| **Security professional** | Designs and implements the security program |
| **User** | Follows policy |
| **Auditor** | Independently verifies controls |

> **Exam tip:** CISSP wants a **manager's mindset**. The right answer usually aligns with business goals, involves senior management and protects people first.

## Compliance and legal issues

- **Legal systems:** civil (code) law, common law, religious law, customary law.
- **Law categories:** criminal, civil (tort), administrative/regulatory.
- **Intellectual property:**
  - **Copyright:** creative works; author's life + 70 years.
  - **Trademark:** brand identifiers.
  - **Patent:** inventions; about 20 years.
  - **Trade secret:** protected by NDAs and confidentiality.
  - **Licensing.**
- **Privacy:**
  - **GDPR:** EU. Lawful basis, data subject rights, 72-hour breach notification.
  - **CCPA/CPRA:** California.
  - **HIPAA:** U.S. health data.
  - **GLBA:** U.S. financial institutions.
  - **SOX:** financial reporting.
  - **PIPEDA:** Canada.
  - **OECD privacy principles.**
- **Transborder data flow**, **import/export controls** (ITAR, EAR, Wassenaar Arrangement), **data breaches.**
- **Investigation types:**
  - administrative
  - criminal (beyond a reasonable doubt)
  - civil (preponderance of evidence)
  - regulatory
  - industry standards

## Policies, standards, procedures, and guidelines

| Document | Nature |
|----------|--------|
| **Policy** | High-level management statement of intent; mandatory |
| **Standard** | Mandatory specific requirements (e.g., AES-256) |
| **Baseline** | Minimum security configuration |
| **Procedure** | Step-by-step instructions; mandatory |
| **Guideline** | Recommended; optional |

## Business continuity

- **BCP:** keeps critical business functions running during a disruption.
- **Steps:**
  1. Project scope and planning.
  2. **Business impact analysis (BIA).**
  3. Continuity planning.
  4. Approval and implementation.
- **BIA metrics:**
  - **MTD:** maximum tolerable downtime.
  - **RTO:** recovery time objective; must be ≤ MTD.
  - **RPO:** maximum acceptable data loss.
  - **WRT:** work recovery time. **RTO + WRT ≤ MTD.**

## Personnel security

- **Candidate screening:** background checks, references, education verification.
- **Employment agreements:** NDAs, acceptable use, non-compete.
- **Onboarding, transfers and termination:** remove access promptly; escort out if hostile.
- **Vendor, consultant and contractor controls.**
- **Administrative controls:**
  - **Separation of duties:** no one person controls a whole critical process.
  - **Job rotation:** detects fraud; provides cross-training.
  - **Mandatory vacation:** uncovers fraud.
  - **Least privilege.**
  - **Need to know.**

## Risk management

- **Terms:**
  - **Asset.**
  - **Threat.**
  - **Vulnerability.**
  - **Exposure.**
  - **Risk** = threat × vulnerability (× impact).
  - **Safeguard / countermeasure.**
- **Quantitative analysis:**
  - **SLE** = AV × EF.
  - **ALE** = SLE × ARO.
  - **Countermeasure value** = ALE before − ALE after − annual cost of the countermeasure.
- **Qualitative analysis:** scenarios, Delphi technique, probability/impact matrix.
- **Risk responses:**
  - **mitigate/reduce**
  - **transfer/share** (insurance)
  - **avoid**
  - **accept**
  - **Never ignore/reject.**
- **Inherent risk** vs **residual risk** (what remains after controls). **Total risk** vs **controls gap.**
- **Control types:** preventive, detective, corrective, deterrent, recovery, directive, compensating.
- **Control categories:** administrative (managerial), technical (logical), physical.
- **Frameworks:** **NIST RMF (SP 800-37)** — prepare, categorize, select, implement, assess, authorize, monitor. ISO 31000, ISO 27005, COSO.
- **Supply chain risk management (SCRM):** product tampering, counterfeits, implants; **SBOM** (software bill of materials); third-party assessments and audits (SOC reports).

> **Exam tip:** Example: a $200,000 asset with a 25% exposure factor gives SLE $50,000. With ARO 0.2, ALE is $10,000. A control costing more than $10,000 a year to remove that risk isn't cost-justified.

## Threat modeling

- **STRIDE (Microsoft):**
  - **S**poofing
  - **T**ampering
  - **R**epudiation
  - **I**nformation disclosure
  - **D**enial of service
  - **E**levation of privilege
- **PASTA:** risk-centric, seven stages.
- **DREAD:** damage, reproducibility, exploitability, affected users, discoverability.
- **VAST**, **attack trees.**

## Security awareness, education, and training

- **Awareness:** recognize threats. **Training:** teach skills. **Education:** deeper understanding.
- **Methods:** social engineering simulations, phishing tests, gamification, security champions.
- Review content regularly and measure effectiveness.

## Key terms

| Term | Definition |
|------|-----------|
| ISC2 Code of Ethics | Four canons; higher canon wins in conflicts |
| Due care / due diligence | Acting responsibly / verifying |
| Data owner / custodian | Classifies and decides access / implements controls |
| GDPR | EU privacy regulation with 72-hour breach notice |
| Policy / standard / procedure / guideline | Intent / mandatory spec / steps / recommendation |
| MTD / RTO / RPO / WRT | Downtime limit / recovery time / data loss / work recovery |
| Separation of duties | Splits critical tasks between people |
| SLE / ALE | AV × EF / SLE × ARO |
| Residual risk | Risk remaining after controls |
| NIST RMF | Seven-step risk management framework |
| SBOM | Software bill of materials |
| STRIDE | Microsoft threat modeling categories |

## Questions to review

1. Which ISC2 canon takes priority above all others?
2. A company regularly audits its vendors' security. Is this due care or due diligence?
3. Who is ultimately accountable for an organization's security?
4. Which document is mandatory and gives step-by-step instructions?
5. RTO plus WRT must not exceed what?
6. An asset worth $100,000 has an EF of 40% and an ARO of 0.5. What is the ALE?
7. Which administrative control helps detect fraud by requiring employees to take time off?
8. In STRIDE, which threat does a digital signature mainly address?

<details>
<summary>Show answers</summary>

1. **Protect society, the common good, necessary public trust and confidence, and the infrastructure.**
2. **Due diligence.**
3. **Senior management.**
4. A **procedure.**
5. The **MTD** (maximum tolerable downtime).
6. SLE = $40,000; ALE = **$20,000.**
7. **Mandatory vacation.**
8. **Repudiation** (also tampering).

</details>
