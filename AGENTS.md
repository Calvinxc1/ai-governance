# AGENTS.md

Portable governance policy entrypoint. The maintained governance product lives under `lab-governance/`.
Downstream workspaces seed a local `.governance/` tree from this product, then preserve workspace-owned local governance under `.governance/local/`.

Precedence:
`AGENTS.md` is the entrypoint. Loaded lab/canon governance is the base policy-product layer. Loaded local governance from `.governance/local/index.yaml` is the workspace layer above it. Explicit task overrides in `.governance/overrides/*` override both base and local governance for the declared one-shot operation only.
If ambiguity remains, ask before acting. Override-governance rules are non-overridable unless a process file explicitly says otherwise.

Always load:
- `lab-governance/policies/universal.yaml`
- `lab-governance/policies/enforcement-model.yaml`
- `lab-governance/policies/hard-invariant-index.yaml`

Load additional policy only via:
- `lab-governance/task-map.yaml`
- `lab-governance/kind-routes.yaml` when present on a kind branch
- `.governance/local/index.yaml` for workspace-local governance when present
