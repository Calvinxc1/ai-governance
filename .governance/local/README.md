# Local Governance Deviations

This directory records explicit local deviations for this repository's uniform `.governance/` operating layer.

Use this directory when the repository's purpose requires local behavior that should not automatically propagate to other repositories or agents.

Files committed under this local governance directory are ratified by existence. Do not store draft local-governance proposals here; keep proposals outside the active local governance tree until Jason ratifies them.

Local deviations must be:

- explicit
- narrow
- tied to this repository's governance-maintenance purpose
- reviewed against branch-local metadata and `lab-governance/` when those trees exist on the current branch
- promoted to `lab-governance/` only when Jason decides the rule should generalize

The canonical deviation list is `deviations.yaml`.

`index.yaml` is the loose local-governance pointer. Branch-local status belongs outside `.governance`, under `lab-governance/status.yaml` when present. Other local files are repository-owned and should not be inferred as lab-wide structure.
