# Red Witch Hosting Notes

This note records the intended hosting relationship without exposing provider
or DNS details.

## Intended Deployment Flow

- `redwitch/site/` is the source for the public apex site.
- `redwitch.ca` is the live public site.
- A deployment process in `../site-ops/` is expected to publish the site.
- The exact deployment process is TBD.

## Notes

- Keep public-site content separate from documentation content.
- Do not treat this file as a source of hosting credentials or internal
  infrastructure details.
