# AGENTS.md

Repository policy entrypoint. Active repo-local operating governance lives under `.governance/`.
The `.governance/` tree is the same on every branch. Branch-local identity and status live under `branch-governance/` when present. The generalized lab-wide governance rule set maintained by this repository lives under `lab-governance/` when present.
Use `.governance/` to govern work in this repository unless a task explicitly concerns the generalized rule set or branch metadata.

Precedence:
`AGENTS.md` is the entrypoint. Loaded lab/canon governance is the policy-product layer when the task concerns maintained governance content. Loaded local operating governance from `.governance/local/index.yaml` governs this repository's agent behavior. Explicit task overrides in `.governance/overrides/*` override both base and local governance for the declared one-shot operation only.
If ambiguity remains, ask before acting. Override-governance rules are non-overridable unless a process file explicitly says otherwise.

Always load:
- `.governance/policies/universal.yaml`
- `.governance/policies/enforcement-model.yaml`
- `.governance/policies/hard-invariant-index.yaml`

Load additional policy only via:
- `.governance/task-map.yaml`
- `.governance/kind-routes.yaml` for Governance Agent desktop-orchestrator operating behavior
- `.governance/local/index.yaml` for repo-local governance when present
- `branch-governance/` for branch-local identity, status, and routing metadata when the task concerns branch structure or propagation
- `lab-governance/` when the task concerns the maintained generalized governance product
