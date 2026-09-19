# ryanthomas-tools

Desk tooling for **ryanthomas.ai** — shared utilities Architect and other agents use across products (Focx, Studio 810, …). Not a customer-facing product.

## Layout

```
ryanthomas-tools/
  README.md
  docs/
    roadmap.md
  # future: packages/ or tools/ entries as we migrate desk utilities here
```

## Planned / related

| Tool | Status | Notes |
|------|--------|--------|
| [drift-check](https://github.com/ryanphillipthomas/drift-check) | Live standalone repo | Design-token drift GitHub Action; migrate or nest here when ready |
| focx-site `tools/site-compose` | Stays in product repo | Site build only — not desk tooling |

## Principles

- **Desk-wide** — useful to more than one product
- **Agent-safe** — clear inputs/outputs; no silent prod side effects
- **Thin products** — Focx/Studio site repos stay landing + compose, not tool umbrellas

## Default branch

`main`
