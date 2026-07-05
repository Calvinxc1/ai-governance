# AI Governance

This repository maintains Jason's AI agent governance.

It has two governance layers:

- `.governance/` is this repository's active local governance copy. Agents working in this repository load and follow it the same way they would use `.governance/` in any other repository.
- `lab-governance/` is the generalized governance rule set this repository maintains for propagation to the rest of the lab and to specialized agent branches.

The two trees intentionally duplicate governance rules. Drift between them is allowed when it is visible and intentional: `.governance/` governs this repository, while `lab-governance/` is the candidate general rule set for other agents and repos.

Agents should start with `AGENTS.md`, then load local policy through `.governance/task-map.yaml` and any branch-local `.governance/kind-routes.yaml` file. The task map is the explicit loading contract: agents resolve route groups and direct route files from the map instead of inferring policy from folder names. When the task is to maintain the generalized rule set, compare the local copy against `lab-governance/` and update the appropriate tree explicitly.

General policy intended for lab propagation belongs in `lab-governance/`. Local governance needed for this repo's agents belongs in `.governance/`.

For new agent setup and governed-agent updates, use the canonical prompt at `lab-governance/templates/governance-bootstrap-prompt.md`. The prompt points agents to `lab-governance/governance-init.md`, registry files, self-stamp mechanics, reconciliation feedback, and registry-loop attestation.
