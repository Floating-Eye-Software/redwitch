# 📄 Red Witch – Design Input: Modular Calendar Overlays

**Document Name:** *Calendar Overlays System for Fertility & Cultural Frameworks*
**Document Type:** Internal Design Input / Architecture Specification
**Purpose:** Define a modular system that allows users to apply fertility awareness methods (FAM) and cultural/alternative frameworks as “overlays” on the base Red Witch cycle calendar. Supports inclusivity, personalization, and scalability while preserving privacy-first principles.

---

## 1. Summary

Red Witch shall implement a **Calendar Overlays architecture**, enabling multiple frameworks to interpret the same core cycle data.

* **Core calendar = neutral log of dates, symptoms, biomarkers.**
* **Overlays = interpretation layers** (fertility frameworks, cultural calendars, spiritual systems).
* **User control = toggle overlays on/off like map layers.**

This model allows both **evidence-based fertility awareness methods** (e.g., Billings, Symptothermal) and **cultural/spiritual approaches** (e.g., lunar, Wiccan) to coexist in one platform, without bias or data duplication.

---

## 2. Overlays Supported

### 2.1 Fertility Awareness Method (FAM) Overlays

* **Billings Ovulation Method (BOM):** cervical mucus interpretation.
* **Symptothermal Method (STM):** combines basal body temperature + mucus + cervical position.
* **Creighton Model:** standardized mucus charting with symbols.
* **Standard Days Method (SDM):** fixed fertile window overlay.
* **TwoDay Method:** simple yes/no mucus-based overlay.
* **Marquette Method:** adds hormonal testing (if user integrates test results).

### 2.2 Cultural & Alternative Overlays

* **Wiccan / Pagan Calendar:** lunar phases, sabbats, ritual cycles.
* **Lunar/Astrological Cycles:** moon phases, zodiac tracking.
* **Ayurvedic / TCM Cycles:** holistic cycle interpretations (doshas, qi flow).
* **Other cultural frameworks** as suggested by user research and PMS findings.

---

## 3. Technical Requirements

| Requirement ID | Requirement                                                                                                                          | Notes                                          |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------- |
| CO-001         | Core cycle data shall be stored once and interpreted by overlays without duplication.                                                | Ensures data efficiency and privacy.           |
| CO-002         | Users shall be able to enable/disable overlays independently.                                                                        | “Layer toggle” menu in calendar UI.            |
| CO-003         | Overlays shall display transparent layers on top of the core calendar.                                                               | Similar to map layers.                         |
| CO-004         | Each overlay shall include a legend, explanation, and risk disclaimer.                                                               | Regulatory compliance, user clarity.           |
| CO-005         | Overlays shall be modular and extensible, so new frameworks can be added in updates.                                                 | Supports scalability.                          |
| CO-006         | Overlays shall not alter raw user data; only interpret it.                                                                           | Preserves integrity of user logs.              |
| CO-007         | Fertility method overlays (e.g., STM, BOM) shall clearly state whether they are **validated medical methods** or **wellness tools**. | Distinguishes regulated vs. non-regulated use. |

---

## 4. Risk & Compliance Considerations

| Risk ID  | Risk Description                                                      | Mitigation                                          |
| -------- | --------------------------------------------------------------------- | --------------------------------------------------- |
| R-CO-001 | Users may confuse wellness overlays with medical contraceptive tools. | Clear disclaimers; education; informed consent.     |
| R-CO-002 | Overlays may not be culturally appropriate in all contexts.           | Allow opt-in only; no defaults.                     |
| R-CO-003 | Incorrect overlay interpretation could cause unintended pregnancy.    | Education, user manual, and warnings.               |
| R-CO-004 | Overlays add complexity for low-literacy or young users.              | Age-appropriate defaults; ability to hide overlays. |

---

## 5. Usage

This design input informs:

* **SRS:** Add requirements for modular overlay architecture.
* **RMF:** Add overlay-specific risks (e.g., misinterpretation, inappropriate use).
* **QMS Evidence:** Demonstrates inclusive, extensible design aligned with PMS findings and user personas.

---

## 6. Notes

* Implementation should use the **same mechanism** for both FAM and cultural overlays (single “layering” system).
* Overlays should be **future-proof**: easy to add methods or cultural calendars through modular updates.
* Transparent separation between **data (raw logs)** and **interpretation (overlays)** is critical for user trust and regulatory compliance.

---
