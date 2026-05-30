# ADR Email Templates

Copy-and-fill email templates for the ADR approval flow. ADRs are authored in **IcePanel**; approval happens by emailing the **CTO** to review and **vote inside IcePanel**.

Replace every `<placeholder>`. Keep the IcePanel link in every email so the recipient can act in one click.

Order of use: **1. Tech Lead recommendation** → **2. Request CTO vote** → (**3. Reminder** if needed) → **4. Decision outcome**.

See the [ADR Sign-Off Procedure](../signoff-adr-procedure.md) for the full approval chain (Dev → Tech Lead → CTO).

---

## 1. Tech Lead Recommendation

*Sent by the Tech Lead after reviewing a Proposed ADR, to hand it off for the CTO vote. CC the author and the CTO.*

**To:** `<CTO email>`
**CC:** `<Dev author>`, `<team list>`
**Subject:** [ADR-`<NNNN>`] Recommended for your vote — `<short decision title>`

Hi `<CTO name>`,

I've reviewed **ADR-`<NNNN>`: `<short decision title>`** in IcePanel and I recommend it for acceptance.

- **Decision in one line:** `<we will …>`
- **Why it matters:** `<one-line impact / risk>`
- **Alternatives considered:** `<A, B — rejected because …>`
- **Author:** `<Dev name>`

Please review and cast your vote in IcePanel:
`<IcePanel ADR link>`

Could you vote by **`<date>`** so the team can proceed? Happy to walk through it if useful.

Thanks,
`<Tech Lead name>`

---

## 2. Request CTO Vote

*Sent to ask the CTO to review and vote on a Recommended ADR in IcePanel. This is the core approval request.*

**To:** `<CTO email>`
**CC:** `<Tech Lead>`, `<Dev author>`
**Subject:** [ADR-`<NNNN>`] Your vote requested — `<short decision title>`

Hi `<CTO name>`,

We need your sign-off on an architecture decision. The full ADR is in IcePanel:

**ADR-`<NNNN>`: `<short decision title>`**
`<IcePanel ADR link>`

Summary:
- **Context:** `<1–2 lines — why a decision is needed>`
- **Decision:** `<we will …>`
- **Consequences / trade-off:** `<the main one>`
- **Recommended by:** `<Tech Lead name>`

Please cast your vote (Accept / Request changes / Reject) directly in IcePanel by **`<date>`**. The decision is not authoritative until you accept it; the team is `<proceeding at risk / holding>` until then.

Thank you,
`<sender name>`

---

## 3. Reminder / Nudge

*Short follow-up if the CTO has not voted by the deadline. Keep it brief.*

**To:** `<CTO email>`
**CC:** `<Tech Lead>`
**Subject:** Re: [ADR-`<NNNN>`] Vote reminder — `<short decision title>`

Hi `<CTO name>`,

Gentle reminder on **ADR-`<NNNN>`: `<short decision title>`** — still waiting on your vote in IcePanel:
`<IcePanel ADR link>`

`<It's blocking … / We'd like to start … >`. Could you vote by **`<new date>`**? If you need anything from us to decide, just say.

Thanks,
`<sender name>`

---

## 4. Decision Outcome

*Sent to the team after the CTO votes, announcing the result. Update the ADR status in IcePanel and the index first.*

**To:** `<team list>`
**CC:** `<Tech Lead>`, `<Dev author>`
**Subject:** [ADR-`<NNNN>`] `<Accepted / Rejected>` — `<short decision title>`

Hi all,

**ADR-`<NNNN>`: `<short decision title>`** has been **`<Accepted / Rejected>`** by `<CTO name>`.

- **Decision:** `<we will …>`
- **Status:** `<Accepted / Rejected>` as of `<date>`
- **Record:** `<IcePanel ADR link>`
- **What this means for you:** `<e.g. new work follows this pattern / the alternative is off the table>`

`<If superseding an earlier ADR: This supersedes ADR-NNNN.>`

Thanks to everyone who weighed in.

`<sender name>`
