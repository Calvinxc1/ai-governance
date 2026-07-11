# Uniform Operating Governance

This directory is this repository's uniform operating governance layer.

Agents working in this repository load and follow this directory the same way they would use `.governance/` in any other repository. `AGENTS.md` points here for the active local operating contract when an `AGENTS.md` entrypoint exists on the current branch.

Committed governance files under `.governance/` are ratified by existence. Draft local-governance proposals must stay outside this active local governance tree until Jason ratifies them.

Use `task-map.yaml` as the explicit loading contract. It may define reusable route groups, but agents should still load only the groups and direct files named by selected routes instead of scanning policy folders.

This directory is intentionally byte-identical across every branch in this repository. Branch, policy-line, kind, and version identity belongs outside `.governance`, primarily in `branch-governance/` for branch-local metadata and `lab-governance/` for the maintained generalized governance product where that tree exists.

Do not put branch-specific canon versions, kind inheritance, or policy-line product differences under `.governance`. If a `.governance` change is ratified, propagate the exact `.governance` tree to every branch in the repository before calling the work complete.

This operating layer uses the enforcement-first redesign. Rules should be sorted into hard invariants, outcome-plus-bounds policies, or deliberately ungoverned cheap reversible work.

Hard invariants are surfaced through `policies/hard-invariant-index.yaml`, a tiny always-loaded guarded-domain index. Load the full register at `policies/hard-invariants.yaml` only when the intended action enters a guarded domain.

Use `skills/` for loadable skill sources that implement governance behavior in runtimes that support skills. Skill sources are policy-adjacent artifacts; their controlling policy remains under `policies/`.

Use `local/` for explicit repo-local deviations from the generalized rule set. The universal local policy pointer is `local/index.yaml`. Everything else under `local/` is workspace-owned unless explicitly routed by that local pointer. Use `records/` for repo-local alignment notes or operational metadata. If a local rule should become general lab governance, promote it through an explicit `lab-governance/` policy or process change.
