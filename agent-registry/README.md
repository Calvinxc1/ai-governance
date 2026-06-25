# Agent Registry

This directory is the durable central index of agent governance versions for `ai-governance`.

The registry has two parts:

- `agent-registry/agents.yaml` is the central durable index. It records the governance version each known agent is believed to run, the target version it should run, and the last confirmation source.
- each leaf agent keeps a local self-stamp in its own operating area. The self-stamp is the agent-attested truth about what that agent believes it is running.

The central registry and local self-stamps serve different purposes. The registry gives Jason and coordinating agents a single place to see expected and confirmed versions. The self-stamp gives each agent a local declaration that can be checked against the registry.

A mismatch between the registry and a self-stamp is governance drift. Do not silently reconcile drift by choosing whichever value is newer or more convenient. Mark the row `drifted`, `behind`, or `unknown` as appropriate, then escalate the decision to Jason through the active human liaison.

## Files

- `schema.yaml`: registry schema, required fields, and status enum.
- `agents.yaml`: current seeded registry rows.
- `../lab-governance/templates/agent-self-stamp.yaml`: template each leaf agent can copy into its local governance area.

For desktop-orchestrator kind agents, the fixed local self-stamp path is:

```text
.governance/local/version-stamp.yaml
```

## Branch Placement

The registry is committed on `trunk` because it is a governance-wide artifact, not specific to one agent kind. Kind branches receive it by normal trunk merge-down. Branch-specific agent details may still appear in rows when they describe a particular agent's active governance source.
