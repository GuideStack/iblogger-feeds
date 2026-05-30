# Progress Report Procedure — Daily & Weekly

Standard Operating Procedure (SOP). This is an internal process document, not a legal contract.

This procedure defines how each team member reports their own progress so the PM can keep an accurate picture of the sprint. There are two reports: a short **daily** update and a fuller **weekly** summary. Each member sends their own; the PM aggregates.

## Document Control

| Field | Value |
|-------|-------|
| Document type | Internal Standard Operating Procedure (SOP) |
| Document owner | `<name / role responsible for maintaining this doc>` |
| Version | `<1.0>` |
| Status | `<Draft / Approved>` |
| Effective date | `<YYYY-MM-DD>` |
| Next review date | `<YYYY-MM-DD>` |
| Applies to | Dev, QA, PM, PO on `<team / project>` |

---

## Table of Contents
1. Purpose
2. Who Reports, When, and to Whom
3. What Goes in a Report
4. Daily Report Email Template
5. Weekly Report Email Template
6. Rules
7. Change Log

---

## 1. Purpose

A progress report keeps the team and PM aligned without a meeting. It answers three questions: **what moved, what is blocked, and what is next.** It uses the same Jira statuses as the [Ticket Sign-Off Procedure](signoff-jira-ticket-procedure.md), so a report is just a plain-language view of the board.

A report is a status update, not a justification. It should take a few minutes to write.

---

## 2. Who Reports, When, and to Whom

| Report | Who sends | When | To |
|--------|-----------|------|----|
| Daily | Each Dev and QA | Every working day, by `<time, e.g. 10:00>` (after standup) | Team + PM |
| Weekly | Each Dev and QA | End of the last working day of the week (`<e.g. Friday>`) | Team + PM |

- Each member reports **their own** tickets — not the whole board.
- The **PM aggregates** the individual reports into the sprint picture (and may forward a summary to the PO / stakeholders).
- If a member is out, they note it in advance; no report is expected for days off.

---

## 3. What Goes in a Report

Keep each item tied to a **Jira ticket key** and its **current status**, so the report and the board agree.

- **Done / moved forward** — tickets you moved to a new status since the last report (e.g. "PAY-142 → In Reviews").
- **In progress** — what you are actively working on and its status.
- **Blocked / at risk** — anything stuck, why, and who you need. (A blocker open more than 1 working day must be flagged here and at standup — see the Ticket Sign-Off Procedure.)
- **Next** — what you will pick up next.

If nothing changed, say so honestly ("No movement on PROJ-201 — still blocked on the API key"). A flat report is information, not failure.

---

## 4. Daily Report Email Template

*Sent by each Dev / QA every working day. Keep it short — one line per ticket.*

**To:** `<team list>`, `<PM>`
**Subject:** [Daily] `<your name>` — `<YYYY-MM-DD>`

Hi team,

| What | Ticket | Title | Status | Note |
|------|--------|-------|--------|------|
| Moved yesterday | `<PROJ-001>` | `<title>` | → `<new status>` | — |
| Working on today | `<PROJ-003>` | `<title>` | `<current status>` | `<what specifically>` |
| Blocked / at risk | `<PROJ-004>` | `<title>` | `<status>` | `<blocker, who I need (open since <date>)>` |
| Next up | `<PROJ-005>` | `<title>` | `<status>` | — |

`<Blockers: None — remove the row if nothing is blocked.>`

`<your name>`

---

## 5. Weekly Report Email Template

*Sent by each Dev / QA at the end of the week. Fuller than the daily — a summary of the week, not a copy of five dailies.*

**To:** `<team list>`, `<PM>`
**Subject:** [Weekly] `<your name>` — week of `<YYYY-MM-DD>`

Hi team,

**Completed this week** (reached Done or moved significantly forward)

| Ticket | Title | Status |
|--------|-------|--------|
| `<PROJ-001>` | `<title>` | `<Done / now in QA / etc.>` |
| `<PROJ-002>` | `<title>` | `<status>` |

**In progress (carrying into next week)**

| Ticket | Title | Status | What remains |
|--------|-------|--------|--------------|
| `<PROJ-003>` | `<title>` | `<status>` | `<% / what's left>` |

**Blocked / at risk**

| Ticket | Blocker | Who I need | Since |
|--------|---------|------------|-------|
| `<PROJ-004>` | `<what's blocking>` | `<role/name>` | `<date>` |

`<None — remove this table if nothing is blocked.>`

**Planned for next week**

| Ticket | Title |
|--------|-------|
| `<PROJ-005>` | `<title>` |
| `<PROJ-006>` | `<title>` |

**Notes for the PM** *(optional):* `<capacity, time off, anything that affects the plan>`

`<your name>`

---

## 6. Rules

1. Report your own work. Each member reports their own tickets; the PM aggregates — no one reports for the whole team.
2. Tie every item to a ticket and status. A report mirrors the Jira board; if they disagree, fix the board.
3. Be honest about blockers. Flag anything stuck — especially blockers open more than 1 working day — rather than hiding a stall.
4. Keep it short. Daily = one line per ticket in the table; weekly = a summary, not five dailies pasted together. Delete any table rows or sections that don't apply.
5. Consistent timing. Send by the agreed time so the PM can aggregate before reporting upward.
6. Frozen during a sprint. The report format is not changed mid-sprint; suggest changes at the retrospective.

---

## 7. Change Log

| Version | Date | Author | Change |
|---------|------|--------|--------|
| 1.0 | `<YYYY-MM-DD>` | `<name>` | Initial version |
