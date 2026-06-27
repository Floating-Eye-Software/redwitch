# Red Witch Codex Log

Concise append-only summaries for Codex sessions.

Use this when a session changes source files, closes a task, records findings
that future sessions need, or establishes project setup.

Entry shape:

```text
---

# codex-NNN - Short Title

**Plan:** `plan-id`
**Priority:** Pn
**Status:** recorded
**Timestamp:** YYYY-MM-DD HH:MM TZ

## Changes

...
```

---

# codex-001 - Website and Docs Cleanup

**Plan:** `ad hoc`
**Priority:** P2
**Status:** recorded
**Timestamp:** 2026-06-10 20:25 EDT

## Changes

Cleaned up the Red Witch public site and docs routing without adding a full
repo workflow scaffold.

Changed files:

- `site/index.html`
- `site/styles.css`
- `docs/index.md`
- `docs/product/index.md`
- `_work/design-inputs/redwitch-inventory.md`

Key outcomes:

- `redwitch.ca` is treated as the apex public site.
- `www.redwitch.ca` is intended as a redirect only.
- GitHub Pages docs stay under `/docs/` with relative links.
- The historical wiki remains referenced only from the docs area.
- The NFS PDF captures in `_work/` were left in place as evidence.

Remaining manual step:

- Verify the live `www.redwitch.ca` redirect after deployment.

---

# codex-002 - Routing Consistency Cleanup

**Plan:** `ad hoc`
**Priority:** P2
**Status:** recorded
**Timestamp:** 2026-06-10 23:10 EDT

## Changes

Updated repository-facing documentation and work notes to match the deployed
topology:

- `https://www.redwitch.ca/` is the canonical public website.
- `https://redwitch.ca/` redirects to the public website.
- `https://docs.redwitch.ca/` is the documentation site.
- `https://docs.redwitch.ca/product/` is the product documentation index.
- `redwitch.wiki` is historical only.

Changed files:

- `README.md`
- `docs/index.md`
- `docs/product/index.md`
- `_work/notes/redwitch-hosting-notes.md`
- `_work/codex-log.md`

This was a cleanup pass only. No repository structure or deployment process
was introduced.

---

# codex-003 - Split-Root Canonical Comment Update

**Plan:** `ad hoc`
**Priority:** P2
**Status:** recorded
**Timestamp:** 2026-06-22 EDT

## Changes

Added a small explanatory comment to the apex redirect root and canonical
`www` page so the Red Witch split-root layout is explicit in source:

- `sites/redwitch.ca/.htaccess` is redirect-only
- `sites/www.redwitch.ca/index.html` is the canonical content page

This documents the server-side topology without changing the page content.

---

# codex-004 - Product Restoration Status Reconciliation

**Plan:** `0001-red-witch-product-restoration`
**Priority:** P1
**Status:** recorded
**Timestamp:** 2026-06-27 EDT

## Changes

- Added the repository plan dashboard.
- Moved Plan 0001 to `doing` because the product-document inventory,
  authoritative product drafts, README, documentation routes, and static
  public surfaces already exist.
- Left authority migration, issue reconciliation, wiki archival, and
  effectiveness verification open.

## Verification

- `git diff --check`
