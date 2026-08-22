# aibench published artifacts

Machine-consumed files served straight from this repo via
`raw.githubusercontent.com` — no build, no releases, the files are the
artifacts.

| Path | Served at | Consumed by |
|---|---|---|
| `schema/aibench.schema.json` | `https://raw.githubusercontent.com/xsmod/aibench/main/schema/aibench.schema.json` | the `# yaml-language-server: $schema=…` modeline in every `aibench.yaml` (editor completion + validation) |
| `pricing/pricing.yaml` | `https://raw.githubusercontent.com/xsmod/aibench/main/pricing/pricing.yaml` | `aibench cost update` (the Metrics panel's cost/context rows) |

The schema's source of truth is `internal/config/schema.json` in the app
repo — copies here are published from there. Pricing is harvested from
[catwalk](https://catwalk.charm.land) and republished here so the app has
one stable, curated address.

## Versioning

The ref in every URL above is a git ref of this repo, and that is the
whole versioning story:

- **Released aibench binaries** write config modelines pinned to the tag
  matching their own version (`vX.Y.Z`) — cutting that tag here is part of
  every aibench release.
- **`main`** is the verification branch: schema changes land here first
  (dev builds of aibench point at it), then get tagged.
- Pin anything yourself by putting a tag or commit SHA in your modeline:

```
https://raw.githubusercontent.com/xsmod/aibench/<tag-or-sha>/schema/aibench.schema.json
```

Pricing is consumed from `main` regardless of app version — rates change
on their own clock.
