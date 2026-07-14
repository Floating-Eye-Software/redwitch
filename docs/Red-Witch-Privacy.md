# 📄 Red Witch – External Design Input: Cambridge Menstrual Tracking App Report

**Document Name:** "Menstrual tracking app data is a ‘gold mine’ for advertisers that risks women’s safety"
**Source / Link:** [Cambridge Research News – Minderoo Centre, 2025](https://www.cam.ac.uk/research/news/menstrual-tracking-app-data-is-a-gold-mine-for-advertisers-that-risks-womens-safety-report)
**Document Type:** External Design Input / Market & Safety Evidence
**Purpose:** Provide evidence of privacy, safety, and commercial risks associated with menstrual tracking apps. Used to inform requirements and risk management in the Red Witch project.

---

## 1. Summary of Key Findings

- Cycle tracking apps collect highly sensitive data (exercise, diet, sexual preferences, contraception use, hormone levels).
- Commercial apps monetize this data for advertising and profiling, often without meaningful consent.
- Potential harms include:
  - Cyberstalking and surveillance
  - Discrimination in employment or insurance
  - Legal risks related to reproductive rights (e.g., abortion access)
- Current market solutions prioritize profit over user safety.
- Public health alternatives (e.g., NHS app) could provide privacy-preserving options and improve digital literacy.

---

## 2. Implications for Red Witch Design

Based on the report, Red Witch shall implement the following **design inputs / requirements**:

| Requirement / Design Input | Description | Linked RMF Risk |
|----------------------------|------------|----------------|
| DI-001: Local-only storage | All user data must remain on the device; no cloud storage by default | R-Ext-001 |
| DI-002: End-to-end encryption | User-controlled encryption key; app cannot access PHI | R-Ext-001, R-Ext-002 |
| DI-003: User-controlled export/import | Only encrypted exports allowed; no automatic sharing | R-Ext-001 |
| DI-004: Minimal data collection | Collect only data strictly necessary for functionality | R-Ext-001, R-Ext-002 |
| DI-005: Transparency & consent | Clear, granular consent options for any data use | R-Ext-001 |
| DI-006: Privacy education | User guidance in app/manual about risks and safe use | R-Ext-003 |

---

## 3. Link to Risk Management File

External risks identified from the Cambridge report have been added to the RMF:

| RMF Risk ID | Source | Risk Description | Mitigation / Control |
|------------|--------|-----------------|-------------------|
| R-Ext-001 | Cambridge Report (2025) | Commercial exploitation of menstrual data leading to privacy/safety harms | Local-only storage, encryption, user-controlled export, minimal data collection, consent |
| R-Ext-002 | Cambridge Report (2025) | Data misuse could lead to discrimination, cyberstalking, or limitation of reproductive rights | Legal compliance (HIPAA, PHIPA, PIPEDA, GDPR), offline operation, minimal data collection |
| R-Ext-003 | Cambridge Report (2025) | Users unaware of risks due to lack of education | User Manual, Privacy Policy, digital literacy guidance |

---

### 4. Usage

This external design input informs:

- **SRS – Design Inputs Section**: justification for privacy/security features.
- **RMF**: identification of external risks, linkage to mitigations.
- **QMS Evidence**: demonstrates consideration of external research in risk-based design.
