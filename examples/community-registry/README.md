# Community registry demo

This example shows how to cache official Mint catalog records from the
immutable mint-registry snapshot `v0.2.0-alpha.0`. It does not
pip-install or execute an integration. CI still runs `mint check` on
the starter project; this directory is documentation plus static JSON.
Do not follow registry `main` or `/releases/latest`.

## Records

`records/v0.json` matches the official GitHub Release pins:

- `local.sandbox.ensure_marker` → `mint-integration-local` `v0.2.1-alpha.1`
- `repo.github.plan` → `mint-integration-github` `v0.3.0-alpha.1`

Digests were verified against GitHub Release `SHA256SUMS` and the tagged
`mint-integration.json` blob.

## Commands (language ADR/cache required)

```bash
mint integrations update --project . --registry examples/community-registry
mint integrations search sandbox --project .
mint integrations add --project . repo.github.plan
mint integrations verify --project .
mint lock --project .
```

`update --registry` copies records into `.mint/catalog-records.json`.
Search, add, verify, and lock stay offline after that. Do not pass a
URL. There is no hosted registry service.
