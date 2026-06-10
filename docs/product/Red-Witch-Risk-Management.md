
# 📄 Red Witch – Risk Management File (RMF)

## 1. Hazard Identification

| ID   | Hazard                                      | Scenario                                    | Harm                               |
| ---- | ------------------------------------------- | ------------------------------------------- | ---------------------------------- |
| H-1  | Unauthorized device access                  | Device lost/stolen; bypasses phone/app lock | PHI disclosure                     |
| H-2  | Data loss                                   | User forgets encryption key                 | Permanent data loss                |
| H-3  | Supply chain attack                         | Malicious app update installed              | PHI disclosure                     |
| H-4  | Malware on device                           | Spyware captures input                      | PHI disclosure                     |
| H-5  | Legal compulsion                            | Authorities seize device                    | PHI disclosure used in prosecution |
| H-6  | Regulatory misclassification                | App marketed without device license         | Legal penalties, recall            |
| H-7  | Human error                                 | User exports unencrypted backup             | PHI disclosure                     |
| H-30 | Incorrect BOM or overlay interpretation     | Misinterpretation of fertility status       | Unintended pregnancy               |
| H-31 | Coercive overlay/BOM use                    | Partner/family abuse                        | Privacy violation, emotional harm  |
| H-32 | Misuse of exported overlay data             | Unauthorized sharing/export                 | Legal/reputational harm            |
| H-33 | Misinterpretation due to language/culture   | Low literacy/misunderstanding               | Incorrect predictions              |
| H-34 | Overlay visibility revealing sensitive info | Accidental disclosure                       | Social, legal, emotional harm      |

---

## 2. Risk Control Measures

| Hazard | Mitigation                                         | Linked Requirement                   |
| ------ | -------------------------------------------------- | ------------------------------------ |
| H-1    | Biometric + PIN, device encryption                 | SR-4, SR-5                           |
| H-2    | Key backup with warnings                           | SR-2, FR-4                           |
| H-3    | Signed reproducible builds, app store verification | NFR-2                                |
| H-4    | User guidance on secure device                     | User manual                          |
| H-5    | Local-only storage; minimal metadata               | SR-2, SR-6                           |
| H-6    | Regulatory review before launch                    | RR-4, RR-5                           |
| H-7    | Encrypted-only export                              | SR-3, FR-4                           |
| H-30   | Education, structured logging, disclaimers         | FR-BOM-1, FR-BOM-2, FR-Overlay-2     |
| H-31   | Privacy defaults, discreet UI, opt-in overlays     | FR-BOM-5, FR-Overlay-3               |
| H-32   | Explicit consent, anonymized export                | FR-BOM-6, SR-Overlay-3               |
| H-33   | Multilingual support, usability testing            | FR-BOM-4, FR-Overlay-7               |
| H-34   | Neutral notifications, opt-in overlays             | FR-BOM-5, FR-Overlay-3, SR-Overlay-1 |

---

## 3. Residual Risk Evaluation

* **H-5, H-30:** Residual risk remains medium; mitigated with education, structured logging, and privacy-first design.
* All other hazards reduced to **low/medium** via technical, procedural, and user-consent controls.

---

## 4. Traceability Matrix

| Requirement                 | Linked Hazard | Mitigation                                         |
| --------------------------- | ------------- | -------------------------------------------------- |
| FR-4, FR-5                  | H-2, H-7      | Encrypted backups only                             |
| SR-2                        | H-1, H-2, H-5 | User-only control, local storage                   |
| SR-3                        | H-7           | Prevent plaintext leakage                          |
| RR-4/5                      | H-6           | Ensure compliance review                           |
| FR-BOM-1 / FR-BOM-2         | H-30          | Structured logging, education, disclaimers         |
| FR-BOM-5 / FR-Overlay-3     | H-31, H-34    | Discreet UI, opt-in overlays                       |
| FR-BOM-6 / SR-Overlay-3     | H-32          | Anonymized export, explicit consent                |
| FR-BOM-4 / FR-Overlay-7     | H-33          | Multilingual support, usability testing            |
| FR-Overlay-2 / FR-Overlay-4 | H-30, H-31    | Local processing, privacy-respecting visualization |

---
