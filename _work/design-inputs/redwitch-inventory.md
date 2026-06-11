# Red Witch Repository and Documentation Inventory

**Inventory date:** 2026-06-06  
**Scope:** Local Red Witch-related repositories, current GitHub repository
state, the `redwitch.ca` apex site, the `www` redirect, docs published under
`/docs/`, and Red Witch authority references in `fley-org`.

## Executive Summary

Red Witch remains an incubating FLEY product, but its visible product
repository and public surfaces still need cleanup. The public `redwitch`
repository was last pushed in September 2022, its committed README contains
only a heading, and the repository now has explicit apex-site and docs routing
instead of a single legacy Pages hostname.

Substantial Red Witch planning did happen after 2022. Most activity occurred in
the Red Witch GitHub wiki during 2024 and 2025. That content was then migrated
into the separate `fley-qms` repository. The newest and most complete Red Witch
document collection is currently in the local `fley-qms` worktree on
`feature/qms-foundation`, including two newer untracked working drafts.

The result is an authority and discoverability problem:

- `redwitch` is intended to be the product repository but contains almost no
  product content.
- `redwitch.wiki` contains useful product documentation but now functions as a
  historical migration source.
- `fley-qms` contains the richest Red Witch product documentation, but
  `Project-Docs/` is absent from its authoritative `main` branch.
- `redwitch/site/` is now the intended apex site source for `redwitch.ca`,
  `www.redwitch.ca` should redirect to the apex, and `redwitch/docs/` is the
  GitHub Pages source for the documentation surface under `/docs/`.
- `fley-org` registers Red Witch as an incubating peer product while still
  recording its active status and classification as needing verification.

No files outside this report were changed during the inventory.

## Current Surfaces

| Surface | Observed State | Current or Intended Role |
| --- | --- | --- |
| `../redwitch/` | Product repository. Six tracked files. Last commit and push on 2022-09-04. Local worktree is dirty. | Intended Red Witch product repository and public site source tree (`site/`), with docs published from `docs/`. |
| `../redwitch.wiki/` | Clean wiki checkout with 16 tracked files. Last commit on 2025-10-29: `archive QMS content, refs #28`. | Historical Red Witch project documentation and original QMS prototype. |
| `../fley-qms/` | Controlled QMS repository. Local branch `feature/qms-foundation`; worktree is dirty and contains newer untracked Red Witch drafts. | FLEY QMS authority, plus the current de facto home of Red Witch product documents. |
| `../fley-qms.bak/` | Approximately 54 MB, 108 files, no commits, and every file untracked. | Legacy QMS backup; not a Red Witch authority. |
| `../fley-org/` | Registers Red Witch as an incubating peer product and product repository candidate. | Portfolio, repository topology, and authority-routing source. |
| `https://redwitch.ca` | NFS/Apache apex site served from `redwitch/site/`; canonical public landing page and entry point. | Intended public Red Witch site. |
| `https://www.redwitch.ca` | Redirects to `https://redwitch.ca`. | Legacy hostname, redirect only. |
| `https://redwitch.ca/docs/` | GitHub Pages docs surface published from `redwitch/docs/`; relative links resolve under `/docs/`. | Active documentation surface. |
| `Floating-Eye-Software/redwitch` | Public GitHub repository with issues, projects, wiki, Pages, and discussions enabled. Twenty open issues observed. | Current GitHub product repository. |
| `mlehotay/redwitch` | Redirects to `Floating-Eye-Software/redwitch`. | Historical repository URL, not a separate repository. |

## Repository Details

### `redwitch`

Local path: `/home/mlehotay/projects/redwitch`  
Remote: `git@github.com:mlehotay/redwitch.git`, which redirects to
`Floating-Eye-Software/redwitch`  
Branch: `main`  
Last commit: `84cfde6 Update CNAME`, 2022-09-04

Tracked content:

- `.github/FUNDING.yml`
- `.gitignore`
- `LICENSE`
- `README.md`
- `docs/CNAME`
- `docs/index.md`

