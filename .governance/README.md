# Repo-Local Governance Copy

This directory is this repository's active local governance copy.

Agents working in this repository load and follow this directory the same way they would use `.governance/` in any other repository. On `main`, this copy supports repository-local governance while README.md remains only a routing map to active versioned governance branches.

Committed governance files under `.governance/` are ratified by existence. Status fields may still describe operational role, such as `active`, but they are not a separate ratification gate. Draft local-governance proposals must stay outside this active local governance tree until Jason ratifies them.

Use `task-map.yaml` as the explicit loading contract. It may define reusable route groups, but agents should still load only the groups and direct files named by selected routes instead of scanning policy folders.

This directory intentionally duplicates governance rules that may also appear in active versioned branches. On `main`, do not treat this branch as an active policy-line endpoint; use the versioned branches listed in README.md for active governance contracts.

Hard invariants are surfaced through `policies/hard-invariant-index.yaml`, a tiny always-loaded guarded-domain index. Load the full register at `policies/hard-invariants.yaml` only when the intended action enters a guarded domain.

Use `skills/` for loadable skill sources that implement governance behavior in runtimes that support skills. Skill sources are policy-adjacent artifacts; their controlling policy remains under `policies/`.

Use `local/` for explicit repo-local deviations from the generalized rule set. The universal local policy pointer is `local/index.yaml`; the universal local governance status report is `local/status.yaml`. Everything else under `local/` is workspace-owned unless explicitly routed by that local pointer. Use `records/` for repo-local alignment notes or operational metadata. If a local rule should become general lab governance, promote it through an explicit `lab-governance/` policy or process change.
