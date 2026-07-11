# Universal Governance Bootstrap Prompt

Use this prompt for any agent that needs to initialize, verify, or update local governance from Jason's `ai-governance` repository.

Canonical source:

```text
gitea.infra.newedenhomestead.net:ai-projects/ai-governance.git
```

Canonical prompt location:

```text
branch: main
path: governance-bootstrap-prompt.md
```

This prompt is policy-line neutral. It does not choose `baseline` or `enforcement-redesign` for the agent. The target policy line must be explicit before local governance is changed.

## Branch Mapping

Branches use the stable endpoint shape:

```text
<policy-line>/<endpoint>/main
```

Current target branches:

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

````markdown
Before doing substantive work, bootstrap, verify, or update this workspace's governance from Jason's `ai-governance` repository.

Use the universal bootstrap prompt from either this pasted text or the canonical repository location:

```text
gitea.infra.newedenhomestead.net:ai-projects/ai-governance.git
branch: main
path: governance-bootstrap-prompt.md
```

This prompt is policy-line neutral. Do not infer the target policy line from agent kind, runtime surface, repository name, task role, prior chat label, or the endpoint branch that happens to be easiest to read.

Two-tree model:

- In the downstream workspace, `.governance/` is the active local governance copy the agent loads and obeys.
- In `ai-governance`, the selected endpoint branch's `lab-governance/` tree is the source product used to seed or update that downstream `.governance/` copy.
- Never use `ai-governance`'s own `.governance/` tree as the downstream source; it governs this repository's Governance Agent only.
- `lab-governance/status.yaml` in the downstream workspace is local status metadata, not the active local policy tree.

Before changing files, identify or ask for:

- the Jason-settled canonical agent name
- the agent kind
- the target policy line: `baseline` or `enforcement-redesign`
- the active governance branch selected from the branch mapping
- the current local status path and versions, if present
- any old branch names, old canon/version labels, missing modern status fields, or previous governance source paths

If the target policy line was not explicitly provided by Jason, the orchestrating agent, or a trusted local status record that Jason confirms, stop and ask:

```text
Which governance policy line should this workspace use: baseline or enforcement-redesign?
```

If local status, old branch names, old canon/version labels, missing modern status fields, or previous governance source paths name an agent, branch, or policy line, report them as candidate evidence and ask Jason or the orchestrating agent to confirm or correct them before mutating governance. Do not silently reconcile conflicting evidence. Treat obsolete branch names and old status shapes as migration evidence, not as authoritative blockers, unless they create a real policy-line, identity, or local-governance conflict.

Then:

1. Inspect or fetch `ai-governance`.
2. Read this universal prompt from literal branch `main`.
3. Select the target branch from the mapping using the confirmed policy line and agent kind.
4. Read the selected branch's `lab-governance/governance-init.md` as the setup guide and `lab-governance/templates/local-status.yaml` as the local status shape.
5. Seed or update the downstream workspace's active `.governance/` tree only from the selected branch's `lab-governance/` source product.
6. Do not copy, merge, diff against, or otherwise use the ai-governance repository's `.governance/` tree as a source for a downstream workspace. In ai-governance, `.governance/` is the Governance Agent's own uniform operating layer, not the per-kind governance product.
7. Do not copy the selected branch's concrete `lab-governance/status.yaml` into the downstream workspace. Treat it as source-branch maintainer metadata for ai-governance only.
8. Create or update the downstream workspace's `lab-governance/status.yaml` from `lab-governance/templates/local-status.yaml` and fill it with locally attested downstream values.
9. Preserve local-only governance files unless Jason or explicit policy says to reconcile them.
10. Ensure `.governance/local/index.yaml` exists, using `lab-governance/templates/local-index.yaml` as the loose starter shape when needed. Do not prescribe the rest of `.governance/local/`.
11. Re-read the downstream workspace's resulting `AGENTS.md`, `.governance/policies/universal.yaml`, `.governance/task-map.yaml`, any `.governance/kind-routes.yaml`, and `.governance/local/index.yaml` when present. These are the files just seeded or updated in the downstream workspace, not ai-governance's `.governance/` files.
12. Load every local governance file reachable from `.governance/local/index.yaml` and compare local governance against the newly seeded canonical governance for conflicts, duplicated rules, obsolete local overrides, and local rules that now overlap with canonical rules.
13. Treat lab/canon governance as the base layer, loaded local governance as the workspace layer above it, and explicit one-shot overrides as the top layer for their declared operation. Local governance wins operationally over canonical governance unless Jason or explicit local policy says otherwise, but conflicts and redundancies must still be surfaced.
14. Compare local status, source branch descriptor, and old branch or version evidence. Report conflicts instead of silently reconciling them.

Close out with only:

- canonical agent name and agent kind
- confirmed target policy line
- source branch and commit consumed, when known
- active and generalized canon versions after the operation
- local status path updated or created
- local status declared state
- local governance conflicts, redundancies, or obsolete overrides found during update
- unresolved reconciliation items and their owners
````
