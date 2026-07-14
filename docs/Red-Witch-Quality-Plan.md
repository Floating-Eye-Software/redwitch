# **PLAN - Red Witch – Project Quality Plan (PQP)**

**Slug:** Red-Witch-Quality-Plan  
**Revision:** r1  
**Effective Date:** [YYYY-MM-DD]  
**Related SOP:** Project-Management-SOP  
**Controlled Source:** https://github.com/mlehotay/redwitch/wiki/Red-Witch-Quality-Plan  

---

**Project Manager / Owner:** [Name]

> This PQP defines how the **Red Witch** project implements the **Floating Eye Software (FLEY) QMS**, including configuration of SOPs, Work Instructions (WIs), and tools used to achieve compliance.

---

## **1. QMS Activity Configuration**

Each project defines its own QMS implementation “stack.”
All SOPs remain in effect; this table specifies the **selected methods, tools, and WIs** used to meet each SOP for *Red Witch*.

| SOP / QMS Activity                           | Selected Work Instruction / Framework                                                                                       | Tool / Platform             | Notes / Comments                                                                        |
| -------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | --------------------------- | --------------------------------------------------------------------------------------- |
| **QMS-SOP-02 Change Control**                | `WIs/GitHub/GitHub-Change-Control.md`                                                                                       | GitHub (PR Workflow)        | All change requests handled through pull requests with mandatory reviews.               |
| **QMS-SOP-05 Document Control**              | `WIs/GitHub/GitHub-Document-Control.md`, `WIs/GitHub/GitHub-Version-Control.md`                                             | GitHub Wiki / Repo          | Controlled via PR approvals and branch protection; revisions auto-tracked.              |
| **QMS-SOP-06 Quality Planning**              | `Project-Docs/Red-Witch-Quality-Plan.md`                                                                                           | PQP in GitHub Wiki              | Defines objectives, risk linkage, and review cadence.                       |
| **QMS-SOP-07 Project Management**            | `WIs/GitHub/GitHub-Project-Management.md`                                                                                   | GitHub Projects             | Milestones, boards, and Issues used for schedule and progress control.                  |
| **QMS-SOP-08 Risk & Opportunity Management** | FLEY Risk Framework *(current)* → planned migration to **ISO 14971**                                                        | GitHub Issues + Wiki        | Each risk logged and tracked; linked to DCP and verification evidence.                  |
| **QMS-SOP-09 Design & Development Control**  | `WIs/Ontario-Design-Framework/Ontario-Service-Design-WI.md` *(primary)* + `WIs/FLEY/FLEY-Design-Control-WI.md` *(parallel)* | GitHub Wiki / Repo          | Ontario Design Framework governs design stages; FLEY WI ensures regulated traceability. |
| **QMS-SOP-10 Continuous Improvement / CAPA** | `WIs/GitHub/GitHub-QMS-Operations.md`                                                                                       | GitHub Issues / Discussions | CAPA issues tracked to closure; linked to audits and retrospectives.                    |
| **Information Security (NIST Alignment)**    | `WIs/NIST/Information-Security.md`                                                                                          | GitHub Access Control / CI  | Access control and security aligned with NIST principles.                               |

**Configuration Rules**

* All QMS activities must be executed using the selected methods/tools.
* Configuration must be reviewed and approved by **PM** and **Quality Manager** before project start.
* Updates require a **Change Request** per SOP-02.
* Applicable standards determined by **intended use** and **regulatory classification**.

---

## **2. Governance & Quality Planning**

**Objectives**

* Maintain complete bidirectional traceability: Requirements ↔ Design ↔ Implementation ↔ Verification ↔ Validation.
* ≥95 % unit test pass rate before release; ≥80 % code coverage.
* All high-risk features undergo formal design and risk review.

**Planning**

* Milestones and reviews per **Ontario Design Framework (ODF)** and **FLEY SDLC**.
* Sprint retrospectives for continuous improvement.
* KPIs tracked in GitHub dashboards and trace matrices.

---

## **3. Document & Record Control**

* Documentation maintained in **GitHub Wiki**, pull requests, and CI/CD pipelines.
* Controlled via PR approvals and revision history.
* Releases tagged in GitHub for baseline control.
* Verification/Validation evidence linked to DCP checkpoints.

---

## **4. Training & Competence**

* All contributors complete QMS, GDPR, and security training.
* Repository access contingent on training completion.
* Training logs stored in the Wiki.

---

## **5. Risk Management**

* Risks tracked in GitHub Issues and Wiki.
* Linked directly to requirements and design controls.
* Reviewed during design and milestone reviews.
* Migration to ISO 14971 planned for formal risk categorization.

---

## **6. Design & Development Control**

* Requirements, design, implementation, and V&V managed via GitHub Issues, PRs, and test reports.
* Design reviews held at each milestone and recorded in the Wiki.
* DCP deliverables per phase:

  | Phase                   | Deliverables                              |
  | ----------------------- | ----------------------------------------- |
  | Design Planning         | DCP, Risk Register                        |
  | Requirements            | Approved backlog, SRS                     |
  | Design & Implementation | Architecture, detailed design, code       |
  | Verification            | Test plans, reports                       |
  | Validation              | Validation protocol, stakeholder approval |
  | Release                 | Release notes, post-release review        |

**Reference:** *Design Control Plan (DCP) – Red Witch*

---

## **7. Change & Configuration Management**

* GitHub branch protections enforce controlled configuration.
* Pull requests + linked Issues = change control records.
* Baselines tagged per release.
* Impacts assessed via Trace Matrix and DCP documentation.

---

## **8. Supplier & External Resource Management**

* No qualified suppliers at this time.
* Open-source dependencies tracked via GitHub’s dependency management and license scanning.

---

## **9. Production, Release & Deployment**

* Releases documented with notes, GitHub tags, and DCP compliance links.
* Disaster recovery tested pre-release.
* Issue backlog reviewed prior to deployment.

---

## **10. Verification, Validation & Testing**

* Automated CI/CD executes unit, integration, regression tests.
* Test evidence archived in pipelines and cross-linked to requirements.
* Validation performed with stakeholders; results in validation reports.

---

## **11. Nonconformance & CAPA**

* CAPA items tracked as GitHub Issues (CAPA label).
* Root cause analysis for repeated or high-risk issues.
* Linked to SOP/WI updates when applicable.

---

## **12. Audit & Continuous Improvement**

* Internal audits every 6 months.
* Findings logged in Wiki or GitHub Issues.
* Retrospectives feed CAPA and process updates.
* ISO 9004 and GDPR milestones used for continuous improvement.

---

## **13. Customer & Stakeholder Feedback**

* Feedback from usability tests, design reviews, workshops.
* Logged as Issues; linked to CAPA or backlog refinement.
* Integrated into release planning.

---

## **14. Infrastructure, Security & Work Environment**

* GitHub Repos + CI/CD serve as core infrastructure.
* GDPR/HIPAA/privacy considerations included in design.
* Access control enforced via GitHub org permissions.
* Security managed per `WIs/NIST/Information-Security.md`.

---

## **15. Regulatory & Standards Reference**

**Primary Standards**

* ISO 13485:2016 — Medical Device QMS
* IEC 62304 — Software Lifecycle
* IEC 62366 — Usability Engineering
* ISO 9001:2015 — Quality Management
* GDPR / HIPAA / EU MDR

**Supporting Standards**

* IEC 82304-1:2016 — Health Software Product Safety
* ISO/TS 82304-2:2021 — Health & Wellness Apps
* ISO/IEC 27001 & 27701 — Information & Privacy Security
