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

## Pinning a version

The `main` in every URL above is a git ref. To stay on a specific schema
or pricing version, replace it with a tag or commit SHA of this repo:

```
https://raw.githubusercontent.com/xsmod/aibench/<tag-or-sha>/schema/aibench.schema.json
```

Tags are cut here whenever the schema changes shape; `main` always serves
the latest.
