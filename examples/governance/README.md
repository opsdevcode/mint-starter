# repository-governance (starter copy)

Plan-only `repo.github` example copied from
`opsdevcode/specmint-language` `examples/projects/repository-governance`.

```bash
mint plan --project examples/governance --locked \
  --snapshot examples/governance/snapshots/specmint.json
```

The snapshot is a local file. This does not call GitHub. `execute` is
refused. Open the plan JSON on a pull request; merge is an owner
decision.