Committed public-site content:

- `docs/CNAME` contains `www.redwitch.ca` from the historical Pages setup.
- `docs/index.md` is a landing page that points to `docs/product/` and notes
  that `redwitch.wiki` is historical.
- The intended final routing is `redwitch.ca` at the apex, `www` redirecting
  to the apex, and GitHub Pages content exposed under `/docs/`.

Local worktree caveats:

- `README.md` has an uncommitted replacement containing a generic project
  README template with unresolved placeholders.
- `undefined - Imgur.png` is an untracked 632 by 474 PNG.
- `site/` is the new static public-site source tree, modeled after the
  `site-ops/site/` layout and kept separate from the documentation tree.
- Neither local change should currently be treated as authoritative product
  content.

Current GitHub metadata observed through the public GitHub API:

- Repository: `Floating-Eye-Software/redwitch`
- Description: `GDPR compliant period tracking app`
- Homepage: `https://redwitch.ca`
- Default branch: `main`
- Created: 2022-07-13
- Last repository push: 2022-09-05 UTC
- Archived: no
- Wiki enabled: yes
- Pages enabled: yes
- Discussions enabled: yes
- Open issues observed: 20

The open Red Witch issues are primarily QMS implementation issues such as
records control, document control, CAPA, design controls, and software
development lifecycle procedures. Recent observed issue updates were in
November 2025, despite the product repository itself not receiving a code push
since 2022.

### `redwitch.wiki`

Local path: `/home/mlehotay/projects/redwitch.wiki`  
Remote: `git@github.com:Floating-Eye-Software/redwitch.wiki.git`  
Branch: `master`  
Last commit: `622d56a archive QMS content, refs #28`, 2025-10-29  
Worktree: clean

The wiki began in July 2022, received process work in 2024, and had substantial
activity from September through October 2025. Its current landing page describes
the wiki as the documentation hub for the Red Witch pilot and points
organization-level policies and SOPs to `fley-qms`.

Current wiki product documents:

- `Red-Witch-Accessibility.md`
- `Red-Witch-Market-Analysis.md`
- `Red-Witch-Market-Comparison.md`
- `Red-Witch-Master-Document-List.md`
- `Red-Witch-Peer-Review.md`
- `Red-Witch-Post-Market-Surveillance.md`
- `Red-Witch-Privacy.md`
- `Red-Witch-Quality-Plan.md`
- `Red-Witch-Requirements.md`
- `Red-Witch-Risk-Management.md`
- `Red-Witch-Roadmap.md`
- `Red-Witch-Software-Architecture.md`
- `Red-Witch-UI-Overlay.md`
- `Red-Witch-Users.md`

All 14 wiki product documents are byte-for-byte identical to their corresponding
copies in the local `fley-qms/Project-Docs/` directory.

The wiki also contains stale or broken authority links:

- One controlled-source link still uses `mlehotay/redwitch/wiki`.
- Numerous master-document-list and post-market-surveillance links use the
  apparently nonexistent `red-witch-org/red-witch` repository path.

The final commit message and migration history support treating the wiki as a
historical source rather than the current editing surface.

Live-site note:

- Reverify the `www` redirect after deployment; the intended final routing is
  apex site plus docs under `/docs/`.

### `fley-qms`

Local path: `/home/mlehotay/projects/fley-qms`  
Remote: `git@github.com:Floating-Eye-Software/fley-qms.git`  
Default branch: `main`  
Current local branch: `feature/qms-foundation`  
Latest local branch commit: `2c70aec first pass at Red Witch threat model`,
2025-12-04

The repository README identifies `fley-qms` as the authoritative system of
record for controlled QMS documentation. Its repository migration plan records
the transition from the Red Witch wiki-based QMS prototype to the dedicated
controlled repository and explicitly calls for separating the Red Witch product
website from the FLEY QMS governance system.

Important branch distinction:

