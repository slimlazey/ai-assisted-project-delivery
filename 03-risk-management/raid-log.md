# RAID Log — CivicPay Implementation

Each item tracked as: `Risk → Impact → Owner → Mitigation → Status`

## Risks

| ID | Risk | Impact | Owner | Mitigation | Status |
|---|---|---|---|---|---|
| R-001 | Payment gateway sandbox availability delays end-to-end testing | Medium — could compress UAT window | PM | Escalated to gateway vendor for a dedicated test window | Mitigated |
| R-002 | Municipal staff UAT participants have limited availability during tax season | High — could delay sign-off | PM | Scheduled UAT sessions in short blocks around their peak hours | Monitoring |
| R-003 | Scope creep from informal client requests outside written requirements | Medium — could affect timeline | PM | All new asks routed through formal change request process | Ongoing |

## Assumptions

| ID | Assumption |
|---|---|
| A-001 | Client will provide test resident accounts with representative billing data |
| A-002 | Payment gateway vendor SLAs remain stable through the engagement |
| A-003 | Municipal staff assigned to UAT have authority to sign off on defect severity |

## Issues

| ID | Issue | Status |
|---|---|---|
| I-001 | Autopay confirmation emails delayed under load in staging | Resolved |
| I-002 | Admin console report export timing out for large date ranges | In progress |
| I-003 | Ambiguity in late-fee calculation rules surfaced late in requirements | Resolved via clarification meeting |
| I-004 | Duplicate resident account creation possible under specific edge case | In progress |

## Dependencies

| ID | Dependency | Cross-team? |
|---|---|---|
| D-001 | Payment gateway vendor sandbox credentials | External vendor |
| D-002 | Legacy billing data export (for account matching) | Separate migration vendor |
| D-003 | Municipal staff availability for UAT sign-off | Client |
| D-004 | SSL certificate provisioning for go-live domain | Client IT |
| D-005 | Final branding assets for resident portal | Client marketing team |
