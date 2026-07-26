# Lab 10 — Incident and Change Management Documentation

## Objective
Create records that allow another technician, manager, auditor or customer to understand what happened, what was done and what must happen next.

## Incident lifecycle

`Identify → Log → Categorise → Prioritise → Diagnose → Escalate → Resolve → Confirm → Close → Review`

## Incident record fields

| Field | Good practice |
|---|---|
| Short description | One clear symptom and affected scope |
| Impact | Number of users/services and business effect |
| Urgency | Required restoration speed |
| Timeline | Time-stamped events in chronological order |
| Diagnostics | Commands, logs, tests and results |
| Root cause | Confirmed cause; never guess |
| Resolution | Exact action that restored service |
| Verification | Technical evidence and user confirmation |
| Follow-up | Problem, monitoring, knowledge or prevention task |

## Change request fields

| Field | Question |
|---|---|
| Title and reason | What is changing and why? |
| Scope | Which users, devices, services and sites? |
| Risk and impact | What can fail and what is the business effect? |
| Implementation | Ordered steps, owner and evidence |
| Test plan | How will success be measured? |
| Rollback | How and by when will the previous state be restored? |
| Schedule | Start, end, outage window and dependencies |
| Approval | Who approves based on risk and type? |
| Communication | Who needs notice before, during and after? |
| Review | Were objectives met and were incidents introduced? |

## Example controlled deployment

1. Pilot a Microsoft 365 app to a representative test group.
2. Record prerequisites, package version, Intune assignment and detection rules.
3. Monitor installation success and user impact.
4. Define rollback through unassignment, uninstall or restored configuration.
5. Communicate the schedule and support route.
6. Expand in controlled rings after pilot success.
7. Close with success metrics and lessons learned.

## Documentation rule
Write what you observed, what you did and what proved the result. Clearly separate confirmed fact from assumption. Never paste passwords, tokens, personal data or unnecessary full logs.

## Interview answer

> An incident restores a degraded or unavailable service. A change introduces a controlled modification. An emergency change may resolve an incident, but it still requires proportionate risk assessment, approval, implementation, rollback and documentation.

---
[Home](../README.md) • [Incident template](../templates/incident-record-template.md) • [Change template](../templates/change-request-template.md) • [GitHub](https://github.com/toannguyenitoz) • [LinkedIn](https://www.linkedin.com/in/toan-nguyen-it-oz/)