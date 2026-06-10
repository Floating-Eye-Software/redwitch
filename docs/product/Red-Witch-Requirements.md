# 📄 Red Witch – Software Requirements Specification (SRS)

**System Name:** *Red Witch*
**Location:** Ontario, Canada
**Intended Market:** Global (Canada, U.S., EU/EEA)
**Version:** Draft 2.0

---

## 1. Introduction

**1.1 Purpose**
This document specifies the software requirements for *Red Witch*, a privacy-first menstrual and cycle tracking application. Requirements ensure compliance with HIPAA, GDPR, PIPEDA, PHIPA, Health Canada guidance, and EU MDR where applicable.

**1.2 Scope**
Red Witch provides:

* Cycle tracking, symptom logging, and predictive insights
* Local-only, end-to-end encrypted storage with user-controlled keys
* Encrypted export/import of user data
* Modular calendar overlays for fertility and cultural frameworks
* Multilingual, accessible UI and educational content

**1.3 Regulatory Context**

* Canada: PIPEDA, PHIPA, Health Canada medical device framework
* United States: HIPAA (if marketed), FTC privacy standards
* European Union: GDPR, MDR (if classified as medical device)

**1.4 Definitions**

* PHI – Protected Health Information
* PII – Personally Identifiable Information
* E2EE – End-to-End Encryption
* Local-only storage – Data stored exclusively on device

---

## 2. System Overview

**2.1 Product Perspective**
Standalone mobile app (iOS, Android) with optional desktop companion.

**2.2 User Needs**

* Privacy-first cycle tracking with ownership of data
* Accurate predictions and reminders
* Support for diverse reproductive goals, genders, ages, and cultural contexts
* Accessible and inclusive interfaces for low-literacy and global users

---

## 3. System Requirements

### 3.1 Functional Requirements (FR)

| Req ID       | Description                                                        | Priority |
| ------------ | ------------------------------------------------------------------ | -------- |
| FR-1         | Log cycle events (start/end, flow)                                 | MVP      |
| FR-2         | Log symptoms (pain, mood, basal temp, notes)                       | MVP      |
| FR-3         | Provide predictive insights (period, fertile window) locally       | MVP      |
| FR-4         | Encrypted backup/export                                            | MVP      |
| FR-5         | Import encrypted backup                                            | MVP      |
| FR-6         | Configurable reminders (period, ovulation, medication)             | MVP      |
| FR-7         | Full offline functionality                                         | MVP      |
| FR-BOM-1     | Daily BOM cervical mucus logging                                   | MVP      |
| FR-BOM-2     | BOM interpretation (fertile/infertile)                             | MVP      |
| FR-BOM-3     | BOM onboarding, education, disclaimers                             | MVP      |
| FR-BOM-4     | Multilingual BOM content                                           | Future   |
| FR-BOM-5     | Privacy-focused BOM UI, discreet notifications                     | Future   |
| FR-BOM-6     | Optional anonymized BOM export                                     | Future   |
| FR-Overlay-1 | Core calendar stores neutral cycle data                            | MVP      |
| FR-Overlay-2 | Modular overlay system for fertility/cultural layers               | MVP      |
| FR-Overlay-3 | Users can toggle overlays independently                            | MVP      |
| FR-Overlay-4 | Overlays display transparent visualization                         | MVP      |
| FR-Overlay-5 | Each overlay includes legend, explanation, disclaimers             | MVP      |
| FR-Overlay-6 | Overlays do not modify raw data                                    | MVP      |
| FR-Overlay-7 | Overlay system modular/extensible                                  | Future   |
| FR-Overlay-8 | Fertility overlays clearly distinguish validated vs wellness tools | MVP      |

---

### 3.2 Security Requirements (SR)

| Req ID       | Description                                         | Priority |
| ------------ | --------------------------------------------------- | -------- |
| SR-1         | Data encrypted at rest (AES-256)                    | MVP      |
| SR-2         | Local-only key generation; no external transmission | MVP      |
| SR-3         | Export encryption via user passphrase               | MVP      |
| SR-4         | Biometric/PIN access                                | MVP      |
| SR-5         | Automatic lock after inactivity                     | MVP      |
| SR-6         | No PHI transmitted to third parties                 | MVP      |
| SR-7         | Audit logs for failed login attempts                | MVP      |
| SR-Overlay-1 | Overlay toggling respects privacy settings          | MVP      |
| SR-Overlay-2 | Overlay processing occurs locally                   | MVP      |
| SR-Overlay-3 | Optional anonymized overlay export                  | Future   |

---

### 3.3 Regulatory Requirements (RR)

| Req ID       | Description                                                      | Priority |
| ------------ | ---------------------------------------------------------------- | -------- |
| RR-1         | Explicit consent dialogs (GDPR, PIPEDA)                          | MVP      |
| RR-2         | User data deletion (“right to erasure”)                          | MVP      |
| RR-3         | Privacy by design/default                                        | MVP      |
| RR-4         | MDR Class IIa compliance if marketed as contraceptive/diagnostic | Future   |
| RR-5         | Health Canada licensing for medical device                       | Future   |
| RR-Overlay-1 | Overlay system clearly labels fertility methods/disclaimers      | MVP      |
| RR-Overlay-2 | Overlay export complies with GDPR/PIPEDA/HIPAA                   | MVP      |

---

### 3.4 Non-Functional Requirements (NFR)

| Req ID        | Description                                              | Priority |
| ------------- | -------------------------------------------------------- | -------- |
| NFR-1         | Response <1s for logging                                 | MVP      |
| NFR-2         | Support 10+ years of cycle data                          | MVP      |
| NFR-3         | WCAG 2.1 AA accessibility                                | MVP      |
| NFR-4         | English/French at launch; multilingual expansion         | MVP      |
| NFR-Overlay-1 | Overlay rendering responsive <1s                         | MVP      |
| NFR-Overlay-2 | Overlay offline support                                  | MVP      |
| NFR-Overlay-3 | Overlay multilingual rendering                           | Future   |
| NFR-Overlay-4 | Overlay integrates with privacy-first storage/encryption | MVP      |

---
