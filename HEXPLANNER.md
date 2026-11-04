# HiGHS fixes from the hexplanner benchmark

These branches start from HiGHS v1.15.1. Each fixes a defect found by benchmarking HiGHS on
conservation prioritization MIPs compiled by prioritizr (see boettiger-lab/hexplanner,
`notes/solver-findings.md`).

| Branch | Fix |
|---|---|
| `fix-dualfixing-substitution-scan` | Presolve dual fixing scanned a whole row for every column with a single lock in it, which is quadratic on rows that hold every column |
| `fix-ipx-divergence-after-optimal` | IPX declared a feasible LP infeasible after diverging from an iterate that met its tolerances |
| `fix-clique-partition-quadratic` | The clique partition in MIP setup was quadratic, in its neighbourhood queries and in re-sorting |
| `hexplanner-fixes` | All three merged; the build benchmarked as `highs-patched3` |

Every branch passes the 168 ctest tests. None of these changes has been proposed upstream yet.
