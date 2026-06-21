# AGENTS.md

Repository policy entrypoint for the `coding-agent` kind branch. Authoritative policy lives under `.governance/`.

Precedence:
`AGENTS.md` > `.governance/processes/*.yaml` > `.governance/policies/*.yaml` > `.governance/overrides/*`
If ambiguity remains, ask before acting. Override-governance rules are non-overridable unless a process file explicitly says otherwise.

Always load:
- `.governance/policies/universal.yaml`
- `.governance/branch-descriptor.yaml`

Load additional policy only via:
- `.governance/task-map.yaml`

