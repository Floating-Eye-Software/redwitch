## 📄 Red Witch – External Design Input: Global Accessibility and Equity in Menstrual Tracking Apps

**Document Name:**
"Review of 49 Studies on Menstrual Cycle Tracking Apps: Women's Needs, Language Barriers, and Technology Access"
**Source / Link:**
[PMC Article: Women's Comfort with Mobile Applications for Menstrual Cycle Tracking](https://pmc.ncbi.nlm.nih.gov/articles/PMC10839505/)
**Document Type:**
External Design Input / Market & Equity Evidence
**Purpose:**
Provide evidence of global accessibility challenges, language and technology barriers, and diverse user needs in the context of menstrual cycle tracking apps. Used to inform inclusive design requirements and risk management in the Red Witch project.

---

### 1. Summary of Key Findings

* **Global Usage Patterns:**
  A systematic review of 49 studies highlighted that while menstrual cycle tracking apps are widely used, their adoption varies significantly across regions, influenced by factors such as digital literacy, access to technology, and cultural perceptions of menstruation.

* **Language Barriers:**
  Many apps are predominantly available in English, limiting accessibility for non-English-speaking populations. This linguistic gap can lead to misunderstandings and reduced usability among diverse user groups.

* **Technology Access:**
  Access to smartphones and the internet is uneven across regions. In low-resource settings, women may face challenges such as limited device access, unreliable internet connectivity, and lack of digital literacy, hindering the effective use of menstrual tracking apps.

* **Cultural Sensitivity:**
  Cultural norms and taboos surrounding menstruation can affect the willingness of women to use digital health tools. Apps that do not consider cultural contexts may face resistance or misuse.

---

### 2. Implications for Red Witch Design

Based on the findings, Red Witch shall implement the following **design inputs / requirements**:

| Requirement / Design Input            | Description                                                                                                                  | Linked RMF Risk |
| ------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- | --------------- |
| **DI-001: Multilingual Support**      | Develop the app in multiple languages to cater to diverse populations.                                                       | R-Ext-001       |
| **DI-002: Offline Functionality**     | Ensure core features are accessible without an internet connection.                                                          | R-Ext-002       |
| **DI-003: User Education**            | Provide tutorials and resources to improve digital literacy among users.                                                     | R-Ext-003       |
| **DI-004: Cultural Sensitivity**      | Design the app to be culturally appropriate and sensitive to various societal norms.                                         | R-Ext-004       |
| **DI-005: Accessibility Features**    | Implement features such as voice commands, screen readers, and adjustable font sizes to accommodate users with disabilities. | R-Ext-005       |
| **DI-006: Data Privacy and Security** | Ensure compliance with global data protection regulations and provide users with control over their data.                    | R-Ext-006       |

---

### 3. Link to Risk Management File

External risks identified from the review have been added to the RMF:

| RMF Risk ID | Source             | Risk Description                                                               | Mitigation / Control                                                        |
| ----------- | ------------------ | ------------------------------------------------------------------------------ | --------------------------------------------------------------------------- |
| R-Ext-001   | PMC Article (2023) | Limited language support leading to reduced accessibility.                     | Implement multilingual support.                                             |
| R-Ext-002   | PMC Article (2023) | Inadequate offline functionality hindering app usage in low-resource settings. | Ensure core features are accessible offline.                                |
| R-Ext-003   | PMC Article (2023) | Low digital literacy among users affecting app adoption and usage.             | Provide user education and tutorials.                                       |
| R-Ext-004   | PMC Article (2023) | Cultural insensitivity leading to resistance or misuse of the app.             | Design culturally sensitive interfaces and content.                         |
| R-Ext-005   | PMC Article (2023) | Lack of accessibility features excluding users with disabilities.              | Implement accessibility features such as voice commands and screen readers. |
| R-Ext-006   | PMC Article (2023) | Non-compliance with global data protection regulations.                        | Ensure compliance with data privacy laws and provide user data control.     |

---

### 4. Usage

This external design input informs:

* **SRS – Design Inputs Section:** Justification for inclusive design features.
* **RMF:** Identification of external risks and linkage to mitigations.
* **QMS Evidence:** Demonstrates consideration of global accessibility challenges in risk-based design.
