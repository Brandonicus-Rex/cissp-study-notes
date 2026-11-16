# Domain 5: Identity and Access Management (IAM) (13%)

## Control physical and logical access to assets

- **Assets:** information, systems, devices, facilities, applications, services.
- **Access control concepts:**
  - **Subject:** active entity requesting access.
  - **Object:** passive resource.
  - **IAAA:** identification, authentication, authorization, accountability (auditing).

## Design identification and authentication strategy

- **Groups and roles.**
- **Authentication factors:**

| Factor | Type | Examples |
|--------|------|----------|
| Something you **know** | Type 1 | Password, PIN |
| Something you **have** | Type 2 | Smart card, token, phone |
| Something you **are** | Type 3 | Fingerprint, iris, face |
| Somewhere you **are** / something you **do** | Context | Location, typing pattern |

- **MFA** requires factors from **different types**. A password plus a PIN is still single-factor.
- **Biometrics:**
  - **FRR (Type I error):** false rejection; a legitimate user is denied.
  - **FAR (Type II error):** false acceptance; an impostor is allowed. More dangerous.
  - **CER / EER (crossover error rate):** where FRR = FAR. **Lower CER = more accurate.**
  - Iris and retina scans are among the most accurate.
- **Passwordless:** FIDO2/WebAuthn, passkeys, Windows Hello.
- **Session management:** timeouts, re-authentication, secure tokens.
- **Registration, proofing and establishment of identity:** NIST SP 800-63 identity assurance levels (IAL), authenticator assurance levels (AAL), federation assurance levels (FAL).
- **Federated identity management (FIM)** and **credential management systems:** password vaults.
- **Single sign-on (SSO).**
- **Just-in-time (JIT) access.**

> **Exam tip:** **Type II errors (false acceptance)** are the more serious security problem. **CER** is the best single number for comparing biometric systems; lower is better.

## Federated identity with a third-party service

- **On-premises**, **cloud**, **hybrid.**
- **Protocols:**

| Protocol | Purpose | Key facts |
|----------|---------|-----------|
| **SAML 2.0** | **Authentication** and authorization assertions for web SSO | XML. Roles: principal (user), identity provider (IdP), service provider (SP) |
| **OAuth 2.0** | **Authorization** (delegated access) | Access tokens; "allow this app to access my data" |
| **OpenID Connect (OIDC)** | **Authentication** on top of OAuth 2.0 | ID tokens (JWT) |
| **Kerberos** | Network authentication | Tickets, KDC, symmetric keys |

## Implement and manage authorization mechanisms

| Model | Who decides | Notes |
|-------|-------------|-------|
| **DAC (discretionary)** | **Owner** | Flexible; ACLs; most common in commercial OSes |
| **MAC (mandatory)** | **System**, by labels and clearances | Rigid; military; uses Bell-LaPadula |
| **RBAC (role-based)** | Job role | Scales well; good for high turnover |
| **Rule-based** | Global rules set by admins | E.g., firewall rules, time-of-day |
| **ABAC (attribute-based)** | Attributes of subject, object, action and environment | Most granular and flexible; policy-driven |
| **Risk-based** | Real-time risk evaluation | Adaptive; uses context and behavior |

- **Non-discretionary access control:** an umbrella term often used for RBAC and MAC.

> **Exam tip:** **MAC** = labels and clearances (military). **DAC** = owner decides. **ABAC** = most flexible ("users in HR can read files tagged 'HR' during business hours from managed devices").

## Manage the identity and access provisioning life cycle

- **Account access review:** user, system and service accounts.
- **Provisioning and deprovisioning:** onboarding, transfers, offboarding. Remove access immediately on termination.
- **Role definition and transition:** people moving between roles.
- **Privilege escalation:** managed service accounts, use of sudo, minimizing its use.
- **Service accounts management.**
- **Privilege creep:** access builds up over time as people change roles. Fix with periodic **access reviews / recertification.**

## Implement authentication systems

- **Kerberos:**
  1. User authenticates to the **authentication service (AS)** and receives a **ticket-granting ticket (TGT).**
  2. The user presents the TGT to the **ticket-granting service (TGS)** and receives a **service ticket.**
  3. The user presents the service ticket to the **service.**
  - AS + TGS = the **key distribution center (KDC)**, a single point of failure.
  - Requires **time synchronization.**
  - Uses **symmetric** cryptography.
- **LDAP / LDAPS:** directory access.
- **RADIUS**, **TACACS+**, **Diameter.**
- **SESAME:** European Kerberos extension using public-key cryptography.

> **Exam tip:** Kerberos needs **synchronized clocks**, because tickets are time-stamped to prevent replay. The **KDC is a single point of failure.**

## Key terms

| Term | Definition |
|------|-----------|
| IAAA | Identification, authentication, authorization, accountability |
| Type 1 / 2 / 3 factors | Know / have / are |
| FRR / FAR / CER | False rejection / false acceptance / crossover error rate |
| NIST SP 800-63 | Digital identity guidelines (IAL, AAL, FAL) |
| SAML | XML-based authentication assertions for SSO |
| OAuth 2.0 | Delegated authorization framework |
| OIDC | Authentication layer on OAuth 2.0 |
| DAC / MAC / RBAC / ABAC | Access control models |
| Privilege creep | Accumulating unnecessary access over time |
| KDC / TGT | Kerberos key distribution center / ticket-granting ticket |
| JIT access | Temporary elevated access when needed |

## Questions to review

1. A password and a security question together count as how many authentication factors?
2. Which biometric error rate is more dangerous from a security standpoint?
3. What does a lower CER indicate?
4. Which protocol provides delegated authorization, not authentication?
5. In SAML, which party authenticates the user and issues the assertion?
6. In which access control model does the data owner decide who gets access?
7. An employee who moved through three departments still has access from all of them. What's this called, and how do you fix it?
8. Which Kerberos component issues the ticket-granting ticket?

<details>
<summary>Show answers</summary>

1. **One** (both are something you know).
2. **FAR (false acceptance, Type II).**
3. A **more accurate** biometric system.
4. **OAuth 2.0.**
5. The **identity provider (IdP).**
6. **DAC** (discretionary access control).
7. **Privilege creep**; fixed with **periodic access reviews.**
8. The **authentication service (AS)**, part of the KDC.

</details>