- `main` contains no `Project-Docs/` directory.
- `feature/qms-foundation` contains 16 tracked Red Witch product documents.
- The local worktree contains two additional untracked Red Witch drafts.

Tracked Red Witch documents on `feature/qms-foundation`:

- The same 14 documents present in `redwitch.wiki`
- `Red-Witch-Data-Sovereignty.md`
- `Red-Witch-Threat-Model.md`

Additional untracked Red Witch documents in the local worktree:

- `Red-Witch-Inference-Governance.md`
- `Red-Witch-Privacy-Assessment.md`

The resulting local `Project-Docs/` collection contains 18 Red Witch documents
and approximately 20,000 words. It is the newest and most complete Red Witch
document set found during this inventory.

The local `fley-qms` worktree also contains unrelated untracked
`Can-They-Eat-This` project documents and a workflow implementation note.
These should not be confused with Red Witch content.

### `fley-qms.bak`

Local path: `/home/mlehotay/projects/fley-qms.bak`

Observed state:

- Approximately 54 MB
- 108 files
- Git repository initialized but no commits exist
- All content is untracked
- Mostly legacy QMS drafts, diagrams, images, and external reference PDFs

This directory may contain useful historical QMS source material, but it is not
a reliable or controlled Red Witch source. It should be explicitly archived or
removed only after unique-content review.

### `fley-org`

Relevant records:

- `projects/projects.csv` lists Red Witch as `incubating`, with `redwitch` as
  its primary repository.
- `projects/repositories.csv` classifies `redwitch` as a candidate product peer
  repository whose active status and classification need verification.
- The May 2026 monthly readout describes Red Witch as a health-adjacent,
  cycle-tracking branch requiring unusually strong privacy, local-first
  storage, overlay-based interpretation, and reproductive-risk threat modeling.
- The active FLEY QMS content-migration plan identifies
  `fley-qms/Project-Docs/Red-Witch-*.md` as product and portfolio material that
  needs classification and routing without confusing working input with
  approved strategy.

This establishes that Red Witch remains part of current portfolio planning even
though its product repository and website do not show that state.

## Additional Red Witch-Related Material

The following local files also reference or contain Red Witch material, but are
not primary product-document sources:

- `../chatgpt-tool/data/RedWitch_Compliance_Matrix_Updated.md`
- `../chatgpt-tool/data/Quality_Plan_Phase1.md`
- `../chatgpt-tool/data/DSS_Compliance_Mapping.md`
- `../site-ops/_work/drafts/old-redwitch-design.txt`
- `mentors/redwitch-profile.md`
- `mentors/red-witch.png`

These should be reviewed as supporting inputs, historical drafts, or
cross-project context rather than silently promoted to authority.

## Content Lineage

The observed Red Witch documentation lineage is:

1. The `redwitch` product repository was created on GitHub in July 2022.
2. Activity moved into the repository wiki, initially for project material and
   later for QMS development.
3. The wiki received substantial updates during September and October 2025.
4. QMS content was migrated from `redwitch.wiki` into the new `fley-qms`
   repository, preserving history through migration branches.
5. The 14 surviving wiki product documents were copied unchanged into
   `fley-qms/Project-Docs/`.
6. Additional Red Witch product and risk documents were developed on
   `fley-qms/feature/qms-foundation`.
7. The newest inference-governance and privacy-assessment drafts currently
   exist only as untracked files in the local `fley-qms` worktree.

## Authority Findings

### Observed Authority

- `fley-qms/main` is the stated authority for controlled QMS documents.
- `fley-org` is the authority for organization-level portfolio status and
  repository topology.
- `redwitch` is registered as the Red Witch product repository.
- The most complete Red Witch product content is nevertheless located in a
  non-default `fley-qms` feature branch and local untracked files.

### Resulting Problems

- The intended product repository does not explain the product or route readers
  to current documentation.
- The public website gives no indication that Red Witch is part of current
  planning.
- The wiki appears like the project documentation hub but lacks newer material
  and has an archival migration commit.
