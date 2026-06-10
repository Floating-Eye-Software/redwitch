# Red Witch Design Inputs

**Document Type:** Design Input Archive
**Status:** Informational / Historical Design Material
**Authority:** Product Research
**Last Updated:** 2026-06-09

---

# Purpose

This document preserves design explorations, research notes, brainstorming
sessions, regulatory investigations, and architectural ideas that influenced
the development of Red Witch.

The material collected here spans multiple exploratory discussions and should
be treated as design input rather than product requirements.

This document exists to preserve reasoning, context, and lineage.

Nothing in this document should be interpreted as:

* a product requirement,
* a regulatory claim,
* a clinical claim,
* a compliance commitment,
* an approved roadmap item,
* or a commitment to implementation.

Authoritative product decisions belong in the current Red Witch product
documentation.

---

# Relationship To Other Documents

This document informs but does not supersede:

* `docs/product/Red-Witch-Requirements.md`
* `docs/product/Red-Witch-Software-Architecture.md`
* `docs/product/Red-Witch-Threat-Model.md`
* `docs/product/Red-Witch-Privacy.md`
* `docs/product/Red-Witch-Privacy-Assessment.md`
* `docs/product/Red-Witch-Inference-Governance.md`
* `docs/product/Red-Witch-Roadmap.md`

---

# Contents

1. Regulatory Landscape Research
2. Software as a Medical Device Considerations
3. AI Governance Research
4. Privacy and Reproductive Data
5. Financial Incentive Explorations
6. Community Participation Models
7. Lunar Cycle Synchronization Concepts
8. Wellness Reflection Systems
9. Witch Calendar RFC Draft
10. Multi-Calendar Architecture Notes
11. Archived Diagrams
12. Design Lessons

---

# Regulatory Landscape Research

## Overview

One of the earliest design questions surrounding Red Witch was whether a
cycle-tracking application would be regulated as a medical device.

The answer depends primarily on intended use.

A simple cycle journal and wellness tracker may remain outside medical device
classification, while fertility prediction and contraceptive guidance can
trigger substantial regulatory obligations.

---

## Regulatory Domains Identified

### Medical Device Regulation

Potentially relevant frameworks:

| Jurisdiction   | Framework                               |
| -------------- | --------------------------------------- |
| United States  | FDA Software as a Medical Device (SaMD) |
| European Union | MDR 2017/745                            |
| United Kingdom | MHRA                                    |
| Canada         | Health Canada                           |
| Australia      | TGA                                     |

Key observation:

> Small changes in product claims can dramatically change regulatory status.

Examples:

| Product Claim          | Possible Classification  |
| ---------------------- | ------------------------ |
| Cycle journal          | Wellness application     |
| Period tracker         | Wellness application     |
| Fertility predictor    | Medical device candidate |
| Contraceptive guidance | Medical device           |
| Conception assistance  | Medical device           |

---

## Data Protection Frameworks

Research identified the following as potentially relevant:

| Framework   | Jurisdiction                     |
| ----------- | -------------------------------- |
| GDPR        | European Union                   |
| UK GDPR     | United Kingdom                   |
| HIPAA       | United States (limited contexts) |
| CCPA / CPRA | California                       |
| LGPD        | Brazil                           |
| PIPEDA      | Canada                           |

Recurring themes:

* explicit consent
* transparency
* minimization
* user control
* deletion rights
* security by design

---

## AI Regulation

Potentially relevant frameworks:

| Framework          | Scope                   |
| ------------------ | ----------------------- |
| EU AI Act          | High-risk healthcare AI |
| FDA AI/ML Guidance | Medical software        |
| NIST AI RMF        | AI risk management      |

Common expectations include:

* model documentation
* dataset provenance
* validation procedures
* monitoring plans
* explainability
* change control

---

# Software As A Medical Device Considerations

Several investigations focused on where Red Witch sits on the spectrum between:

```text
Wellness Tool
        ↓
Cycle Tracker
        ↓
Fertility Awareness Tool
        ↓
Clinical Decision Support
        ↓
Medical Device
```

The strongest conclusion was that intended use determines classification.

Red Witch's current architecture intentionally separates:

* data collection
* interpretation
* fertility overlays
* symbolic overlays
* educational content

This separation provides flexibility while reducing regulatory ambiguity.

---

# Privacy And Reproductive Data

## Core Observation

Reproductive-health information is among the most sensitive categories of
personal data.

Potential harms include:

* discrimination
* coercion
* intimate partner violence
* reproductive surveillance
* criminalization
* unwanted disclosure

These concerns strongly influenced the Red Witch architecture.

---

## Design Principles Reinforced

Research repeatedly supported:

### Local First

Store data locally whenever possible.

### Data Minimization

Collect only what is necessary.

### User Control

Users remain the primary authority over their information.

### Exportability

Users should be able to leave without losing their history.

### Separation Of Data And Interpretation

Raw observations and derived interpretations should remain distinct.

This principle eventually became one of the core Red Witch architectural ideas.

---

# Financial Incentive Explorations

## Historical Context

Several exploratory discussions considered whether reproductive-health data
could participate in broader community accounting systems.

Examples included:

* points systems
* symbolic economies
* community milestones
* participation rewards
* lunar-cycle accounting

