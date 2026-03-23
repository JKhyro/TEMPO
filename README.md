# TEMPO

TEMPO is the clock and time surface for the broader KHYRON and SYMBIOSIS suite.

The repo is currently in a boundary-first bootstrap phase. The immediate goal is to
define a stable v1 clock contract before deeper cross-system integrations begin.

## What TEMPO Owns

- A canonical clock and time surface for the suite.
- The first shippable visible clock experience.
- Explicit time formatting and refresh behavior for TEMPO-owned surfaces.
- Clear documentation for what belongs in TEMPO versus adjacent products.

## What TEMPO Does Not Own Yet

- Calendar workflow and event scheduling.
- Alarms, reminders, recurrence, or planner behavior.
- Cross-system orchestration for downstream products.
- Per-user timezone preference management.

Those adjacent concerns should stay outside TEMPO v1 until the core clock contract is
stable.

## v1 Time Contract

- Canonical reference time is `UTC`.
- Persisted or exchanged timestamps should be unambiguous and carry either `Z` or an
  explicit UTC offset.
- Operator planning and roadmap notes may still mention `JST` where the existing team
  workflow already does so, but TEMPO's product contract remains UTC-first.
- The first visible clock surface should label its timezone explicitly.

## Immediate v1 Slice

The first executable TEMPO slice is intentionally small:

- one visible clock surface
- one documented timezone rule
- one refresh policy
- no dependency on unresolved integration work

See [docs/product-boundary.md](docs/product-boundary.md),
[docs/v1-minimal-clock-surface.md](docs/v1-minimal-clock-surface.md), and
[docs/integration-watchlist.md](docs/integration-watchlist.md) for the working contract.

## Adjacent Products

- `EPOCH` should own calendar and scheduling concerns.
- `SYNAPSIS` and `SYMBIOSIS` should consume TEMPO's stable clock contract rather than
  define time semantics themselves.
- `ANVIL` and `NEXUS` may eventually embed TEMPO surfaces, but that is downstream of
  the v1 clock contract.