- The richest document collection is difficult to discover and not present on
  `fley-qms/main`.
- Product documentation and controlled QMS authority are mixed together.
- Red Witch issues remain populated with organization-level QMS work that now
  belongs in `fley-qms`.
- Broken and historical repository links obscure the actual current locations.
- Dirty and untracked local worktrees contain potentially important material
  that is not protected by remote history.

## Recommended Authority Model

| Authority Area | Recommended Source |
| --- | --- |
| Red Witch product identity, source, roadmap, requirements, architecture, privacy design, and project working documents | `redwitch` repository |
| Public-facing product overview and selected documentation | `redwitch/site/` for the apex overview, plus `redwitch/docs/` published under `/docs/` |
| Historical Red Witch wiki and migration history | `redwitch.wiki`, clearly marked archived/read-only |
| Controlled QMS processes, SOPs, work instructions, templates, compliance mappings, approvals, and quality records | `fley-qms` |
| Portfolio status, repository ownership, and authority routing | `fley-org` |
| Legacy uncommitted QMS backup | Explicit archive outside active authority surfaces |

Red Witch-specific quality plans or controlled records may remain in
`fley-qms` when their controlled status requires it. Product design and
planning documents should live in `redwitch`, with links to controlled QMS
records rather than duplicate uncontrolled copies.

## Recommended Cleanup Sequence

1. Protect current work before moving anything.

   Review and commit or otherwise preserve the untracked Red Witch inference
   governance and privacy assessment documents in `fley-qms`. Do not delete or
   overwrite the existing dirty worktrees.

2. Decide document-by-document authority.

   Classify every `fley-qms/Project-Docs/Red-Witch-*.md` file as product
   planning, controlled quality record, external design input, or historical
   material. This classification should determine whether it moves to
   `redwitch`, remains in `fley-qms`, or is linked from both.

3. Restore the `redwitch` repository as the product entry point.

   Replace the placeholder README with a concise current product overview,
   lifecycle state, authority map, documentation index, and links to relevant
   QMS records. Resolve the unexplained untracked image separately.

4. Make `redwitch.ca` useful.

   Keep `redwitch/site/` as the public apex landing page that explains the
   privacy-first cycle-tracking concept, current incubating status, and where
   current documentation and governance records live. Keep `redwitch/docs/`
   as the GitHub Pages documentation source under `/docs/`.

5. Move or reconstruct current product documentation under `redwitch`.

   Preserve history where practical. Avoid maintaining independent editable
   copies in both `redwitch` and `fley-qms`.

6. Archive the wiki clearly.

   Keep `redwitch.wiki` for historical traceability, but replace its landing
   page with a migration notice and links to current product and QMS sources.
   Disable wiki editing if appropriate.

7. Re-home stale QMS issues.

   Review the 20 open Red Witch issues. Transfer or recreate organization-level
   QMS work in `fley-qms`; retain only actual Red Witch product work in the
   product repository.

8. Repair links and identifiers.

   Replace obsolete `mlehotay/redwitch` controlled-source references where the
   redirect is undesirable, and remove broken `red-witch-org/red-witch` links.

9. Reconcile portfolio records.

   Update `fley-org` after the product authority and lifecycle state are
   confirmed, replacing the current “candidate / needs verification” language
   with the decided state.

10. Review and archive `fley-qms.bak`.

    Compare it for unique material, preserve anything required, and then move
    it out of the active project workspace or document it explicitly as a
    historical archive.

## Suggested End State

A reader arriving at any Red Witch surface should be routed consistently:

- GitHub product repository: what Red Witch is, its current status, and where
  to work on it.
- `redwitch.ca`: public product explanation and selected public documentation
  from the apex site, with docs under `/docs/`.
- Product documents: one editable authoritative location under `redwitch`.
- QMS records: controlled sources under `fley-qms`.
- Portfolio state: concise authoritative entry under `fley-org`.
- Wiki and backups: clearly historical, retained only for traceability.
