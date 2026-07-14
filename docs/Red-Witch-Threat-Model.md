# **Threat Model for Menstrual-Cycle Tracking Data**

**Framework:** STRIDE (security threats) + LINDDUN (privacy threats)
**Scope:** Menstrual cycle logs, symptoms, sexual activity, fertility windows, partner-sharing, device metadata, identifiers, geolocation, backups, analytics events, notification content, and user account data.

---

# **1. STRIDE Threat Model (Security-Focused)**

## **S — Spoofing Identity**

**Threats**

* Attacker uses stolen credentials to impersonate a user and access menstrual and reproductive data.
* Abusive partners or family members guessing simple passcodes on shared devices.
* Account creation via falsified email to intercept shared/partner data.

**Root Causes**

* Weak or reused passwords.
* No multi-factor authentication (MFA) options.
* Poor session token hygiene.

**Potential Harms**

* Exposure of sensitive reproductive information.
* Coercive control, harassment, or intimate partner violence.

**Mitigations**

* Optional MFA.
* Strong session management.
* Device-level biometric or PIN lock for app access.
* Rate limiting and login anomaly detection.

---

## **T — Tampering**

**Threats**

* Unauthorized modification of cycle logs or symptom entries by an abuser.
* Malicious apps or spyware altering stored data.
* API manipulation to interfere with prediction accuracy.

**Root Causes**

* Unprotected local storage.
* Insufficient input validation.
* No integrity checks for local files.

**Potential Harms**

* Compromised health data.
* Wrong fertility or ovulation predictions.
* Evidence manipulation in legal or custody disputes.

**Mitigations**

* Data integrity hashing.
* Secure local storage (Keychain/Keystore).
* Access controls and tamper-evident logging.

---

## **R — Repudiation**

**Threats**

* Users or attackers deny actions they performed (data changes, deletions).
* Lack of verifiable logs complicates internal incident response.

**Root Causes**

* Insufficient audit logging.
* No cryptographic signing of events.

**Potential Harms**

* Inability to investigate breaches.
* Legal challenges in law-enforcement requests.

**Mitigations**

* Privacy-preserving audit logs.
* Clear logging of administrative actions (never log symptoms, sexual data).

---

## **I — Information Disclosure**

**Threats**

* Data leaks via third-party analytics SDKs.
* Geolocation data correlating with clinic visits.
* Cloud breach exposing reproductive data.
* Notification previews exposing sensitive symptoms on locked screens.

**Root Causes**

* Use of ad networks and external trackers.
* Misconfigured cloud buckets.
* Broad permission scopes.
* Unencrypted local or cloud storage.

**Potential Harms**

* Digital stalking, discrimination, reproductive-rights criminalization.
* Profiling by insurers, employers, or advertisers.

**Mitigations**

* Zero/low third-party SDKs.
* End-to-end encryption for sensitive fields.
* Privacy-first notification design.
* Data minimization and local-storage options.

---

## **D — Denial of Service (DoS)**

**Threats**

* API flooding disrupting availability of predictions or reminders.
* Targeted attacks during ovulation windows to create panic or uncertainty.
* App inaccessible due to server outage or shutdown.

**Root Causes**

* Weak rate limiting.
* Unreliable cloud infrastructure.
* Centralized architecture with no offline mode.

**Potential Harms**

* Missed medication or contraceptive timing reminders.
* Loss of trust and abandonment of digital tracking.

**Mitigations**

* Rate limiting and traffic filtering.
* Offline-first architecture.
* Graceful fallback for predictions.

---

## **E — Elevation of Privilege**

**Threats**

* Malicious actors or rogue employees elevating privileges to access sensitive datasets.
* Exploits in partner-sharing systems granting access to unauthorized parties.

**Root Causes**

* Overbroad internal roles.
* Poorly segmented permissions.
* Missing authorization checks in APIs.

**Potential Harms**

* Large-scale data exposure.
* Unauthorized manipulation of user profiles or preferences.

**Mitigations**

* Strict RBAC/ABAC.
* Internal access logging and monitoring.
* Secure-by-default API authorization.

---

# **2. LINDDUN Threat Model (Privacy-Focused)**

## **L — Linkability**

**Threats**

* Linking menstrual logs across sessions, devices, or external datasets.
* Cross-app correlation through advertising identifiers or fingerprinting.

**Harms**

* Re-identification of pseudonymous users.
* Sensitive insights about fertility status or sexual activity.

**Mitigations**

