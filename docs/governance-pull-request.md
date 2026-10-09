# Governance pull request example

This pull request is the worked example. It does not call GitHub and
does not apply settings.

Current captured snapshot
(`examples/governance/snapshots/specmint.json`) has
`pullRequestRequired=false` and `requiredApprovingReviewCount=0`.

The desired plan-only change:

- `pullRequestRequired`: true
- `requiredApprovingReviewCount`: 1

Reproduce locally after installing `specmint==0.7.0a2` or the GitHub
Release wheel:

```bash
mint plan --project examples/governance --locked \
  --snapshot examples/governance/snapshots/specmint.json
```

Attach the plan JSON to the pull request. `execute` stays refused.
Merge is an owner decision. No PAT. No `mint apply`.
