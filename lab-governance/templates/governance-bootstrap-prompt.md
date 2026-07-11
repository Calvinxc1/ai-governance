# Governance Bootstrap Prompt

Use this single prompt for any agent that needs to initialize, verify, or update its local governance from Jason's `ai-governance` repository.

Canonical source:

```text
gitea.infra.newedenhomestead.net:ai-projects/ai-governance.git
```

Canonical prompt path:

```text
lab-governance/templates/governance-bootstrap-prompt.md
```

Policy-line rule:

Branches use the stable endpoint shape `<policy-line>/<endpoint>/main`. Preserve the prompt source policy line unless Jason explicitly redirects it. The baseline policy line is Jason's original governance line. The enforcement-redesign policy line is the enforcement-first experimental line.

Governance source rule:

Seed and update downstream workspaces only from the selected branch's `lab-governance/` tree. Never use this repository's `.governance/` tree as the source or an external reference for another workspace. In this repository, `.governance/` is the Governance Agent's own uniform operating layer.

Current branch mapping:

```text
baseline:
  general -> baseline/trunk/main
  coding_agent -> baseline/coding-agent/main
  desktop_orchestrator -> baseline/desktop-orchestrator/main
  factorio_modding_agent -> baseline/factorio-modding-agent/main

enforcement-redesign:
  general -> enforcement-redesign/trunk/main
  coding_agent -> enforcement-redesign/coding-agent/main
  desktop_orchestrator -> enforcement-redesign/desktop-orchestrator/main
  factorio_modding_agent -> enforcement-redesign/factorio-modding-agent/main
```

## Prompt

```markdown
Before doing substantive work, bootstrap or update this workspace's governance from Jason's `ai-governance` repository.

Use `lab-governance/governance-init.md` as the setup guide and `lab-governance/templates/local-status.yaml` as the local status shape.

Use the same policy line as the prompt source. If this prompt came from a `baseline/<endpoint>/main` branch, select the current mapped `baseline` branch for this agent kind. If it came from an `enforcement-redesign/<endpoint>/main` branch, select the current mapped `enforcement-redesign` branch for this agent kind. Do not silently switch policy lines unless Jason explicitly directs that change.

Seed or update this downstream workspace only from `lab-governance/` on the selected branch. Do not copy, merge, diff against, or otherwise use this repository's `.governance/` tree as a source for the downstream workspace. That `.governance/` tree is the Governance Agent's own operating layer, not the per-kind governance product.

First, determine whether this workspace already has local governance:

- If `AGENTS.md` and `.governance/` exist, treat this as a governed-agent update.
- If they do not exist, treat this as first-time governance initialization.

Before changing files, identify or ask for:

- the Jason-settled canonical agent name
- the agent kind
- the prompt source branch, policy line, or source commit when known
- the active governance branch to consume
- the current local status path and versions, if present
- any legacy self-stamp or registry row that may provide candidate evidence only

Do not infer the canonical agent name from repository name, hostname, model backend, runtime surface, task role, or prior chat label. If local status, a legacy self-stamp, or a legacy registry row names an agent, report it and ask Jason to confirm or correct it before mutating governance.

Then:

1. Inspect or fetch `ai-governance`.
2. Select the correct active governance branch for the agent within the prompt source policy line.
3. Copy or merge the selected branch's `lab-governance/` product into the downstream workspace's local governance copy.
4. Preserve local-only governance files unless Jason or explicit policy says to reconcile them.
5. Ensure `.governance/local/index.yaml` exists, using `lab-governance/templates/local-index.yaml` as the loose starter shape when needed. Do not prescribe the rest of `.governance/local/`.
6. Create or update `lab-governance/status.yaml` from `lab-governance/templates/local-status.yaml`.
7. Re-read the downstream workspace's resulting `AGENTS.md`, `.governance/policies/universal.yaml`, `.governance/task-map.yaml`, any `.governance/kind-routes.yaml`, and `.governance/local/index.yaml` when present. These are the files just seeded or updated in the downstream workspace, not this repository's `.governance/` files.
8. Treat lab/canon governance as the base layer, loaded local governance as the workspace layer above it, and explicit one-shot overrides as the top layer for their declared operation.
9. Compare local status, source branch descriptor, and any legacy self-stamp or registry evidence. Report conflicts instead of silently reconciling them.
10. Treat the legacy central registry as historical and non-authoritative. Do not submit a central registry attestation unless Jason explicitly requests legacy registry maintenance.

Do not directly edit `agent-registry/agents.yaml` unless Jason explicitly asks for legacy registry maintenance.

Close out with only:

- canonical agent name and agent kind
- source branch and commit consumed, when known
- prompt source policy line used for branch selection
- active and generalized canon versions after the operation
- local status path updated or created
- local status declared state
- legacy registry status, only if Jason explicitly requested legacy registry maintenance
- unresolved reconciliation items and their owners
```
