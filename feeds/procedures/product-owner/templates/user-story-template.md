# Template: User Story (with AC, INVEST & Definition of Ready)

> **How to use:** Use this for every story that's heading toward the top of the backlog. Write the story and the acceptance criteria yourself; pressure-test the AC and edge cases *with QA*; check INVEST and the Definition of Ready *with the team*. A story isn't ready because you say so — it's ready because the team agrees they could build it without coming back with questions. See [04 — Backlog & Stories](../04-backlog-and-stories.md) and [DoR vs DoD](../../../management/02-dor-and-dod-guide.md).

---

## ─── BLANK TEMPLATE ───────────────────────────────────────────────

---

## Story: [Short title]

**ID:** [KEY-123] · **Theme / Epic:** [roadmap theme] · **Size:** [points]

### Story
**As a** [role / persona],
**I want** [goal / capability],
**so that** [benefit / outcome].

### Why this matters (value)
[One or two lines: the outcome this serves, ideally with the metric it should move.]

### Acceptance Criteria (Given / When / Then)
```
Scenario: [happy path name]
  GIVEN [context / precondition]
  WHEN  [action]
  THEN  [observable result]
  AND   [additional observable result]

Scenario: [edge / unhappy path name]
  GIVEN [context]
  WHEN  [action]
  THEN  [observable result]
```

### Out of scope
- [What this story explicitly does NOT include]

### INVEST checklist
- [ ] **I**ndependent — buildable without waiting on another story
- [ ] **N**egotiable — a problem to solve, not a fixed spec
- [ ] **V**aluable — delivers value to a user or the business on its own
- [ ] **E**stimable — the team understands it enough to size it
- [ ] **S**mall — fits comfortably inside one sprint
- [ ] **T**estable — the AC make "done" verifiable

### Definition of Ready checklist
- [ ] Story has a clear role / goal / benefit
- [ ] Value / outcome is stated
- [ ] Acceptance criteria written and reviewed with QA
- [ ] Dependencies identified (and none block the start)
- [ ] Sized by the team
- [ ] Designs / data / API contracts available if needed
- [ ] Small enough to finish in one sprint

---

## ─── FILLED EXAMPLE ───────────────────────────────────────────────

---

## Story: Send money by phone number

**ID:** WALLET-204 · **Theme / Epic:** Fast, fearless first payment · **Size:** 5 pts

### Story
**As a** first-time Riel Wallet user,
**I want** to send money to someone using just their phone number,
**so that** I don't need to ask them for an account number before my first transfer.

### Why this matters (value)
The #1 support complaint is that the first transfer is confusing because it asks for an account number. Removing that friction is the core of this quarter's outcome: **first-payment-in-24h from 34% → 60%.**

### Acceptance Criteria (Given / When / Then)
```
Scenario: Send to a registered phone number
  GIVEN I am logged in with a balance of $50
  AND   the recipient's phone number belongs to a registered wallet user
  WHEN  I enter the phone number and send $20
  THEN  my balance shows $30
  AND   the recipient receives $20 and a notification
  AND   the transaction appears in my history as "Sent · [name] · $20"

Scenario: Recipient phone number is not registered
  GIVEN I am logged in
  WHEN  I enter a phone number with no wallet account and tap Send
  THEN  I see "This number isn't on Riel Wallet yet — invite them?"
  AND   no money leaves my balance

Scenario: Insufficient balance
  GIVEN my balance is $5
  WHEN  I try to send $20
  THEN  I see "Not enough balance" and the Send button stays disabled

Scenario: Invalid phone number format  [AC #4]
  GIVEN I am on the send screen
  WHEN  I enter a number that isn't a valid Cambodian mobile format
  THEN  I see an inline format error before I can tap Send
```

### Out of scope
- Sending to international numbers (separate story, *Later*).
- Splitting a payment among multiple recipients.

### INVEST checklist
- [x] **I**ndependent — uses the existing transfer service
- [x] **N**egotiable — UI/lookup approach left to the team
- [x] **V**aluable — directly removes the top onboarding friction
- [x] **E**stimable — team sized it at 5 pts in refinement
- [x] **S**mall — fits one sprint
- [x] **T**estable — four scenarios with observable results

### Definition of Ready checklist
- [x] Clear role / goal / benefit
- [x] Value / outcome stated (activation 34% → 60%)
- [x] AC written and reviewed with QA (QA added scenario #4)
- [x] Dependencies identified — phone-lookup API exists
- [x] Sized by the team (5 pts)
- [x] Designs available (send-by-number flow in Figma)
- [x] Small enough for one sprint

---

*Template for the [Product Owner Playbook](../README.md)*
