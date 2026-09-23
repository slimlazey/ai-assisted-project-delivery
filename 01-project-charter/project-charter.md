# Project Charter — CivicPay Implementation

**Client:** Northbridge Civic Solutions (fictional)
**Engagement type:** Digital municipal payments platform implementation
**Duration:** ~3 months
**Role:** Project Manager — Project Delivery & UAT Coordination

## Background

Northbridge Civic Solutions engaged the delivery team to implement CivicPay, a
platform allowing residents to pay municipal utility bills, property taxes,
and permit fees online, with an admin console for municipal staff to manage
accounts, billing cycles, and reporting.

## Scope

The engagement covers the full delivery lifecycle:

```
Requirements → Development → Testing → UAT → Change Requests → Release Readiness
```

In scope:
- Resident-facing payment portal (bill pay, payment history, autopay setup)
- Municipal staff admin console (account management, billing cycle config, reporting)
- Integration with a third-party payment gateway
- UAT coordination and defect resolution through go-live

Out of scope:
- Mobile app development (web-responsive only for this phase)
- Legacy billing system migration (handled by a separate vendor workstream)

## Stakeholder groups

| Group | Role in project |
|---|---|
| Business / Client (Northbridge) | Requirements sign-off, UAT participation, go-live approval |
| Development | Feature implementation, defect fixes |
| QA / UAT | Test case execution, defect logging |
| Project Manager (this role) | Requirements coordination, Jira/ticket management, UAT coordination, defect tracking, change impact analysis, RAID log management, meeting minutes, release tracking |

## My role

As the sole Project Manager on this engagement, I owned delivery coordination
end-to-end: turning client discussions into documented requirements, keeping
Jira aligned with what was actually agreed, running UAT, tracking defects and
risks, and assessing the impact of every change request before it reached
development.

AI was used throughout as a delivery copilot — accelerating requirement
extraction, meeting documentation, and change-impact drafting — with every
output reviewed and validated by me before it became an action, a ticket, or
a decision.