These discussions occurred primarily because of related exploration in the
Pitchfork and Pancakes ecosystems.

---

## Important Note

No cryptocurrency, token, staking, investment, or financial-reward mechanism
is currently part of the Red Witch product.

The concepts below are preserved only as design history.

---

## Observed Regulatory Risks

Exploratory analysis identified substantial risks:

### Financial Regulation

Potential exposure to:

* securities law
* crypto regulation
* AML requirements
* KYC requirements
* consumer protection regulation

### Privacy Risks

Potential concerns include:

* monetization of health data
* secondary use
* exploitation
* coercive incentives

### Ethical Risks

Potential concerns include:

* vulnerable populations
* informed consent
* reproductive autonomy
* fairness

These concerns strongly outweighed perceived benefits.

---

# Community Participation Models

Several concepts explored the idea of collective participation.

Examples included:

* aggregate wellness contributions
* network milestones
* shared achievements
* community learning systems

Conceptually:

```text
Individual Contributions
        ↓
Aggregate Participation
        ↓
Community Milestones
        ↓
Shared Benefits
```

Interesting aspects included:

* cooperative rather than competitive incentives
* community achievement
* collective stewardship

These ideas influenced later Pitchfork discussions more than Red Witch itself.

---

# Lunar Cycle Synchronization Concepts

One design exploration investigated lunar cycles as a community rhythm.

Potential motivations included:

* symbolic resonance
* historical cultural associations
* recurring reflection periods
* shared temporal structure

The concept proposed:

```text
Lunar Cycle
        ↓
Reflection Period
        ↓
Community Milestone
        ↓
New Cycle
```

Importantly:

This was always intended as symbolism rather than biology.

No assumption was made that menstrual cycles and lunar cycles are equivalent.

---

# Wellness Reflection Systems

Several examples explored lightweight reflection and consistency systems.

Illustrative categories included:

* sleep
* exercise
* nutrition
* hydration
* journaling
* mood tracking

Example tier structure:

| Tier     | Example Threshold |
| -------- | ----------------- |
| Bronze   | 150               |
| Silver   | 300               |
| Gold     | 400               |
| Platinum | 500               |

The purpose was reflective engagement rather than competition.

No scoring system is currently part of Red Witch.

---

# RFC Draft: Witch Calendar

## Background

An exploratory RFC-style document proposed a modular calendar architecture
supporting modern witchcraft and Wiccan observances.

The document included:

### Solar Cycle

The Wheel of the Year:

* Samhain
* Yule
* Imbolc
* Ostara
* Beltane
* Litha
* Lammas
* Mabon

### Lunar Cycle

Phases:

* New Moon
* Waxing Moon
* Full Moon
* Waning Moon

### Local Observation

The draft emphasized local observability and decentralized practice.

---

## Architectural Lesson

The most valuable outcome was not the calendar itself.

It was the realization that calendars should be implemented as overlays.

---

# Multi-Calendar Architecture Notes

## Recommended Model

```text
UTC Storage
        ↓
Gregorian Calendar Core
        ↓
Overlay Layer
        ├── Lunar Phase Overlay
        ├── Witch Calendar Overlay
        ├── Regional Holiday Overlay
        ├── Cultural Overlay
        ├── Spiritual Overlay
        └── User Extensions
```

Benefits:

* internationalization
* localization
* user choice
* cultural flexibility

This idea aligns closely with Red Witch's broader overlay architecture.

---

# Archived Diagrams

## Moon-Synced Community Economy Diagram

Historical design artifact:

```text
_work/design-inputs/uteruscoin.png
```

The diagram explored:

```text
User Data
        ↓
Proof Of Data
        ↓
Community Milestones
        ↓
Symbolic Rewards
```

This was an exploratory concept only.

It is preserved for historical reference.

---

## Basal Body Temperature Notes

Historical reference image:

```text
_work/design-inputs/bbt.png
```

This image was collected as design research regarding fertility awareness
methods.

---

# Design Lessons

Several themes repeatedly emerged across these explorations.

## 1. Privacy Is Foundational

Privacy cannot be treated as an optional feature.

It must be a core architectural property.

---

## 2. Data And Meaning Are Different

Raw observations:

```text
temperature
bleeding
symptoms
dates
```

should remain separate from:

```text
fertility interpretations
predictions
symbolic overlays
recommendations
```

This became one of the defining Red Witch principles.

---

## 3. Intended Use Matters

Regulatory classification is driven primarily by intended use and product
claims.

Careful language matters.

---

## 4. Overlays Are Powerful

Calendar overlays, fertility overlays, symbolic overlays, and educational
overlays all emerged from the same architectural insight:

> One dataset can support multiple interpretations without requiring a single
> authoritative meaning.

---

## 5. User Sovereignty Matters

Users should remain the primary authority over:

* their data
* their interpretations
* their exports
* their participation

---

## 6. Symbolism Should Remain Optional

Symbolic systems can be meaningful and valuable.

They should never be mandatory.

---

# Conclusion

This document captures a collection of exploratory paths investigated during
the early development of Red Witch.

Many ideas were discarded.

Some evolved into core architectural principles.

The most durable outcomes were:

* privacy-first design,
* local-first architecture,
* data sovereignty,
* overlay-based interpretation,
* and explicit separation between observation and meaning.

Those principles continue to shape the direction of the project.
