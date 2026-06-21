# Governance Layout

This repository is the authoritative draft source for Jason's AI agent governance.

The trunk branch carries the general contract for every agent kind. Kind branches carry complete branch-local pictures after trunk is merged down into them. Core content is intentionally duplicated across kind branches so an agent can read one branch and have the complete contract.

Layout:

- `AGENTS.md`: thin entrypoint with precedence, always-load policy, and routing pointer.
- `.governance/task-map.yaml`: task or session routing to the additional policy files that should be loaded.
- `.governance/policies/`: standing domain policies in YAML.
- `.governance/processes/`: meta-governance and operating processes.
- `.governance/overrides/`: temporary exception log and its schema.

Kind branches add `.governance/branch-descriptor.yaml`. Trunk does not carry that descriptor, so trunk merge-downs do not overwrite kind orientation.

Current draft status:

- The files in the normal root and `.governance/` paths are the trunk draft.
- `.governance/draft-kind-branches/` holds proposed kind-branch overlays for Jason's ratification before real branch creation.

