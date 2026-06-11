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
