# Lab Governance Layout

This directory contains the lab-wide governance rule set maintained by this repository.

These files are the general policy and process contract intended to propagate to the rest of the lab and to specialized agent branches.

This directory is not the active local governance entrypoint for agents working in this repository. That role belongs to `.governance/`. The two trees intentionally duplicate governance rules and may drift when the distinction is visible and intentional.

The trunk branch carries the general contract for every agent kind. Kind branches carry complete branch-local pictures after trunk is merged down into them. Core content is intentionally duplicated across kind branches so an agent can read one branch and have the complete contract.

Layout:

- `AGENTS.md`: thin entrypoint with precedence, always-load policy, and routing pointer.
- `lab-governance/task-map.yaml`: task or session routing to the additional policy files that should be loaded.
- `lab-governance/policies/`: standing domain policies in YAML.
- `lab-governance/processes/`: meta-governance and operating processes.
- `lab-governance/overrides/`: temporary exception log and its schema.

Kind branches add `lab-governance/branch-descriptor.yaml` and `lab-governance/kind-routes.yaml`. Trunk does not carry those files, so trunk merge-downs do not overwrite kind orientation or kind-specific routing.
