# Red Witch – Inference Governance Policy

**Document ID:** RW-IG-001
**Document Type:** Inference Governance Policy
**Version:** Draft 1.0
**Status:** Working Draft

**Related Documents:**

* Privacy Assessment (RW-PA-001)
* Threat Model for Menstrual-Cycle Tracking Data
* External Design Input: Cambridge Menstrual Tracking App Report
* External Design Input: Digital Colonialism & AI Data Sovereignty
* Software Requirements Specification (SRS)
* Risk Management File (RMF)

---

# 1. Purpose

This document establishes governance requirements for all predictive, inferential, analytical, and AI-assisted functions within the Red Witch platform.

The purpose of this policy is to ensure that:

* User autonomy is preserved.
* Derived information receives the same or greater protection as source data.
* Predictions remain transparent and explainable.
* Users retain meaningful control over reproductive-health inferences.
* The system remains aligned with privacy-by-design and data-sovereignty principles.

---

# 2. Scope

This policy applies to all system-generated outputs derived from user-provided or user-authorized data, including:

* Menstrual-cycle predictions
* Ovulation predictions
* Fertility-window estimates
* Symptom trend analysis
* Pattern recognition
* Cycle irregularity detection
* Wellness insights
* Statistical classifications
* AI-assisted recommendations
* Future machine-learning models

This policy applies regardless of whether processing occurs:

* On-device
* In a cloud environment
* Through third-party AI systems
* Through rule-based algorithms

---

# 3. Definitions

## Source Data

Information intentionally entered or explicitly authorized by the user.

Examples:

* Period start dates
* Symptom logs
* Mood records
* Basal body temperature
* Medication records

---

## Derived Data

Information generated from source data through computation or analysis.

Examples:

* Predicted period date
* Fertility score
* Ovulation estimate
* Cycle-length averages
* Trend analysis

---

## Sensitive Inference

A generated conclusion that may reveal information not explicitly entered by the user.

Examples:

* Pregnancy likelihood
* Fertility intent
* Sexual activity likelihood
* Hormonal-state estimation
* Potential reproductive-health conditions

---

## Classification

Assignment of a user into a category based on data patterns.

Examples:

* Regular cycle
* Irregular cycle
* High-confidence prediction
* Low-confidence prediction

---

# 4. Core Governance Principles

## IG-001: User Primacy

The user remains the primary authority regarding interpretation of their health information.

System-generated outputs shall support user understanding and decision-making but shall not supersede user judgment.

---

## IG-002: Inference Is Data

Derived information shall be treated as sensitive user data.

Predictions, classifications, and analytical outputs shall receive the same protections as source information.

---

## IG-003: No Hidden Inference

The application shall not generate sensitive inferences unknown to the user.

Users shall be informed whenever:

* New inference categories are introduced.
* New analytical capabilities are enabled.
* Significant predictive models are added.

---

## IG-004: Explainability

Users shall be able to understand:

* What prediction was generated.
* Why the prediction was generated.
* What information contributed to the prediction.
* The degree of uncertainty associated with the prediction.

---

## IG-005: Revocability

Users shall be able to:

* Disable inference features.
* Delete generated insights.
* Reset prediction history.
* Withdraw consent for future processing.

---

## IG-006: Proportionality

Inference complexity shall remain proportional to user expectations.

The application shall not perform analyses unrelated to menstrual-health functionality.

---

# 5. Inference Categories

## Category A – Core Cycle Predictions

Examples:

* Next period prediction
* Cycle length estimate
* Ovulation estimate

Purpose:

Directly support menstrual tracking.

Default Status:

Enabled.

---

## Category B – Trend Analysis

Examples:

* Cycle regularity trends
* Symptom frequency trends
* Historical comparisons

Purpose:

Provide user insight.

Default Status:

Enabled.

---

## Category C – Health Pattern Detection

Examples:

* Unusual cycle variation
* Significant changes in symptoms
* Irregularity alerts

Purpose:

Support awareness and healthcare discussions.

Default Status:

Optional.

User Notification Required:

Yes.

---

## Category D – Sensitive Reproductive Inferences

Examples:

* Pregnancy likelihood
* Fertility-intent estimation
* Sexual-activity inference
* Reproductive-status prediction

Purpose:

Potentially sensitive.

Default Status:

Disabled unless explicitly enabled.

Additional Governance Required:

Yes.

---

## Category E – Future AI-Assisted Insights

Examples:

* Large-language-model recommendations
* Behavioral pattern analysis
* AI-generated summaries

Purpose:

Advanced features.

Default Status:

Disabled unless explicitly enabled.

Additional Governance Required:

Yes.

---

# 6. Prohibited Inferences

The following inferences shall not be generated:

## PI-001

Political beliefs.

---

## PI-002

Religious affiliation.

---

## PI-003

Sexual orientation.

---

## PI-004

Relationship quality assessments.

---

## PI-005

Mental-health diagnoses.

---

## PI-006

Employment suitability.

---

## PI-007

Insurance risk assessments.

---

## PI-008

Advertising profiles.

---

## PI-009

Commercial segmentation.

---

## PI-010

Any inference unrelated to menstrual-health functionality.

---

# 7. Inference Sovereignty

Red Witch recognizes that derived information may be more sensitive than source data.

Therefore:

* Users retain ownership of generated insights.
* Users may export generated insights.
* Users may delete generated insights.
* Generated insights shall not be sold.
* Generated insights shall not be licensed.
* Generated insights shall not be shared with advertisers.
* Generated insights shall not be used to train third-party models.

Inference shall not create new ownership claims over user information.

---

# 8. Model Transparency Requirements

Where predictive models are used, users shall have access to:

* Prediction confidence
* Last update date
* Data sources used
* General explanation of methodology
* Known limitations

The application shall clearly distinguish:

* Facts entered by the user
* Information estimated by the system

---

# 9. Privacy and Security Controls

Inference systems shall follow the principles of:

* Local-first processing
* Data minimization
* Privacy-by-design
* Secure storage
* Revocable consent

Where feasible:

* Inference should occur on-device.
* Cloud processing should be avoided.
* Sensitive reproductive-state calculations should remain local.

---

# 10. Human Factors and User Experience

The application shall avoid language that implies surveillance or authority.

Preferred language:

* "Based on your logged data..."
* "The application estimates..."
* "Prediction confidence is moderate..."

Avoid:

* "We detected..."
* "We know..."
* "You are..."
* "The system determined..."

The application shall remain a tool supporting the user, not an observer evaluating the user.

---

# 11. Governance Review

Inference capabilities shall be reviewed whenever:

* New models are introduced.
* New inference categories are proposed.
* AI systems are added.
* New data sources are integrated.
* Significant privacy risks are identified.

Review shall include:

* Privacy impact assessment
* Risk assessment
* User autonomy assessment
* Data sovereignty assessment

---

# 12. Compliance Statement

Red Witch adopts the principle that inference is not exempt from privacy obligations.

Generated knowledge shall be governed with the same care, transparency, and user control as the source data from which it was derived.

No predictive capability shall override the principles of:

* User autonomy
* Privacy-by-design
* Data sovereignty
* Revocable consent
* Non-extractive software design
