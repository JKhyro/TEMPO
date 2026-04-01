# TEMPO Native Core

This directory is reserved for the canonical TEMPO implementation in native C.

Keep the following here by default:

- clock state
- time calculations
- formatting behavior
- refresh policy
- reusable TEMPO runtime logic

If a behavior is part of TEMPO's core product contract, it should start here unless a
clear platform constraint proves otherwise.
