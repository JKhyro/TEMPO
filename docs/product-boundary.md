# TEMPO Product Boundary

## Purpose

TEMPO exists to give the KHYRON suite one clear owner for clock and time display
behavior. The project should answer "what time is it?" and "how should time be shown?"
before it expands into broader scheduling or calendar concerns.

## Owned Surfaces

- The canonical suite clock contract.
- TEMPO-owned visible time displays.
- Time formatting and refresh behavior for TEMPO v1.
- Documentation that defines the boundary between TEMPO and adjacent products.

## Explicit Non-Goals

- Calendar events, recurrence, reminders, or alarms.
- Task scheduling and timeline planning.
- Cross-product workflow orchestration.
- Deep integration dependencies needed before the first TEMPO surface can ship.
- User-specific timezone settings or account synchronization.

## Canonical Decisions For v1

- `UTC` is the canonical reference time.
- TEMPO surfaces must label timezone context explicitly.
- The first visible surface should work without waiting on `SYNAPSIS`, `SYMBIOSIS`,
  `ANVIL`, `NEXUS`, or `EPOCH`.
- Any downstream integration should consume this contract instead of redefining it.

## Exit Criteria For Boundary Work

- The repo README states what TEMPO owns and does not own.
- The v1 clock slice is documented with a visible-surface target and refresh policy.
- The integration watchlist is separated from execution scope.

## Deferred Follow-Up

Once the minimal clock surface exists and the boundary is stable, TEMPO can open
follow-on execution issues for:

- secondary timezone views
- embed contracts for adjacent products
- richer time formatting modes
- eventual handoff points with `EPOCH`