* Disable ad IDs.
* Partition identifiers by context.
* Provide true anonymous mode.

---

## **I — Identifiability**

**Threats**

* Combining metadata (IP, device ID, location) with cycle data to identify specific users.
* Inference of identity from unique cycle patterns.

**Harms**

* Unwanted exposure, stalking, discrimination.

**Mitigations**

* Strict data minimization.
* IP tokenization.
* Optional local-only profiles without cloud sync.

---

## **N — Non-Repudiation (In Privacy)**

(In privacy models, this refers to **inability to plausibly deny** an association with sensitive data.)

**Threats**

* App stores or cloud logs linking an account to period tracking.
* Metadata revealing pregnancy attempts or sexual activity.

**Harms**

* Legal risk in restricted reproductive-rights environments.

**Mitigations**

* Anonymous download paths where possible.
* Minimal server-side logging.
* Local-only modes without account creation.

---

## **D — Detectability**

**Threats**

* Adversaries inferring app use through traffic patterns, notifications, or OS-level metadata.
* Observers detecting period-prediction reminders on shared devices.

**Harms**

* Outing of sexual or reproductive behavior.
* Increased vulnerability in abusive relationships.

**Mitigations**

* Stealth mode: neutral notification text.
* Traffic obfuscation (padding or batching).
* Option to hide or rename app icon (where permitted).

---

## **D — Disclosure of Information**

(Overlaps with STRIDE “Information Disclosure,” but from a privacy lens.)

**Threats**

* Sharing data with advertisers, health-data brokers, or AI training pipelines.
* Unintentional disclosures through customer support tickets or logs.

**Harms**

* Behavioral profiling.
* Employment or insurance discrimination.

**Mitigations**

* Explicit prohibition on third-party data sharing.
* Purpose-limited collection.
* Granular, revocable consent.

---

## **U — Unawareness**

**Threats**

* Users not understanding prediction uncertainty or data use.
* Dark patterns in consent flows.
* Confusing privacy settings for partner sharing.

**Harms**

* Users inadvertently sharing highly sensitive data.
* Over-reliance on prediction accuracy for contraception decisions.

**Mitigations**

* Clear explanations of uncertainty.
* Transparent, non-bundled consent.
* Simple, front-loaded privacy settings.

---

## **N — Non-Compliance**

**Threats**

* Violations of GDPR, CPRA, DPDP, LGPD, or data-localization requirements.
* Cloud providers storing data in jurisdictions with reproductive-rights risks.
* App-store policy violations that force data-sharing compliance.

**Harms**

* Legal penalties, forced shutdown, user harm via inappropriate law-enforcement access.

**Mitigations**

* Data-mapping and jurisdiction-aware storage.
* Privacy-by-design controls.
* Regular audits and DPIAs.

---

# **3. High-Risk Scenarios (Cross-STRIDE/LINDDUN)**

These represent the most severe, multi-category threats:

### **A. Intimate Partner Violence (IPV) Coercion**

* Device access forced; app reveals menstrual or sexual activity.
* Notifications or icons expose tracking.
* Threat Categories: Spoofing, Disclosure, Identifiability, Detectability.

### **B. Reproductive-Rights Criminalization**

* Data subpoenaed for pregnancy/abortion investigations.
* Law enforcement correlating cycle data with clinic visits.
* Threat Categories: Disclosure, Identifiability, Linkability, Non-Repudiation.

### **C. Third-Party SDK Leakage**

* Analytics/ads SDKs transmitting reproductive data without intent.
* Threat Categories: Disclosure, Linkability, Non-Compliance.

### **D. Data Breach of Cloud Storage**

* Mass exposure of cycle logs, sexual activity, fertility status.
* Threat Categories: Information Disclosure, Identifiability, Tampering.

### **E. App Shutdown or Acquisition**

* Data sold or transferred to less ethical companies.
* Threat Categories: Non-Compliance, Disclosure, Unawareness, Non-Repudiation.

---

# **4. Summary of Mitigation Priorities**

Based on severity and likelihood:

1. **Local-first architecture with strong encryption.**
2. **Eliminate or drastically limit third-party SDKs.**
3. **Stealth and safety modes for IPV contexts.**
4. **Granular, revocable consent with no bundled permissions.**
5. **Privacy-preserving analytics or zero analytics.**
6. **Offline access and minimal server logging.**
7. **Inclusive design for gender-diverse and vulnerable users.**
8. **Data retention limits and “zero-knowledge” policies where possible.**
