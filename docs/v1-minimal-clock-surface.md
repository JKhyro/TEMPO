# TEMPO v1 Minimal Clock Surface

## Goal

Ship the first usable TEMPO surface without waiting on unresolved integration work.

## User-Facing Contract

- Show the current time in one visible surface.
- Label the timezone explicitly as `UTC`.
- Refresh once per second.
- Keep the initial surface intentionally narrow: clock first, not calendar or planner.

## Why This Slice First

- It proves TEMPO has a clear product boundary.
- It creates a concrete contract for downstream embedding later.
- It avoids blocking on larger suite coordination work.

## Acceptance Criteria

- One visible clock surface exists.
- The surface shows an explicit timezone label.
- The refresh cadence is defined as one update per second.
- The behavior is documented in this repo.
- No dependency on unresolved items from the integration watchlist is required.

## Out Of Scope For This Slice

- alarms or reminders
- calendar dates or event lists
- timezone switching UI
- preference sync
- cross-product embeds
