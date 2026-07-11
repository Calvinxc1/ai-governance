# AI Governance

This repository stores Jason's AI agent governance. The `main` branch is the neutral routing branch: it explains the branch structure, points to the active governance branches, and carries the universal bootstrap/update prompt at the repository root. It also carries the repo-local `.governance/` copy that should remain available across branches.

Active governance is stored on stable endpoint branches shaped as:

```text
<policy-line>/<endpoint>/main
```

The final `main` segment is the current active endpoint for that policy line and agent kind. Older version endpoint branches are not retained as active branch targets.

Policy lines:

- `baseline`: Jason's original governance line.
- `enforcement-redesign`: the enforcement-first experimental governance line.

Universal bootstrap/update prompt:

```text
governance-bootstrap-prompt.md
```

Use the root prompt from literal branch `main` before selecting a policy-line endpoint. The prompt can also be pasted directly. It requires the target policy line, such as `baseline` or `enforcement-redesign`, to be explicit before an agent chooses its kind branch or mutates local governance.

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
