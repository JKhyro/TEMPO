# TEMPO Integration Watchlist

This document is a parking area for downstream dependencies. It is not the active v1
execution scope.

| Surface | Why TEMPO Needs It Later | Smallest Useful Shape | Current Blocker / Assumption |
| --- | --- | --- | --- |
| `SYNAPSIS` | Suite shell should eventually embed a stable TEMPO surface. | Read-only clock widget or panel mount point. | TEMPO must first ship a stable standalone clock contract. |
| `SYMBIOSIS` | Platform/runtime surfaces may need canonical time display. | Shared formatting contract and embedded read-only clock. | Host/runtime work should consume TEMPO, not define TEMPO. |
| `ANVIL` | Team operations views may want a shared clock reference. | Dashboard widget with explicit timezone label. | ANVIL should not become the source of truth for time semantics. |
| `NEXUS` | Coordination surfaces may need visible suite time context. | Embedded clock and timestamp formatting contract. | Messaging/coordination requirements should wait until TEMPO v1 is stable. |
| `EPOCH` | Calendar/scheduling work will need a boundary with TEMPO. | Explicit contract split: TEMPO owns clock/time display, EPOCH owns scheduling. | EPOCH and TEMPO boundaries should be documented before any deeper coupling. |

Each downstream embed should consume the TEMPO native C-backed clock contract rather
than fork time logic into its host surface.

## Rule Of Use

If an integration is still speculative, keep it here instead of promoting it into active
v1 implementation scope.
