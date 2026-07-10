# Lab Governance Layout

This directory contains the lab-wide governance rule set maintained by this repository.

These files are the general policy and process contract intended to propagate to the rest of the lab and to specialized agent branches.

This secondary branch channel uses an enforcement-first governance model. High-stakes recurring failures should map to hard gates, cheap default paths, or detectors; prose-only fixes are tracked debt unless Jason accepts the residual risk. Bootstrap and update instructions in this channel preserve the `enforcement-redesign/*` source branch family unless Jason explicitly redirects an agent to the normal branch family.

This directory is not the active local governance entrypoint for agents working in this repository. That role belongs to `.governance/`. The two trees intentionally duplicate governance rules and may drift when the distinction is visible and intentional.

The `enforcement-redesign/trunk` branch carries the experimental general contract for every agent kind. Secondary kind branches carry complete branch-local pictures after `enforcement-redesign/trunk` is merged down into them. Core content is intentionally duplicated across kind branches so an agent can read one branch and have the complete contract.

Layout:

- `AGENTS.md`: thin entrypoint with precedence, always-load policy, and routing pointer.
- `lab-governance/governance-init.md`: setup guide for initializing governance in a new or unverified agent workspace.
- `lab-governance/task-map.yaml`: task or session routing to the additional policy files that should be loaded. Route groups provide reusable subroutes; selected routes, not folder names, remain the explicit loading contract.
- `lab-governance/policies/enforcement-model.yaml`: bucket model for hard invariants, outcome-plus-bounds policy, and deliberately ungoverned work.
- `lab-governance/policies/hard-invariant-index.yaml`: tiny always-loaded guarded-domain index for context-loading the full hard-invariant register.
- `lab-governance/policies/hard-invariants.yaml`: full context-loaded Bucket A hard-invariant register.
- `lab-governance/policies/`: standing domain policies in YAML.
- `lab-governance/processes/`: meta-governance and operating processes.
- `lab-governance/skills/`: loadable skill sources that implement governance behavior in runtimes that support skills.
- `lab-governance/overrides/`: temporary exception log and its schema.
- `lab-governance/templates/`: reusable setup templates, including the local governance status template, loose local index template, legacy self-stamp template, and canonical governance bootstrap prompt.
- `lab-governance/templates/governance-bootstrap-prompt.md`: canonical prompt for first-time governance initialization and governed-agent updates.
- `lab-governance/templates/experimental-channel-transition-prompt.md`: prompt for moving an already-governed workspace from the normal governance branch family to the secondary `enforcement-redesign/*` branch family.
- `lab-governance/templates/kind-branch-migration-checklist.md`: version-agnostic checklist for adopting a target kind branch without hard-coding a particular canon version.
- `lab-governance/templates/local-index.yaml`: loose pointer template for `.governance/local/index.yaml`; the local directory's internal structure remains workspace-owned.
- `lab-governance/templates/local-status.yaml`: local status template for `.governance/local/status.yaml`; this is metadata, not a local policy body.
- `lab-governance/templates/task-brief.md`: standard brief shape for objective, definition of done, bounds, risk, budget, and stopping condition.

Kind branches add `lab-governance/branch-descriptor.yaml` and `lab-governance/kind-routes.yaml`. The channel trunk does not carry those files, so channel-trunk merge-downs do not overwrite kind orientation or kind-specific routing.
