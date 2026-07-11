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
baseline/trunk/3.16.0
baseline/coding-agent/1.6.0
baseline/desktop-orchestrator/1.2.0
baseline/factorio-modding-agent/1.1.0
```

Current enforcement-redesign branches:

```text
enforcement-redesign/trunk/1.5.0
enforcement-redesign/coding-agent/1.6.0
enforcement-redesign/desktop-orchestrator/1.5.0
enforcement-redesign/factorio-modding-agent/1.5.0
```
