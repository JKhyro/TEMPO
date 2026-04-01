# TEMPO Interop Boundary

This directory is reserved for the stable C ABI that non-C hosts consume.

The intent is simple:

- native C remains the source of truth
- host layers call across a documented interop boundary
- bindings stay thin and do not become alternate logic owners

Avalonia, tests, and future hosts should depend on this boundary instead of recreating
TEMPO rules in managed code.
