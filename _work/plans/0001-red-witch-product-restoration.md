# 0001 - Red Witch Product Restoration

## Goal

Restore `redwitch` as the authoritative and discoverable home for Red Witch
product work while preserving the historical wiki and QMS migration trail.

## Authority And Related Work

This repository is authoritative for Red Witch product identity, requirements,
architecture, privacy design, inference governance, threat model, roadmap,
product issues, user documentation, and public-site content.

Related coordination and execution plans:

- `fley-org/_work/plans/0008-red-witch-rescue.md`
- `site-ops/_work/plans/0011-product-site-deployment.md`

`fley-qms` remains authoritative for controlled QMS processes, compliance
mappings, approvals, audits, and quality records. `site-ops` remains
authoritative for domain, hosting, deployment, redirect, backup, TLS, and
live-site verification.

## Problem

The Red Witch repository and public website look abandoned even though
substantial product planning exists. Current material is fragmented across:

- `redwitch.wiki`
- `fley-qms/Project-Docs/` on `feature/qms-foundation`
- untracked local Red Witch drafts in `fley-qms`
- historical and supporting material in other repositories

The product repository also has existing uncommitted changes that must be
reviewed rather than overwritten:

- a generic placeholder replacement for `README.md`
- an untracked `undefined - Imgur.png`

## Scope

In scope:

- classify Red Witch documents by authority and status
- create a coherent product-document structure in `redwitch`
- migrate or reconstruct authoritative product documents with provenance
- replace the placeholder repository README
- define and write the `www.redwitch.ca` public-site content
- reconcile Red Witch product issues
- convert the wiki into a clearly historical archive
- leave controlled QMS records and approvals in `fley-qms`
- repair broken and historical links

Out of scope:

- production deployment, DNS, redirects, TLS, or live-root backups
- bypassing QMS review for regulated, privacy, health, safety, compliance, or
  regulatory claims
- deleting the wiki, issue history, QMS records, or backups
- silently overwriting existing dirty worktrees

## Proposed Repository Shape

The final structure should be chosen after classification. A likely shape is:

```text
README.md
docs/
    index.md
    vision.md
    requirements/
    architecture/
    privacy/
    governance/
    risk/
    research/
    roadmap/
_work/
    plans/
```

`site/index.html` should serve as the public-site entry point, while
`docs/index.md` should provide a clear route to the broader product
documentation. Public output must distinguish working drafts from reviewed or
controlled claims.

## Work Plan

1. Protect and inventory current work.

   Review the dirty `redwitch` and `fley-qms` worktrees. Preserve important
   untracked Red Witch drafts before migration. Use the organization inventory
   as a starting point, but verify every source file.

2. Classify candidate documents.

   For every Red Witch document in `redwitch.wiki`,
   `fley-qms/Project-Docs/`, and supporting source areas, record:

   - classification: product, controlled QMS, historical, mixed, or supporting
   - current authority
   - intended destination
   - status: working draft, reviewed, controlled, superseded, or archive
   - provenance and required QMS review

3. Establish the product documentation structure.

   Create a navigable structure that keeps product design, research, privacy,
   governance, risk, and roadmap material understandable without making
   uncontrolled compliance claims.

4. Migrate product authority.

   Move or reconstruct authoritative product documents under `redwitch`.
   Preserve source attribution, dates, document identifiers, and links to
   controlled records where appropriate. Avoid maintaining competing editable
   copies.

5. Restore the repository entry point.

   Replace the placeholder README with a current product overview, lifecycle
   state, authority map, documentation index, contribution route, and links to
   relevant QMS records. Resolve the unexplained untracked image separately.

6. Prepare the public website content.

   Replace the current one-heading page with a small, accurate site explaining
   the product concept, incubating state, privacy posture, documentation, and
   project relationship to FLEY. Route claims requiring controlled review to
   `fley-qms` before publication.

7. Reconcile product issues.

   Keep actual Red Witch product work in this repository. Mark historical QMS
   realization issues clearly and route ongoing organization-level QMS work to
   `fley-qms` without deleting issue history.

8. Archive the wiki clearly.

   Add an archive and migration notice that routes readers to current Red Witch
   product documentation and current FLEY QMS sources. Preserve wiki history.

9. Remove duplicate product authority from `fley-qms`.

   After current product sources are established, route any required QMS
   cleanup through its controlled workflow. Do not remove controlled records or
   evidence merely because related product material moved.

10. Verify discoverability and authority.

    Confirm that the repository, public-site source, wiki, issues, and QMS
    references consistently route readers to the correct current sources.

## Acceptance Criteria

- `redwitch` contains the authoritative Red Witch product documents
- the README accurately explains the product, status, and authority boundaries
- public-site content is current and ready for `site-ops` deployment
- product issues are distinguishable from historical QMS issues
- the wiki is clearly historical and routes to current sources
- controlled QMS records remain governed by `fley-qms`
- document provenance is preserved
- broken and obsolete authority links are repaired
- current product work no longer requires discovering a non-default QMS branch

## Verification Of Effectiveness

Use this section near closure.

Objectives achieved:

- TBD

Evidence:

- TBD

Residual risks:

- TBD

Follow-on actions:

- TBD

Lessons learned:

- TBD

## Status

Ready.
