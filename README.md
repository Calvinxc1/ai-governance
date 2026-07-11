# AI Governance

This branch carries a portable AI agent governance policy collection.

It distinguishes two governance areas:

- `lab-governance/` is the maintained governance product for this branch. Downstream workspaces seed and update from the selected branch's `lab-governance/` tree.
- `.governance/` is the downstream workspace-local governance tree created from the product; it is not part of this portable source branch. Workspace-local files under `.governance/local/` remain owned by the consuming workspace.

The split is intentional: `lab-governance/` is the portable source product, while downstream `.governance/` trees are local copies plus workspace-specific overlays.

This branch is `portable/coding-agent/main`, a stable `/main` endpoint in the `portable` policy line.

Agents should start with `AGENTS.md`, then load policy through `lab-governance/task-map.yaml` and any branch-local `lab-governance/kind-routes.yaml` file. The task map is the explicit loading contract: agents resolve route groups and direct route files from the map instead of inferring policy from folder names.

Workspace-local governance, when present, is reached through `.governance/local/index.yaml`. Local governance is the layer above the generalized lab/canon base for that workspace. Explicit one-shot overrides remain the top layer for the declared operation.

Portable policy belongs in `lab-governance/`. Local governance belongs in the consuming workspace's `.governance/local/`.

For new agent setup and governed-agent updates, use the bootstrap prompt supplied by the policy source. In a downstream workspace, `.governance/` is the active local governance tree; this branch's `lab-governance/` tree is the source product used to seed or update it.
