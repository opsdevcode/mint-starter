# mint-starter

GitHub template for a fifteen-minute Mint adoption. Public preview.

This repository is a `local-marker` project plus a plan-only repository
governance example. There is no `mint apply` and no live GitHub mutation.

## Fifteen minutes

1. Use this repository as a template (or clone it).
2. Keep `.github/workflows/mint.yml`. It calls
   `opsdevcode/mint-action` on `pull_request` with `contents: read`.
3. Open a pull request. CI installs Mint `v0.7.0-alpha.2` /
   `specmint==0.7.0a2` from the GitHub Release wheel after `SHA256SUMS`.
4. Locally: `pipx install specmint==0.7.0a2` then
   `mint check --project .` and `mint plan --project . --locked`.

The starter may stay untagged. Pin the language release; there is no
`latest`.

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
| Language | `v0.7.0-alpha.2` / `0.7.0a2` |
| Action | `opsdevcode/mint-action` (commit pin in the workflow) |
| GitHub integration | `v0.3.0-alpha.1` (plan-only wheel, not PyPI) |
| Local integration | `v0.2.1-alpha.1` |

Apache-2.0. Marketplace, GHCR, and integration PyPI are out of scope.
