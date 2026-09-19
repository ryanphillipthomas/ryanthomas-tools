# ryanthomas-tools

Desk tooling for **ryanthomas.ai** — shared utilities Architect and other agents use across products (Focx, Studio 810, …). Not a customer-facing product.

## Layout

```
ryanthomas-tools/
  action.yml                 # Drift Check GitHub Action entrypoint
  tools/drift-check/         # scanner implementation
  README.md
  docs/roadmap.md
```

## Drift Check

Dependency-free GitHub Action that blocks design drift (raw visual values + invalid design-token overrides). Reads only the checked-out repo; no telemetry.

### Quickstart

```yaml
name: drift-check
on: pull_request

permissions:
  contents: read

jobs:
  drift-check:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: ryanphillipthomas/ryanthomas-tools@main
```

Previously published from [`ryanphillipthomas/drift-check`](https://github.com/ryanphillipthomas/drift-check) (`@v1`). That repo remains as the old Action home until we cut a deprecation redirect; **new consumers should use this repo**.

### Local

Requires Node.js 20+:

```sh
node tools/drift-check/index.mjs
```

Config: optional `drift-check.config.json` at the consumer repo root (see upstream docs / action inputs: `parent-namespace`, `token-path-pattern`, `scan-dirs`, `scan-extensions`).

## Other notes

| Tool | Status | Notes |
|------|--------|--------|
| Drift Check | **In this repo** | Action at repo root |
| focx-site `tools/site-compose` | Stays in product repo | Site build only |

## Principles

- **Desk-wide** — useful to more than one product
- **Agent-safe** — clear inputs/outputs; no silent prod side effects
- **Thin products** — Focx/Studio site repos stay landing + compose, not tool umbrellas

## Default branch

`main`
