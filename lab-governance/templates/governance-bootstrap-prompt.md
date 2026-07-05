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

## Prompt

```markdown
Before doing substantive work, bootstrap or update this workspace's governance from Jason's `ai-governance` repository.

Use `lab-governance/governance-init.md` as the setup guide and `agent-registry/README.md`, `agent-registry/schema.yaml`, and `agent-registry/agents.yaml` for registry and self-stamp expectations.

First, determine whether this workspace already has local governance:

- If `AGENTS.md` and `.governance/` exist, treat this as a governed-agent update.
- If they do not exist, treat this as first-time governance initialization.

Before changing files, identify or ask for:

- the Jason-settled canonical agent name
- the agent kind
- the active governance branch to consume
- the current local self-stamp path and versions, if present
- the registry row and target versions, if present

Do not infer the canonical agent name from repository name, hostname, model backend, runtime surface, task role, or prior chat label. If a self-stamp or registry row names an agent, report it and ask Jason to confirm or correct it before mutating governance.

Then:

1. Inspect or fetch `ai-governance`.
2. Select the correct active governance branch for the agent.
3. Copy or merge the branch-local governance picture into the workspace.
4. Preserve local-only governance files unless Jason or explicit policy says to reconcile them.
5. Create or update `.governance/local/version-stamp.yaml`.
6. Re-read the resulting `AGENTS.md`, `.governance/policies/universal.yaml`, `.governance/task-map.yaml`, and any `.governance/kind-routes.yaml`.
7. Compare local self-stamp, source branch descriptor, and registry state. Report conflicts instead of silently reconciling them.
8. Emit or submit a structured registry attestation using the currently ratified transport. If no remote transport is available, write the attestation to a local durable path and report it.

Use `lab-governance/templates/agent-self-stamp.yaml` as the self-stamp shape. Do not directly edit `agent-registry/agents.yaml` unless a ratified process explicitly authorizes direct registry mutation.

Close out with only:

- canonical agent name and agent kind
- source branch and commit consumed
- active and generalized canon versions after the operation
- self-stamp path updated or created
- registry attestation path or submission target
- central registry status: updated, pending, failed, skipped, or explicitly deferred
- unresolved reconciliation items and their owners
```
