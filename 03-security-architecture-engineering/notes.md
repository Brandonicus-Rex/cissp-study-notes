# Domain 3: Security Architecture and Engineering (13%)

## Secure design principles

- **Threat modeling.**
- **Least privilege.**
- **Defense in depth.**
- **Secure defaults.**
- **Fail securely:** fail-safe (protects people) vs fail-secure (protects assets).
- **Separation of duties (SoD).**
- **Keep it simple (KISS).**
- **Zero Trust:** never trust, always verify.
- **Privacy by design:** seven principles, including proactive not reactive and privacy as the default.
- **Trust but verify.**
- **Shared responsibility.**
- **Secure access service edge (SASE).**

> **Exam tip:** **Fail-safe** = doors unlock in a fire, because **people come first.** **Fail-secure** = doors stay locked to protect assets. Life safety always wins on the CISSP.

## Security models

| Model | Focus | Rules |
|-------|-------|-------|
| **Bell-LaPadula** | **Confidentiality** | **No read up** (simple security property); **no write down** (* star property); strong star property |
| **Biba** | **Integrity** | **No read down** (simple integrity); **no write up** (* integrity) |
| **Clark-Wilson** | Integrity (commercial) | Access through **well-formed transactions** (programs); separation of duties; subject–program–object triple |
| **Brewer-Nash (Chinese Wall)** | Conflict of interest | Access changes dynamically based on what you've already accessed |
| **Lattice-based** | Classification levels | Upper and lower bounds of access |
| **Take-Grant** | Rights transfer | Take, grant, create, remove rights |
| **Graham-Denning** | Secure creation and deletion of subjects and objects | Eight protection rules |
| **Harrison-Ruzzo-Ullman (HRU)** | Changing access rights | Builds on Graham-Denning |

> **Exam tip:** **Bell-LaPadula** = confidentiality (military): "no read up, no write down." **Biba** = integrity: "no read down, no write up." They're opposites.

## Controls based on system security requirements

- **Evaluation criteria:**
  - **Common Criteria (ISO/IEC 15408).**
  - **Protection Profile (PP):** customer's security requirements.
  - **Security Target (ST):** vendor's claims.
  - **Target of Evaluation (TOE):** the product being evaluated.
  - **Evaluation Assurance Levels EAL1–EAL7:** EAL1 = functionally tested; EAL7 = formally verified design and tested.
- **Certification and accreditation:**
  - **Certification:** technical evaluation.
  - **Accreditation / authorization (ATO):** management's formal acceptance of risk.

## Security capabilities of information systems

- **Memory protection.**
- **Trusted Platform Module (TPM).**
- **Hardware security module (HSM).**
- **Secure enclaves.**
- **Encryption/decryption.**
- **Trusted computing base (TCB):** all protection mechanisms in a system.
- **Reference monitor:** the concept of mediating all access. Must be tamperproof, always invoked and verifiable.
- **Security kernel:** the implementation of the reference monitor.
- **Processor states:** supervisor (kernel) vs problem (user) mode. **Protection rings:** ring 0 = kernel.

## Vulnerabilities of security architectures

- **Client-based systems.**
- **Server-based systems.**
- **Database systems:**
  - **aggregation:** combining less-sensitive data to reveal sensitive info
  - **inference:** deducing sensitive info
  - **polyinstantiation:** multiple versions of a record at different classification levels to prevent inference
- **Cryptographic systems.**
- **Industrial control systems (ICS):** SCADA, PLCs.
- **Cloud-based systems:** SaaS, PaaS, IaaS.
- **Distributed systems.**
- **Internet of Things (IoT).**
- **Microservices.**
- **Containerization.**
- **Serverless.**
- **Embedded systems.**
- **High-performance computing.**
- **Edge and fog computing.**
- **Virtualized systems:** VM escape, VM sprawl, hypervisor types. **Type 1** = bare metal; **Type 2** = hosted on an OS.
- **Other vulnerabilities:**
  - **TOCTOU / race conditions**
  - **covert channels:** **timing** and **storage**
  - **emanations:** TEMPEST
  - **maintenance hooks / backdoors**

> **Exam tip:** **Polyinstantiation** is the defense against **inference** attacks in multilevel databases.

## Cryptographic solutions

- **Cryptographic life cycle:** keys, algorithm selection, retirement.
- **Methods:**
  - **Symmetric:** AES, 3DES, Twofish, ChaCha20.
  - **Asymmetric:** RSA, ECC, Diffie-Hellman, ElGamal.
  - **Elliptic curve.**
  - **Quantum:** post-quantum algorithms such as ML-KEM and ML-DSA.
