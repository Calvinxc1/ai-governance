# AGENTS.md

Repository policy entrypoint. Active repo-local governance lives under `.governance/`.
The generalized lab-wide governance rule set maintained by this repository lives under `lab-governance/`.
The two trees intentionally duplicate policy and may drift; use `.governance/` to govern work in this repository unless a task explicitly concerns the generalized rule set.

Precedence:
`AGENTS.md` is the entrypoint. Loaded lab/canon governance is the base layer. Loaded local governance from `.governance/local/index.yaml` overrides the base layer for this repository. Explicit task overrides in `.governance/overrides/*` override both base and local governance for the declared one-shot operation only.
If ambiguity remains, ask before acting. Override-governance rules are non-overridable unless a process file explicitly says otherwise.

Always load:
- `.governance/policies/universal.yaml`
- `.governance/policies/enforcement-model.yaml`

Load additional policy only via:
- `.governance/task-map.yaml`
- `.governance/kind-routes.yaml` when present on a kind branch
- `.governance/local/index.yaml` for repo-local governance when present
