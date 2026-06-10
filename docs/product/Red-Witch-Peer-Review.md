# 📄 Red Witch – Post-Market Surveillance (PMS) Item: Peer-Reviewed Comparison of Menstrual Tracking Apps

**Document Name:** "Evaluation of Menstrual Cycle Tracking Applications Available in the App Stores"
**Source / Link:** [PMC Article (2023)](https://pmc.ncbi.nlm.nih.gov/articles/PMC10018377/)
**Document Type:** External Report / Scientific Literature
**Purpose:** Provide peer-reviewed evidence of quality, accuracy, and scientific evaluation of menstrual tracking apps. This evidence complements consumer reports by benchmarking against methodological rigor and health claims.

---

## 1. Summary of Key Findings

* **Quality Assessment**

  * Review identified that many apps are *popular but not scientifically validated*.
  * Few apps meet standards for medical accuracy or transparent intended use.

* **Regulatory Gaps**

  * Only **Natural Cycles** and **Clue Birth Control** had regulatory clearance.
  * Most apps risk misuse for contraception despite disclaimers.

* **Evidence-based Scoring**

  * App quality varied widely across domains (engagement, functionality, aesthetics, information quality).
  * Many scored poorly on **scientific credibility** and **data protection transparency**.

* **Risk of Bias**

  * High reliance on user-entered data undermines prediction reliability.
  * Apps rarely disclose scientific references for algorithms.

---

## 2. Implications for Red Witch

| Requirement / Design Input        | Description                                                             | Linked RMF Risk |
| --------------------------------- | ----------------------------------------------------------------------- | --------------- |
| **DI-011: Evidence Transparency** | All predictive models must cite scientific basis or state if heuristic. | R-Ext-010       |
| **DI-012: Clear Intended Use**    | Explicit disclaimers to prevent misuse as contraception.                | R-Ext-007       |
| **DI-013: Evidence of Accuracy**  | Provide validation results (bench or clinical) in user documentation.   | R-Ext-010       |

---

## 3. Link to Risk Management File

| RMF Risk ID | Source                            | Risk Description                                                 | Mitigation / Control                                   |
| ----------- | --------------------------------- | ---------------------------------------------------------------- | ------------------------------------------------------ |
| R-Ext-007   | Women’s Health (2023), PMC (2023) | Off-label use as contraception despite lack of clearance.        | Disclaimers, no contraceptive marketing.               |
| R-Ext-010   | PMC (2023)                        | Lack of evidence transparency undermines credibility and safety. | Publish model references, disclaimers, accuracy notes. |

---

## 4. Usage

This PMS item informs:

* **SRS – Design Inputs Section**: justification for transparency on scientific basis.
* **RMF**: identification of risk due to lack of evidence validation in market apps.
* **QMS Evidence**: demonstrates monitoring of peer-reviewed evaluations, not just consumer-facing reports.
