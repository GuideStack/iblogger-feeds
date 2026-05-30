# ADR-0001: Use a feature flag for the MoMo wallet rollout

| Field | Value |
|-------|-------|
| Status | Accepted |
| Date | 2026-06-04 |
| Proposed by (Dev) | Visal |
| Recommended by (Tech Lead) | Lyda |
| Accepted by (CTO) | Sokha |
| Supersedes | — |
| Superseded by | — |

> This is an example ADR, filled in to show the template in use. Replace it with real decisions.

---

## Context

We are adding the MoMo wallet as a new checkout payment option (ticket PAY-142). The integration touches the live checkout flow used by all customers. If the MoMo gateway misbehaves in production, it could block checkout entirely — a revenue-critical path.

Constraints:
- We release as a bundled version every sprint; we cannot hotfix instantly.
- The MoMo sandbox has shown intermittent timeouts during testing.
- Finance wants the option live for a marketing campaign on a fixed date, but is willing to delay the *visible* launch if needed.

The forces in tension: ship on the campaign date vs. protect the checkout path from a new, partly-unproven gateway.

## Decision

We will ship the MoMo wallet behind a **feature flag** (`momo_wallet`), defaulted **off** in production. The flag is toggled on only after the deploy is verified healthy, and can be turned off instantly without a redeploy.

This lets us deploy the code with the normal release while keeping the new payment path dark until we choose to enable it — and gives us an instant kill switch if the gateway misbehaves.

## Alternatives Considered

- **Ship it always-on (no flag).** Rejected — a gateway failure would immediately affect real checkouts with no fast way back except a rollback or hotfix, which we cannot do mid-sprint.
- **Hold the whole release until MoMo is fully proven.** Rejected — it would block unrelated Done tickets in the same release from shipping, for a risk we can isolate with a flag.
- **Separate microservice for payments behind its own deploy.** Rejected for now — too large a change for this sprint; revisit if we add more gateways (would warrant its own ADR).

## Consequences

- **Positive:** Code ships on schedule; launch timing is a business toggle, not an engineering deploy; instant kill switch reduces production risk.
- **Negative / trade-off:** One more flag to manage and eventually remove; QA must test both flag states (on and off).
- **Follow-up needed:** Remove the `momo_wallet` flag once the feature is stable and fully launched (track as a cleanup ticket).

---

## Sign-Off

| Step | Role | Name | Date |
|------|------|------|------|
| Proposed | Dev | Visal | 2026-06-04 |
| Recommended | Tech Lead | Lyda | 2026-06-04 |
| Accepted | CTO | Sokha | 2026-06-05 |
