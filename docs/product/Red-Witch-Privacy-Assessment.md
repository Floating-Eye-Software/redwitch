# Red Witch – Privacy Assessment

**Document ID:** RW-PA-001
**Document Type:** Privacy Assessment
**Version:** Draft 1.0
**Status:** Working Draft
**Related Documents:**

* Threat Model for Menstrual-Cycle Tracking Data
* External Design Input: Cambridge Menstrual Tracking App Report
* External Design Input: Digital Colonialism & AI Data Sovereignty
* Software Requirements Specification (SRS)
* Risk Management File (RMF)

---

# 1. Purpose

This Privacy Assessment evaluates the privacy posture of the Red Witch menstrual-cycle tracking application and assesses whether identified risks, design inputs, and architectural controls adequately address the privacy, safety, autonomy, and data-sovereignty concerns associated with reproductive-health data.

The assessment considers:

* Technical privacy risks
* Security threats
* Data-governance risks
* Consent and autonomy concerns
* Contextual privacy expectations
* Data sovereignty principles
* Emerging AI and inference-related risks

The objective is to determine whether Red Witch's design supports a privacy-preserving, non-extractive, and user-controlled approach to menstrual health tracking.

---

# 2. Assessment Scope

The assessment covers:

* Menstrual-cycle logs
* Symptom tracking
* Fertility and ovulation predictions
* Sexual activity records
* Notifications and reminders
* User accounts and identifiers
* Device metadata
* Data exports and backups
* Partner-sharing features
* Analytics and telemetry
* Future AI-assisted features

The assessment does not evaluate:

* Medical efficacy
* Clinical decision-making
* Regulatory approval status
* General software quality unrelated to privacy

---

# 3. Privacy Context

Menstrual and reproductive-health information represents a category of highly sensitive personal information.

Potential harms associated with misuse include:

* Stalking and surveillance
* Intimate partner violence (IPV)
* Employment discrimination
* Insurance discrimination
* Reproductive-rights enforcement actions
* Reputational harm
* Social coercion
* Loss of personal autonomy

Unlike many consumer applications, privacy risks arise not only from unauthorized disclosure but also from inappropriate collection, inference, secondary use, and contextual misuse.

Consequently, privacy must be evaluated not only through confidentiality and security controls, but also through user agency, consent, governance, and contextual integrity.

---

# 4. Privacy Principles

Red Witch adopts the following privacy principles:

## P-001 User Ownership

User data belongs to the user.

No collection, processing, sharing, or reuse shall occur without an explicit and legitimate user-authorized purpose.

---

## P-002 Data Minimization

Only information necessary to provide requested functionality shall be collected.

Data collection for speculative future use is prohibited.

---

## P-003 Local-First Architecture

User data should remain on the user's device whenever practical.

Cloud storage shall be optional and require explicit user consent.

---

## P-004 Revocable Consent

Consent must be:

* Granular
* Purpose-specific
* Revocable

Withdrawal of consent must be effective and meaningful.

---

## P-005 Transparency

Users shall be able to determine:

* What data exists
* Why it exists
* How it is processed
* When it is accessed
* Whether it is shared

---

## P-006 Non-Extractive Design

The application shall not rely on business models based upon:

* Advertising profiles
* Behavioral targeting
* Data brokerage
* Secondary monetization of reproductive-health information

---

## P-007 Data Sovereignty

The application shall recognize that data is not ownerless.

User data shall remain under user governance and shall not be treated as an unrestricted corporate asset.

---

# 5. Assessment of Current Privacy Controls

## 5.1 Strong Areas

### Local Storage

The proposed architecture prioritizes local storage and offline functionality.

Assessment:
**Strong**

Privacy Benefit:

* Reduces cloud breach risk
* Reduces third-party exposure
* Improves user control

---

### Data Minimization

Current design inputs emphasize collection of only information required for functionality.

Assessment:
**Strong**

Privacy Benefit:

* Reduced attack surface
* Reduced regulatory exposure
* Reduced misuse potential

---

### Consent Architecture

Current requirements emphasize:

* Granular consent
* Revocable consent
* Anti-coercive UX

Assessment:
**Strong**

Privacy Benefit:

* Preserves user autonomy
* Reduces dark-pattern risk
* Supports data-sovereignty goals

---

### IPV and Safety Considerations

Threat modeling includes:

