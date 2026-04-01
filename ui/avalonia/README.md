# TEMPO Avalonia Host

This directory is reserved for the thin Avalonia host layer.

C# is allowed here only where Avalonia requires it, for example:

- app startup
- window/view composition
- bindings and event wiring
- native interop glue

Do not move TEMPO business logic here unless native C cannot reasonably own it.
