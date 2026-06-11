# Red Witch Initialization Notes

**File:** `_work/notes/redwitch-init-notes.md`
**Status:** Working Context Note
**Audience:** Future maintainers, Codex sessions, repository restoration work

---

# Purpose

This note provides historical and architectural context for the current Red
Witch repository restoration effort.

Red Witch is being transitioned from an abandoned-looking historical
repository into a normal FLEY planning repository with the same workflow,
authority model, and planning surfaces used by projects such as:

* Pancakes
* Pitchfork
* Resonance

This note exists to help future Codex sessions understand the unusual history
of the repository and avoid accidentally destroying provenance or creating
competing authorities.

---

# What Is Red Witch?

Red Witch is a privacy-first cycle tracking and reproductive health project.

Historically it was described as:

> GDPR-compliant period tracking app

but the current conception is broader.

Red Witch is now understood as:

* cycle tracking
* symptom tracking
* reproductive-health journaling
* fertility-awareness support
* privacy-preserving health records
* interpretation overlays
* reproductive-data sovereignty

The project is explicitly designed around:

* local-first principles
* privacy by default
* user sovereignty
* consent
* data minimization
* exportability
* anti-surveillance design

The project should be viewed as part of the broader FLEY ecosystem rather than
a standalone startup application.

---

# Relationship To The FLEY Ecosystem

Red Witch is one member of a larger collection of projects.

Current major peers include:

* Pancakes
* Pitchfork
* Resonance

Red Witch is not a Pitchfork client.

Red Witch is not a Pancakes module.

Red Witch is a separate product that shares:

* values
* governance
* workflow
* architectural principles

with the broader ecosystem.

Important recurring ideas include:

* data sovereignty
* local ownership
* overlays
* privacy-first design
* anti-extractive software
* humane computing

---

# Repository History

The repository was created in 2022.

Public development largely stopped shortly afterward.

As a result:

* GitHub shows little recent activity.
* The repository appears abandoned.
* The public website contained only a placeholder page.

However, actual Red Witch development continued elsewhere.

The majority of later work occurred in:

```text
redwitch.wiki
```

followed by:

```text
fley-qms
```

The result was an authority problem:

* the official product repository looked abandoned
* the wiki appeared current
* the most complete document collection lived in a QMS repository
* the public website contained almost nothing

The current restoration effort exists to correct this situation.

---

# Current Restoration Goal

The goal is:

> Restore redwitch as the authoritative home for Red Witch product work.

The intended authority model is:

| Area                   | Authority     |
| ---------------------- | ------------- |
| Product identity       | redwitch      |
| Product documentation  | redwitch      |
| Requirements           | redwitch      |
| Architecture           | redwitch      |
| Privacy design         | redwitch      |
| Inference governance   | redwitch      |
| Threat model           | redwitch      |
| Roadmap                | redwitch      |
| Public website content | www.redwitch.ca |
| Documentation site     | docs.redwitch.ca |
| QMS procedures         | fley-qms      |
| Compliance records     | fley-qms      |
| Controlled processes   | fley-qms      |
| Portfolio status       | fley-org      |
| Hosting and deployment | site-ops      |
| Historical archive     | redwitch.wiki |

---

# Current Repository State

As of the restoration effort:

```text
docs/product/
```

contains the current Red Witch document collection.

The repository now contains product documents that previously lived in:

* redwitch.wiki
* fley-qms

including:

* requirements
* architecture
* threat model
* roadmap
* privacy
* accessibility
* risk management
* market analysis
* data sovereignty
* inference governance
* privacy assessment

The migration is intentionally moving authority into this repository.

Future work should avoid creating duplicate editable copies elsewhere.

---

# Important Authority Rule

A document should have exactly one editable authority.

Historical copies may remain elsewhere.

Reference copies may remain elsewhere.

Editable copies should not exist in multiple repositories.

When authority is unclear:

1. Determine intended owner.
2. Move authority there.
3. Replace duplicate content with links.

---

# The Wiki

The wiki is being converted into a historical archive.

Historically:

```text
redwitch.wiki
```

contained active project documentation.

That is no longer the intended role.

The desired future state is:

* preserve history
* preserve provenance
* preserve links
* route readers to current sources

The wiki should not remain an active documentation authority.

---

# The Public Website

Current deployment:

```text
site/
  ↓
www.redwitch.ca

docs/
  ↓
GitHub Pages
  ↓
docs.redwitch.ca
```

Historically the website contained almost no content.

One objective of the restoration effort is to turn the public site into a
useful project page and keep the documentation site separate.

The website should explain:

* what Red Witch is
* current project status
* privacy philosophy
* documentation routes
* authority boundaries

without making uncontrolled medical or regulatory claims.

---

# Design Philosophy

Several principles repeatedly emerged during project development.

## Privacy First

Privacy is a core architectural requirement.

It is not an optional feature.

---

## Local First

Users should retain meaningful control over their data.

---

## Data Sovereignty

Users should:

* own their data
* export their data
* delete their data
* understand their data

---

## Data Is Not Meaning

A foundational Red Witch idea is:

```text
Observation
≠
Interpretation
```

Examples:

```text
temperature
bleeding
symptoms
```

are observations.

Examples:

```text
fertility prediction
cycle phase
health insight
```

are interpretations.

These should remain separable.

---

## Overlay Architecture

Interpretations should be implemented as overlays whenever possible.

Examples:

* fertility-awareness overlay
* educational overlay
* symbolic overlay
* cultural overlay
* calendar overlay

This allows multiple interpretations without altering the underlying data.

---

# Design Inputs

Historical brainstorming and research have been collected under:

```text
_work/design-inputs/
```

These materials:

* preserve design lineage
* preserve research
* preserve discarded ideas

They are not authoritative requirements.

Notable design-input topics include:

* medical-device regulation
* privacy law
* AI governance
* lunar calendars
* fertility awareness
* symbolic overlays
* community participation systems

Future maintainers should avoid treating design-input documents as approved
product decisions.

---

# Workflow Installation

Red Witch is being converted into a normal FLEY planning repository.

The expected outcome is similar to:

```text
pancakes
pitchfork
resonance
```

The repository should eventually contain:

```text
AGENTS.md
_work/repo-workflow.md
_work/local-workflow.md
_work/plans/plans.csv
_work/todo.csv
_work/codex-log.md
```

alongside existing plans and notes.

Workflow policy is owned by:

```text
../fley-org
```

and should not be forked casually.

---

# Immediate Open Work

Expected near-term tasks include:

1. Install repository workflow.
2. Create planning dashboards.
3. Register existing plans.
4. Convert wiki into archive.
5. Repair authority routing.
6. Improve README.
7. Improve public website.
8. Reconcile repository ownership records.
9. Verify authority boundaries.
10. Establish Red Witch as a normal FLEY planning project.

---

# Guidance For Future Codex Sessions

Before making major changes:

1. Read:

   * `_work/plans/0001-red-witch-product-restoration.md`
   * `_work/redwitch-inventory.md`
   * this document

2. Determine the current authority of any document being modified.

3. Avoid creating duplicate editable authorities.

4. Preserve provenance whenever practical.

5. Prefer routing and clarification over duplication.

The primary objective is not merely moving files.

The primary objective is restoring a coherent authority model for the project.
