# AI Change Impact Analysis

## What it does

Analyzes incoming change requests for downstream impact — which components,
data flows, tests, and reports are affected — before the PM commits to a
scope or timeline decision.

## Workflow

```
Change Request → AI Impact Analysis → PM Validation → Development → QA/UAT → Release
```

AI drafts the impact assessment. The PM confirms it's complete and accurate,
adjusts anything AI missed or overstated, and only then takes it to the
client or development team as a scoped change.

## Examples

### CR1 — Merge Duplicate Resident Accounts

**Request:** Add a staff-initiated flow to merge two resident accounts that
were accidentally created for the same person (e.g., one via web signup, one
created manually by municipal staff).

**AI-drafted impact analysis:**
- Data model: requires a account-merge audit table to preserve history
- Payment history: must reconcile transaction records under a single account ID
- Access: staff-only feature, requires role-based permission check
- Reporting: existing per-account reports need to handle merged-account edge cases
- Regression risk: touches autopay setup — need to confirm active autopay survives a merge correctly

**PM validation:** Confirmed scope with client, added one item AI missed
(notifying the resident by email after a merge), and flagged autopay
regression testing as a required QA step before sign-off.

### CR2 — Multi-Currency Fee Display (Pilot for Border Municipalities)

**Request:** For a small pilot group of municipalities near a national
border, display transaction fees in both local and a secondary currency for
resident clarity.

**AI-drafted impact analysis:**
- UI: fee display components need a secondary-currency field, feature-flagged per municipality
- Data logic: requires a currency conversion rate source and refresh cadence
- Reporting: municipal admin reports need to clarify which currency totals are in
- Regression risk: existing single-currency municipalities must be unaffected by the flag

**PM validation:** Confirmed with client that conversion rates would be
manually updated weekly (not live), which simplified the AI's proposed
real-time-rate approach — AI's draft assumed a live feed that wasn't actually
needed.

Both examples show the same pattern: AI identifies technical surface area
quickly; the PM catches what AI assumed versus what was actually agreed, and
that correction is what actually protects the timeline.
