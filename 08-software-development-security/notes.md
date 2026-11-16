# Domain 8: Software Development Security (10%)

## Integrate security in the software development life cycle (SDLC)

- **Development methodologies:**

| Methodology | Key traits |
|-------------|-----------|
| **Waterfall** | Sequential phases; hard to go back; good for stable requirements |
| **Agile** | Iterative sprints; customer collaboration; Scrum (product owner, scrum master, team) |
| **Spiral** | Iterative with **risk analysis** in each loop; good for large, risky projects |
| **Rapid application development (RAD)** | Fast prototyping |
| **DevOps** | Development and operations integrated; CI/CD |
| **DevSecOps** | Security built into DevOps ("shift left") |
| **Scaled Agile Framework (SAFe)** | Agile at enterprise scale |

- **Maturity models:**
  - **CMMI** (Capability Maturity Model Integration), 5 levels:
    1. Initial
    2. Managed/Repeatable
    3. Defined
    4. Quantitatively Managed
    5. Optimizing
  - **SAMM** (OWASP Software Assurance Maturity Model).
  - **BSIMM** (Building Security In Maturity Model): descriptive; based on real organizations.
- **Operation and maintenance.**
- **Change management.**
- **Integrated product team (IPT).**
- **Typical SDLC phases:**
  1. initiation/requirements
  2. design
  3. development
  4. testing
  5. deployment
  6. operations and maintenance
  7. disposal
  - Security should be included **from the start** (requirements phase).

> **Exam tip:** Security is cheapest and most effective when built in during the **requirements and design** phases, not bolted on later.

## Identify and apply security controls in software development ecosystems

- **Programming languages:** compiled vs interpreted; memory-safe languages (Rust, Go, Java) reduce buffer overflows.
- **Libraries:** third-party components bring vulnerabilities. Track them with **SCA** (software composition analysis) and an **SBOM.**
- **Tool sets.**
- **Integrated development environment (IDE).**
- **Runtime.**
- **Continuous integration and continuous delivery (CI/CD).**
- **Software configuration management (SCM):** version control.
- **Code repositories:** protect secrets; don't commit credentials.
- **Application security testing:**
  - **SAST:** static; white box; source code.
  - **DAST:** dynamic; black box; running app.
  - **IAST:** interactive; agent inside the running app.
  - **SCA:** third-party components.
  - **Fuzzing.**

## Assess the effectiveness of software security

- **Auditing and logging of changes.**
- **Risk analysis and mitigation.**

## Assess security impact of acquired software

- **Commercial off-the-shelf (COTS).**
- **Open source.**
- **Third-party.**
- **Managed services:** SaaS, IaaS, PaaS.
- **Escrow agreements:** a third party holds source code, which is released if the vendor goes out of business.
- **Vendor assessment:** security questionnaires, SOC reports, contract terms.

> **Exam tip:** **Source code escrow** protects you if a software vendor goes out of business or stops supporting the product.

## Define and apply secure coding guidelines and standards

- **Security weaknesses and vulnerabilities at the source-code level:**

| Vulnerability | Defense |
|---------------|---------|
| **Buffer overflow** | Bounds checking, memory-safe languages, ASLR, DEP/NX |
| **SQL injection** | **Parameterized queries / prepared statements**, input validation |
| **Cross-site scripting (XSS)** | Output encoding, input validation, CSP |
| **CSRF** | Anti-CSRF tokens, SameSite cookies |
| **Race condition / TOCTOU** | Locking, atomic operations |
| **Insecure direct object reference** | Server-side authorization checks |
| **Hardcoded credentials** | Secrets management |
| **Covert channels / backdoors / maintenance hooks** | Code review; remove before production |

- **Security of APIs:** authentication (OAuth, API keys), rate limiting, input validation, least privilege, **OWASP API Security Top 10.**
- **Secure coding practices:**
  - input validation (allow lists)
  - output encoding
  - error handling (no detailed errors to users)
  - least privilege
  - secure defaults
  - logging
- **Software-defined security:** policy as code.
- **Resources:** OWASP Top 10, OWASP ASVS, CWE/SANS Top 25, NIST SSDF (SP 800-218).
- **Database concepts:**
  - **ACID:** atomicity, consistency, isolation, durability.
  - **Concurrency control:** locking.
  - **Views:** restrict data visible to users.
  - **Aggregation / inference attacks.**
- **Object-oriented concepts:**
  - **encapsulation:** data hiding
  - **inheritance**
  - **polymorphism**
  - **cohesion:** high is good
  - **coupling:** low is good

> **Exam tip:** Good software design has **high cohesion** (modules do one thing well) and **low coupling** (modules are independent).

## Key terms

| Term | Definition |
|------|-----------|
| Waterfall / Agile / Spiral | Sequential / iterative sprints / risk-driven iterations |
| DevSecOps | Security integrated into DevOps ("shift left") |
| CMMI | Five-level capability maturity model |
| SAMM / BSIMM | Prescriptive / descriptive software security maturity models |
| SCA / SBOM | Third-party component analysis / bill of materials |
| SAST / DAST / IAST | Static / dynamic / interactive testing |
| Code escrow | Third party holds source code for the buyer |
| Buffer overflow | Writing past memory bounds |
| ASLR / DEP | Randomized memory layout / non-executable memory |
| Prepared statement | Parameterized query; stops SQLi |
| ACID | Atomicity, consistency, isolation, durability |
| Cohesion / coupling | Module focus (high is good) / interdependence (low is good) |

## Questions to review

1. Which development model includes risk analysis in each iteration?
2. When is the best time to introduce security into the SDLC?
3. What's the highest level of CMMI?
4. Which testing approach analyzes source code without running it?
5. How does a buyer protect itself if a software vendor goes out of business?
6. What is the most effective defense against SQL injection?
7. Which database property ensures a transaction either completes fully or not at all?
8. Good object-oriented design should have high ___ and low ___.

<details>
<summary>Show answers</summary>

1. **Spiral.**
2. During the **requirements (initiation) phase.**
3. Level 5, **Optimizing.**
4. **SAST** (static application security testing).
5. A **source code escrow** agreement.
6. **Parameterized queries / prepared statements.**
7. **Atomicity.**
8. High **cohesion**, low **coupling.**

</details>
