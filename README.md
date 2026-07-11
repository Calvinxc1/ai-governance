# AI Governance Branch Map

This repository stores Jason's AI agent governance branches.

The `main` branch is only a lightweight repository landing branch. It carries this branch map, the repository `.gitignore`, and local repository governance status. It does not carry active agent policy, `lab-governance`, the canon version log, or any agent registry.

Active governance lives on versioned branches shaped as:

```text
<policy-line>/<endpoint>/<version>
```

Policy lines:

- `baseline`: Jason's original governance line.
- `enforcement-redesign`: the enforcement-first experimental governance line.

Current baseline branches:

```text
baseline/trunk/3.16.0
baseline/coding-agent/1.6.0
baseline/desktop-orchestrator/1.2.0
baseline/factorio-modding-agent/1.1.0
```

Current enforcement-redesign branches:

```text
enforcement-redesign/trunk/1.3.0
enforcement-redesign/coding-agent/1.4.0
enforcement-redesign/desktop-orchestrator/1.3.0
enforcement-redesign/factorio-modding-agent/1.3.0
```

Remote `trunk` may exist as a temporary compatibility/default-branch ref. Treat `baseline/trunk/3.16.0` as the baseline trunk version branch.
