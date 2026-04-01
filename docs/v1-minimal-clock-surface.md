# TEMPO v1 Minimal Clock Surface

## Goal

Ship the first usable TEMPO surface without waiting on unresolved integration work.

## User-Facing Contract

- Show the current time in one visible surface.
- Label the timezone explicitly as `UTC`.
- Refresh once per second.
- Keep the initial surface intentionally narrow: clock first, not calendar or planner.

## Technical Shape

- Native C owns clock state, refresh cadence, formatting, and time calculations.
- A stable C ABI should expose the native core to non-C hosts.
- Avalonia provides the first desktop host surface through native C interop.
- C# stays limited to Avalonia startup, UI composition, and the interop glue that
  cannot live in native C.

## Why This Slice First

- It proves TEMPO has a clear product boundary.
- It creates a concrete contract for downstream embedding later.
- It avoids blocking on larger suite coordination work.

## Acceptance Criteria

- One visible clock surface exists.
- The surface shows an explicit timezone label.
- The refresh cadence is defined as one update per second.
- Native C owns the clock behavior that drives the surface.
- The Avalonia host consumes the native core through a documented C interop boundary.
- C# does not become the home of TEMPO business logic.
- The behavior is documented in this repo.
- No dependency on unresolved items from the integration watchlist is required.

## Out Of Scope For This Slice

- alarms or reminders
- calendar dates or event lists
- timezone switching UI
- preference sync
- cross-product embeds
