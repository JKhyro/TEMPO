# TEMPO Implementation Direction

## Decision Summary

As of April 1, 2026 JST, TEMPO is a native C-first project.

- Native C is the default language for TEMPO-owned logic.
- Avalonia is the preferred managed desktop host when a UI shell is needed.
- Interop should cross a stable plain-C boundary.
- C# is allowed only where Avalonia or host integration makes it necessary.

## Language Allocation

### Native C Owns

- clock state
- time calculations and conversion rules
- formatting primitives and refresh policy
- domain logic and reusable TEMPO runtime behavior
- platform-neutral logic that should survive host changes

### Avalonia/C# May Own

- application startup required by Avalonia
- windowing, view composition, and UI event wiring
- thin interop glue into the native C core
- host-specific packaging concerns that cannot live in native C

### Avalonia/C# Must Not Own By Default

- canonical time calculations
- clock refresh policy
- TEMPO business rules
- duplicated formatting logic that should remain in the native core

## Interop Rule

Managed hosts should talk to TEMPO through a documented, testable C ABI instead of
reimplementing logic on the managed side. If a host needs richer bindings later, those
bindings should still reduce to the same stable native C boundary.

## Initial Repo Shape

- `native/`: native C source and headers for the canonical TEMPO core
- `interop/`: exported headers and ABI notes for host integration
- `ui/avalonia/`: thin Avalonia host and packaging layer

## v1 Consequence

The first shippable TEMPO clock surface should therefore be built as:

1. a native C clock core
2. a stable native interop boundary
3. a thin Avalonia host that renders the clock without absorbing TEMPO logic
