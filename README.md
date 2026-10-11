# mint-starter

GitHub template for a fifteen-minute Mint adoption. Public preview.

This repository is a `local-marker` project plus a plan-only repository
governance example. There is no `mint apply` and no live GitHub mutation.

## Fifteen minutes

1. Use this repository as a template (or clone it).
2. Keep `.github/workflows/mint.yml`. It calls
   `opsdevcode/mint-action` on `pull_request` with `contents: read`.
3. Open a pull request. CI installs Mint `v0.9.0-alpha.2` /
   `specmint==0.9.0a2` from the GitHub Release wheel after `SHA256SUMS`.
4. Locally: `pipx install specmint==0.9.0a2` then
   `mint check --project .` and `mint plan --project . --locked`.

The starter may stay untagged. Pin the language release; there is no
`latest`.

## Community registry demo

`examples/community-registry` holds static `mint.catalog-records/v0`
JSON matching mint-registry GitHub Release `v0.2.0-alpha.0` (not
`main`, not `/releases/latest`). Cache it with
`mint integrations update --registry examples/community-registry`.
Discovery does not install.

## Governance example

`examples/governance` is the language `repository-governance` project:
`repo.github` + a supplied snapshot. Plan only.

```bash
mint plan --project examples/governance --locked \
  --snapshot examples/governance/snapshots/specmint.json
```

Execute is refused. Do not pass a PAT.

## Pins

| Surface | Coordinate |
| --- | --- |
| Language | `v0.9.0-alpha.2` / `0.9.0a2` |
| Action | `opsdevcode/mint-action@2b35bb6a2da3f7f7e41254700aa030b3c18bfd1d` (`v0.2.0-alpha.0` comment only) |
| Registry snapshot | `opsdevcode/mint-registry` `v0.2.0-alpha.0` |
| GitHub integration | `v0.3.0-alpha.1` (plan-only wheel, not PyPI) |
| Local integration | `v0.2.1-alpha.1` |

Apache-2.0. Marketplace, GHCR, and integration PyPI are out of scope.
