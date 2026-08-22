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
whole versioning story. aibench points at **`main`** (evergreen — the
modeline is editor-only lint; the binary's strict parser is the real
contract and never reads it). To freeze your editor's schema, put a tag
or commit SHA in your own modeline:

```
https://raw.githubusercontent.com/xsmod/aibench/<tag-or-sha>/schema/aibench.schema.json
```

Tags are cut here when the schema changes shape. Pricing is consumed from
`main` always — rates change on their own clock.