- **Number of keys:**
  - **Symmetric:** n(n−1)/2 keys for n users.
  - **Asymmetric:** 2n keys.
- **Public key infrastructure (PKI):**
  - CA, RA
  - certificates (X.509)
  - CRL / OCSP
  - certificate pinning
- **Key management practices:**
  - generation, distribution, storage, rotation, destruction
  - **key escrow**
  - **split knowledge / M-of-N control**
- **Digital signatures** and **digital certificates.**
- **Non-repudiation.**
- **Integrity:** hashing (SHA-2/3), HMAC.

## Methods of cryptanalytic attacks

- **brute force**
- **ciphertext only**
- **known plaintext**
- **chosen plaintext / ciphertext**
- **frequency analysis**
- **implementation attacks**
- **side-channel:** timing, power, EM
- **fault injection**
- **timing**
- **man-in-the-middle**
- **pass the hash**
- **Kerberos exploitation**
- **ransomware**
- **birthday attack:** collisions
- **meet-in-the-middle:** why 2DES fails

## Site and facility design and security controls

- **CPTED (crime prevention through environmental design):** natural surveillance, natural access control, territorial reinforcement.
- **Wiring closets / IDFs.**
- **Server rooms / datacenters.**
- **Media storage.**
- **Evidence storage.**
- **Restricted and work area security.**
- **Utilities and HVAC:** temperature and humidity (40–60% humidity typical).
- **Environmental issues:** water, fire, power.
- **Power problems:**
  - fault (momentary loss)
  - blackout (prolonged loss)
  - sag (momentary low voltage)
  - brownout (prolonged low)
  - spike (momentary high)
  - surge (prolonged high)
- **Fire:**
  - **Fire triangle/tetrahedron:** fuel, heat, oxygen, chemical reaction.
  - **Classes:** A (common combustibles; water/foam), B (liquids; CO2/foam), C (electrical; CO2/clean agent; never water), D (metals; dry powder), K (kitchen oils; wet chemical).
  - **Suppression:**
    - **wet pipe:** water always in pipes
    - **dry pipe:** air-filled; good for cold areas
    - **pre-action:** best for datacenters; needs two triggers
    - **deluge**
    - **clean agents:** FM-200, Inergen; Halon is banned
- **Physical controls:** fences (8 ft with barbed wire deters determined intruders), bollards, mantraps/access control vestibules, guards, dogs, lighting, CCTV.

> **Exam tip:** For datacenters, **pre-action** sprinklers are preferred: water only fills the pipes after detection, which reduces accidental discharge.

## Key terms

| Term | Definition |
|------|-----------|
| Fail-safe / fail-secure | Protects people / protects assets on failure |
| Bell-LaPadula | Confidentiality model: no read up, no write down |
| Biba | Integrity model: no read down, no write up |
| Clark-Wilson | Integrity via well-formed transactions |
| Brewer-Nash | Chinese Wall; prevents conflicts of interest |
| Common Criteria / EAL | Product evaluation standard / assurance levels |
| Accreditation (ATO) | Management's formal acceptance of risk |
| TCB / reference monitor | All protection mechanisms / concept mediating all access |
| Aggregation / inference | Combining data / deducing sensitive info |
| Polyinstantiation | Multiple record versions to prevent inference |
| Covert channel | Hidden communication path (timing or storage) |
| Key escrow / M-of-N | Third-party key copy / multiple people needed |
| CPTED | Crime prevention through environmental design |
| Pre-action sprinkler | Requires two triggers before water flows |

## Questions to review

1. Which model enforces "no read up, no write down"?
2. Which model prevents a consultant from accessing a competitor's data after working with a client?
3. Which Common Criteria component describes the customer's security requirements?
4. What's the formal management decision to accept a system's residual risk called?
5. What technique prevents inference attacks in multilevel databases?
6. How many symmetric keys are needed for 10 users to communicate privately in pairs?
7. Which fire extinguisher class is used for electrical fires, and what should never be used on them?
8. Which sprinkler system is best for a datacenter?

<details>
<summary>Show answers</summary>

1. **Bell-LaPadula.**
2. **Brewer-Nash (Chinese Wall).**
3. The **Protection Profile (PP).**
4. **Accreditation / authorization (ATO).**
5. **Polyinstantiation.**
6. 10 × 9 / 2 = **45** keys.
7. **Class C**; never use **water.**
8. **Pre-action.**

</details>
