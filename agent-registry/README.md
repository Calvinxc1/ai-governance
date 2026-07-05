# Agent Registry

This directory is a legacy central index of agent governance versions for `ai-governance`.

Current rule: each governed workspace keeps its authoritative portable status at:

```text
.governance/local/status.yaml
```

That local status file records the workspace's canonical agent name, kind, active governance branch, current active canon version, current generalized canon version, source, and locally declared state. It is the first place to check when auditing whether an agent has governance and what it believes it is running.

The legacy registry has two parts:

- `agent-registry/agents.yaml` is a historical seed/index. It may record versions a known agent was believed to run and target versions that were once assigned centrally.
- legacy local self-stamps may exist in older governed workspaces. They can provide migration evidence, but should be reconciled into `.governance/local/status.yaml`.

The central registry is not the live authority for governed workspace status. Do not treat an absent, stale, or mismatched registry row as overriding local status. If local status, legacy self-stamp, and registry evidence conflict, report the conflict and ask Jason rather than silently choosing one.

At the start of a new conversation, agents use `.governance/local/status.yaml` and source branch descriptors for the minimal version check required by execution control: if current equals target, continue silently; if current is behind target, report only current version, target version, and whether to update before proceeding.

## Files

- `schema.yaml`: legacy registry schema, retained for historical rows.
- `agents.yaml`: current legacy seeded registry rows.
- `../lab-governance/templates/local-status.yaml`: template each governed workspace uses for `.governance/local/status.yaml`.
- `../lab-governance/templates/agent-self-stamp.yaml`: legacy self-stamp template retained for migration reference.
- `../lab-governance/governance-init.md`: initialization guide for bringing a new agent workspace under governance.

## Branch Placement

The legacy registry remains committed on `trunk` because it is a governance-wide historical artifact, not specific to one agent kind. Kind branches receive it by normal trunk merge-down. Branch-specific agent details may still appear in rows when they describe a particular agent's active governance source, but new live status should be maintained locally in the governed workspace.
