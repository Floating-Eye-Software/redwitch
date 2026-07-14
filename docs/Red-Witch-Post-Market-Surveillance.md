# 📄 Red Witch – Post-Market Surveillance (PMS) Log

**Purpose:**
The Post-Market Surveillance (PMS) log tracks external reports, user feedback, and research findings relevant to Red Witch. PMS ensures continuous monitoring of safety, privacy, usability, and regulatory compliance, feeding improvements into the SRS, RMF, and QMS.

**Procedure Reference:** RW-QMS-005 – Post-Market Surveillance Procedure

**Last Updated:** 2025-10-02
**Owner:** QA/RA Manager

---

## 1. PMS Log Table

| PMS ID  | Source                                                      | Type                                    | Summary                                                                                                                                                       | Related RMF / SRS               | Action / Status                                                                                            | Review Date | Owner           | Link                                                                                                                             |
| ------- | ----------------------------------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------- | ---------------------------------------------------------------------------------------------------------- | ----------- | --------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| PMS-001 | Cambridge Report – Minderoo Centre, 2025                    | External Report / Risk                  | Commercial exploitation of menstrual data by profit-driven cycle tracking apps; privacy, safety, and reproductive rights risks.                               | R-Ext-001, R-Ext-002, R-Ext-003 | Include in RMF and SRS as design input; monitor for regulatory updates                                     | 2025-10-30  | QA/RA           | [Link to Design Input](https://github.com/red-witch-org/red-witch/wiki/Cambridge-Menstrual-Tracking-Report)                      |
| PMS-002 | PMC Review of 49 Studies, 2023                              | External Report / Design Input          | Language barriers, technology access limitations, digital literacy challenges, and cultural sensitivity affecting global adoption of menstrual tracking apps. | DI-001 to DI-006                | Include in SRS and RMF; monitor user adoption metrics                                                      | 2025-10-30  | Product Team    | [Link to Design Input](https://pmc.ncbi.nlm.nih.gov/articles/PMC8162175/)                                                        |
| PMS-003 | Women’s Health – Best Period Tracker Apps, 2023             | Market Report                           | Comparison of 11 leading apps; highlights FDA clearance gaps, user frustration with monetization, privacy concerns, and new usability features.               | R-Ext-007, R-Ext-008, R-Ext-009 | Add warnings for off-label use; monitor reviews for monetization/privacy; evaluate future roadmap features | 2025-10-30  | QA/RA + Product | [Existing Solutions & Market Comparison](https://github.com/red-witch-org/red-witch/wiki/Existing-Solutions-&-Market-Comparison) |
| PMS-004 | Peer-Reviewed Review of Menstrual Tracking Apps (PMC, 2023) | External Report / Scientific Literature | Academic evaluation of app quality; found limited scientific validation, evidence gaps, and risks of off-label contraceptive use.                             | R-Ext-007, R-Ext-010            | Update SRS for evidence transparency; disclaimers on accuracy and intended use                             | 2025-10-30  | QA/RA           | [PMC Article](https://pmc.ncbi.nlm.nih.gov/articles/PMC10018377/)                                                                |

---

## 2. PMS Workflow

1. **Identification**

   * Sources: Academic research, media reports, regulatory alerts, user feedback, app store reviews.
   * Assign a unique **PMS ID** to each item.

2. **Documentation**

   * Record source, type, summary, potential risk or design input, linked RMF/SRS references, and owner.

3. **Evaluation**

   * Determine if the item represents a **risk**, a **new design input**, or both.
   * Assign to appropriate team (QA/RA, Product, Development).

4. **Action / Mitigation**

   * Update RMF, SRS, or QMS procedures as necessary.
   * Monitor and track outcomes (e.g., app updates, user education materials).

5. **Review & Reporting**

   * Conduct PMS reviews quarterly or after major findings.
   * Record updates, new actions, and status in this log.

---

## 3. Notes

* All PMS items must be version-controlled in accordance with **RW-QMS-002 – Document Control Procedure**.
* External reports should **not be copied in full**; provide a summary and a link to the source.
* PMS entries can be linked directly to **Design Input Wiki pages** for traceability.

---

## 4. Future Expansion

* Add **user complaints** as they are received.
* Include **regulatory alerts or safety notices** relevant to data privacy, medical device classification, or digital health regulations.
* Track **post-release app metrics**, such as adoption rates, crashes, or reported privacy issues.
