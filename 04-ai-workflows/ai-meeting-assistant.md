# AI Meeting Assistant

## What it does

Takes raw meeting notes from client discussions and extracts:
- Requirements mentioned
- Decisions made
- Action items (with tentative owner, if stated)
- Open questions
- Dependencies and risks flagged in conversation

## Why

Client meetings move fast, and manually re-reading notes to pull out every
requirement and action item is slow and error-prone. AI does the first pass
of extraction so I can focus on validating accuracy rather than transcription.

## The validation step (critical)

AI output is a draft, not a record. Before anything becomes a Jira ticket, a
UAT item, or a tracked action:
- I check every extracted item against my own memory and the raw notes
- I remove anything AI inferred that wasn't actually said
- I confirm owners and deadlines were genuinely stated, not assumed
- Only validated items get logged or ticketed

## Example (illustrative)

**Raw note excerpt:**
> "We talked about the late fee — client wants it configurable per
> municipality, not hardcoded. Priya from their side said she'd confirm the
> exact percentage by Friday. Also flagged that the current export report
> times out on big date ranges."

**AI extraction:**
- Requirement: Late fee percentage must be configurable per municipality (currently hardcoded)
- Action item: Client (Priya) to confirm exact late fee percentage — due Friday
- Issue: Report export times out on large date ranges

**PM validation:** All three confirmed accurate against notes → logged as
I-003 (resolved), tracked action assigned to Priya, and I-002 (in progress)
in the RAID log.
