# CNTRLPLANE-4826 verification report

Open [index.html](index.html) for the dashboard. The overall verdict is
**pass** for the eight scenarios in the plan, all executed at PR head
`ee5691233b`. The rollout paths that move completion metadata now have live
evidence on CAPI `v1.14.3` and on CAPI `v1.13.4`.

T1 covers the release A→B Replace path, including the unpatched stall and the
patched completion with continuous observation. T2 and T3 cover config-only
and VM-size-only rollouts. T4 and T5 are the unit and reconciliation matrices.
T6 is the scale-to-zero regression. T7 covers a stable pool across an operator
transition. T8 closes the pre-1.14 compatibility row and records explicit
dispositions for the second-provider and InPlace rows.

The authoritative evidence is under `assets/evidence/`; each scenario links to
the artifacts supporting its final result. See [appendices.html](appendices.html)
for the environment, code delta, harness limitations, cleanup and sanitization
record.

All evidence was packaged without contacting the management cluster or Azure.
Original SHA-256 manifests are preserved but explicitly invalidated because
sanitization changed the bytes. Verify the published tree with
`SANITIZED-SHA256SUMS`.
