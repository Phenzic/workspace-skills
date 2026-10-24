---
name: debug
description: Diagnose an error or unexpected behavior, find its likely cause, and validate a focused fix when requested.
---

# Debug

Start from the observed behavior, exact error, and reproduction steps. Inspect relevant logs and code, then trace the failure to a supported cause before proposing a change. If evidence is incomplete, state leading hypotheses and the next useful diagnostic. When asked to fix it, make the smallest reliable change and report any checks actually run.

After a fix, run the smallest relevant check that can establish whether the failure is resolved. When practical, check for regressions. If validation is impossible, explain why and identify the next useful check.