* Coercive partner access
* Notification exposure
* Detectability risks

Assessment:
**Strong**

Privacy Benefit:

* Addresses realistic threat scenarios
* Extends beyond traditional cybersecurity models

---

### Data Sovereignty

The project explicitly rejects assumptions of implicit ownership and bundled consent.

Assessment:
**Strong**

Privacy Benefit:

* Supports trust
* Aligns with emerging ethical expectations
* Reduces future governance risks

---

# 6. Identified Privacy Gaps

## GAP-001: Inference Governance

Current documentation focuses primarily on collected and stored data.

Insufficient attention is given to:

* Derived information
* Predictions
* Behavioral classifications
* AI-generated insights

Examples:

* Fertility-state estimation
* Pregnancy likelihood
* Ovulation confidence
* Hormonal-state inference

Risk:

Derived information may become more sensitive than original user-entered data.

Recommendation:

Establish a dedicated Inference Governance Policy.

---

## GAP-002: Derived Data Ownership

Current documentation defines ownership of entered data but does not explicitly define ownership of generated predictions.

Recommendation:

Users should retain ownership and control over:

* Predictions
* Scores
* Risk classifications
* AI-generated insights

---

## GAP-003: Explainability Requirements

Current requirements do not specify how predictions should be explained.

Risk:

Users may perceive the application as surveillant or opaque.

Recommendation:

Provide user-visible explanations for:

* Prediction updates
* Confidence levels
* Significant model outputs

---

## GAP-004: Privacy UX Requirements

Privacy controls exist but user experience requirements are not explicitly defined.

Recommendation:

Create Privacy UX requirements covering:

* Notification design
* Sensitive language
* Visibility controls
* Consent presentation
* Privacy settings discoverability

---

## GAP-005: Future Governance Changes

Current documentation partially addresses acquisition and corporate change risks.

Recommendation:

Establish governance controls covering:

* Ownership changes
* Policy changes
* Data-transfer restrictions
* Successor obligations

---

# 7. Assessment of Contextual Privacy

Traditional privacy assessments focus on unauthorized access.

For Red Witch, contextual privacy is equally important.

Users may accept highly sensitive processing when:

* The purpose is clear
* The benefit is obvious
* The data remains under their control
* The processing occurs within expected boundaries

Users may reject otherwise secure systems when:

* Processing appears opaque
* Inferences are unexpected
* Data is reused for unrelated purposes
* Consent is bundled or coerced

Assessment:

Current documentation addresses contextual privacy indirectly through consent, sovereignty, transparency, and anti-coercive design.

However, contextual expectations regarding inference and prediction should be documented more explicitly.

Assessment Rating:
**Partially Addressed**

---

# 8. Assessment of Data Sovereignty

The project demonstrates strong alignment with modern data-sovereignty principles through:

* Local-first storage
* Revocable permissions
* Transparency requirements
* Anti-coercive consent
* Rejection of silent data collection
* Explicit ownership assumptions

Assessment Rating:
**Strong**

The design substantially exceeds typical consumer-app privacy practices.

---

# 9. Overall Privacy Maturity Assessment

| Category                  | Assessment |
| ------------------------- | ---------- |
| Data Minimization         | Strong     |
| Local Storage             | Strong     |
| Security Threat Coverage  | Strong     |
| Privacy Threat Coverage   | Strong     |
| Consent Model             | Strong     |
| Data Sovereignty          | Strong     |
| Contextual Privacy        | Moderate   |
| Privacy UX                | Moderate   |
| Inference Governance      | Developing |
| Derived Data Governance   | Developing |
| Corporate Governance Risk | Moderate   |

---

# 10. Conclusion

Red Witch demonstrates a privacy posture significantly stronger than typical commercial menstrual-tracking applications.

The project incorporates:

* Privacy-by-design
* Local-first architecture
* Data minimization
* Revocable consent
* Data-sovereignty principles
* Reproductive-health threat modeling

The most significant remaining challenge is governance of derived information and predictive inference.

Future privacy work should focus on:

1. Inference governance.
2. Derived-data ownership.
3. Explainable predictions.
4. Privacy-focused user experience requirements.
5. Long-term governance and acquisition resilience.

Subject to resolution of these gaps, the overall privacy posture is assessed as:

**High Privacy Maturity – User-Centric and Sovereignty-Oriented**
