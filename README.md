# AI Governance

This repository stores Jason's AI agent governance. The `main` branch is only a routing branch: it explains the branch structure and points to the active governance branches. It also carries the repo-local `.governance/` copy that should remain available across branches.

Active governance is stored on versioned branches shaped as:

```text
<policy-line>/<endpoint>/<version>
```

Policy lines:

- `baseline`: Jason's original governance line.
- `enforcement-redesign`: the enforcement-first experimental governance line.

Current baseline branches:

```text
baseline/trunk/main
baseline/coding-agent/main
baseline/desktop-orchestrator/main
baseline/factorio-modding-agent/main
```

Current enforcement-redesign branches:

```text
enforcement-redesign/trunk/main
enforcement-redesign/coding-agent/main
enforcement-redesign/desktop-orchestrator/main
enforcement-redesign/factorio-modding-agent/main
```
