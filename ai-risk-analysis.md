# AI Risk Analysis

## What it does

Uses project context — requirements, dependencies, open change requests — to
surface candidate risks that feed into the RAID log.

## Workflow

AI reviews current project artifacts (requirements docs, dependency list,
active change requests) and proposes potential risks with a brief rationale
for each. It does not assign impact, ownership, or mitigation — that's a PM
judgment call based on knowledge of the client relationship and delivery
constraints AI doesn't have visibility into.

```
Project Context → AI Candidate Risks → PM Assigns Impact/Owner/Mitigation → Logged as Active Risk
```

## Example

**AI-surfaced candidate risk (from CR2 — Multi-Currency Fee Display):**
> "Adding a per-municipality feature flag for currency display increases
> config complexity. Risk of the flag being incorrectly enabled for a
> non-pilot municipality during a future release."

**PM assessment:** Valid risk, but AI didn't know the pilot rollout was
already scoped to use a hard-coded municipality allowlist rather than a
general-purpose flag — so I narrowed the risk description, set impact to
Low, assigned myself as owner, and set mitigation as "code review checklist
item for any release touching the allowlist," rather than the broader
config-management risk AI initially proposed.

This is the recurring pattern across all three AI workflows in this repo: AI
is fast at generating a first draft grounded in visible project data, and the
PM's job is catching what it doesn't have visibility into before anything
becomes official.
