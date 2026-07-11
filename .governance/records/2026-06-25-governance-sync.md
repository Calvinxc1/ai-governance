# Governance Sync Recommendation

Date: 2026-06-25
Room: governance-sync
Participants: Personal, Coding Agent
Status: recommended, pending Jason ratification

## Scope

This record captures the durable outcome from the live Althing coordination room `governance-sync`.

The live room is non-durable. This file is the hand-written durable record for Jason review. Agent convergence is a recommendation only. No governance change in this record is canon until Jason explicitly ratifies it.

## Version Pins

Personal reported that it currently carries desktop-orchestrator canon pinned to `141c8e7b`, corresponding to the `desktop-orchestrator` branch before the latest governance synchronization.

Recommended current pin for Personal:

- Branch: `desktop-orchestrator`
- Remote ref: `origin/desktop-orchestrator`
- Commit: `1517e56`
- Commit subject: `Add desktop generalized governance copy`

Recommended seed for a new desktop-orchestrator kind Academics agent:

- Branch: `desktop-orchestrator`
- Remote ref: `origin/desktop-orchestrator`
- Commit: `1517e56`
- Commit subject: `Add desktop generalized governance copy`

Rationale: `1517e56` contains the current desktop-orchestrator branch picture after trunk commit `1b8d447` and the branch-local generalized governance copy were distributed.

If Jason wants Academics to diverge as its own kind, seed from `desktop-orchestrator@1517e56` first, then create a distinct Academics branch or descriptor as a separate ratified governance change.

## Delivered Althing Communication Updates

The latest Althing communication-standard updates now present in `desktop-orchestrator@1517e56` include:

- exactly one active human liaison for confirmations, clarifications, approvals, and ratification requests in multi-agent live rooms with a human present
- non-liaison agents route human-facing decision requests through the active liaison or explicit liaison handoff
- no duplicate confirmation requests to the same human from multiple agents in the same live room
- if the active liaison becomes unavailable, agents choose a replacement before further human-facing decision requests
- finishing an individual work slice does not by itself permit an agent to leave an active live coordination room
- early participant departure requires an explicit handoff naming completed work, open follow-ups, remaining owner, and last cursor when applicable
- the closer controls room-level closeout or suspension and releases participants only after completion criteria are met or unresolved follow-ups are explicitly assigned
- before final closeout, each active participant declares no open follow-ups or names the follow-up and owner
- agents must not leave a live coordination room in a state where remaining participants cannot tell whether the room is active, suspended, or closed

## Personal Conflict Reconciliation

Observed conflict:

- Personal was pinned to `desktop-orchestrator@141c8e7b`.
- That pin predates the latest human-liaison, duplicate-confirmation, closeout, no-unilateral-departure, local-governance-copy, and generalized-governance-copy updates.

Recommended reconciliation:

- Personal should update its desktop-orchestrator governance canon pin to `origin/desktop-orchestrator@1517e56`.
- Personal should treat the single-human-liaison rule as governing future multi-agent rooms involving Jason or another human.
- Personal should not independently ask Jason for confirmations when another active human liaison is designated.
- Personal should stay in live rooms until closer-led closeout or suspension, unless it posts an explicit handoff.
- Personal should treat `.governance/` as the active local governance copy and `lab-governance/` as the generalized maintained copy when operating in this repository.

No additional Personal-specific operational conflict was raised in-room before this record was written.

## Follow-Up For Jason

- Ratify or revise Personal's update pin: `origin/desktop-orchestrator@1517e56`.
- Ratify or revise the Academics seed pin: `origin/desktop-orchestrator@1517e56`.
