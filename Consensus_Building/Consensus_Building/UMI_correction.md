# UMI CORRECTION

Example of UMI families that we shall use throughout the correction process.

| UMI | Read count |
|---|---:|
| AACCGGTT | 120 |
| AACCGGTA | 80 |
| AACCGGTC | 75 |
| AACCGATT | 64 |
| AACCGGAT | 24 |
| AACCGCTA | 8 |
| AACCGATA | 5 |
| TCCCGGTT | 4 |
| AACCTGTT | 3 |
| GGGCGGTT | 2 |

Parameters to consider:

```text
MAX_DISTANCE = 1  # Number of mismatches you allow
percentage = 50% # Maximum allowed child UMI abundance relative to the parent UMI
```

---

The correction criteria implemented here is adapted from [UMICollapse tool](https://github.com/Daniel-Liu-c0deb0t/UMICollapse)

## 1. Highest-abundance-first processing

UMIs are processed from highest to lowest abundance so that the largest UMI families are evaluated first as candidate parent UMIs.

| Processing order | UMI | Read count |
|---|---|---:|
| 1 | AACCGGTT | 120 |
| 2 | AACCGGTA | 80 |
| 3 | AACCGGTC | 75 |
| 4 | AACCGATT | 64 |
| 5 | AACCGGAT | 24 |
| 6 | AACCGCTA | 8 |
| 7 | AACCGATA | 5 |
| 8 | TCCCGGTT | 4 |
| 9 | AACCTGTT | 3 |
| 10 | GGGCGGTT | 2 |

The algorithm first evaluates `AACCGGTT` because it has the highest read count. Lower-abundance UMIs are then tested against it using Hamming distance and the abundance rule.

---

The algorithm compares UMI sequences using Hamming distance, which counts the number of nucleotide differences between two UMIs of equal length.

A candidate child UMI is only considered for correction if:

```text
dist ≤ MAX_DISTANCE
```

With `MAX_DISTANCE = 1`, only UMIs differing by one nucleotide or fewer can proceed to abundance-rule evaluation.

In our example UMIs, the following parent-child pairs pass this criterion:

| Parent UMI | Child UMI | Hamming distance (base pair mismatch) | Result |
|---|---|---:|---|
| AACCGGTT | AACCGGTA | 1 | Pass |
| AACCGGTT | AACCGGTC | 1 | Pass |
| AACCGGTT | AACCGGAT | 1 | Pass |
| AACCGGTT | TCCCGGTT | 1 | Pass |
| AACCGGTT | AACCTGTT | 1 | Pass |
| AACCGGTA | AACCGATA | 1 | Pass |

The following parent-child pairs fail this criterion:

| Parent UMI | Child UMI | Hamming distance (base pair mismatch) | Result |
|---|---|---:|---|
| AACCGGTT | AACCGATT | 2 | Fail |
| AACCGGTT | AACCGCTA | 2 | Fail |
| AACCGGTT | AACCGATA | 2 | Fail |
| AACCGGTT | GGGCGGTT | 3 | Fail |

---

## 3. Abundance rule

A lower-abundance child UMI is only merged into a higher-abundance parent UMI if its abundance is sufficiently lower than the parent abundance.

The directional abundance rule is:

```text
child count ≤ 50% × (parent count + 1)
```

For parent `AACCGGTT` with 120 reads:

```text
maximum allowed child count = 50% × (120 + 1) = 60.5
```

Therefore, a child UMI with 60 reads or fewer can pass the abundance rule, while a child UMI above 60.5 reads fails.

---

### Correction decision table

This table shows how all 10 UMIs behave during correction.

| Parent UMI tested | Child UMI | Parent count | Child count | Hamming distance | Abundance threshold | Decision | Reason |
|---|---|---:|---:|---:|---:|---|---|
| AACCGGTT | AACCGGTT | 120 | 120 | 0 | NA | Parent | Highest-abundance UMI retained as parent |
| AACCGGTT | AACCGGTA | 120 | 80 | 1 | 60.5 | Fail | Distance passes, but abundance fails because 80 > 60.5 |
| AACCGGTT | AACCGGTC | 120 | 75 | 1 | 60.5 | Fail | Distance passes, but abundance fails because 75 > 60.5 |
| AACCGGTT | AACCGATT | 120 | 64 | 2 | 60.5 | Fail | Distance fails because 2 > 1 |
| AACCGGTT | AACCGGAT | 120 | 24 | 1 | 60.5 | Pass | Distance and abundance criteria both pass |
| AACCGGTT | AACCGCTA | 120 | 8 | 2 | 60.5 | Fail | Distance fails because 2 > 1 |
| AACCGGTT | AACCGATA | 120 | 5 | 2 | 60.5 | Fail | Distance fails because 2 > 1 |
| AACCGGTT | TCCCGGTT | 120 | 4 | 1 | 60.5 | Pass | Distance and abundance criteria both pass |
| AACCGGTT | AACCTGTT | 120 | 3 | 1 | 60.5 | Pass | Distance and abundance criteria both pass |
| AACCGGTT | GGGCGGTT | 120 | 2 | 3 | 60.5 | Fail | Distance fails because 3 > 1 |

Important examples of UMIs with `MAX_DISTANCE = 1` that still fail merging:

| Parent UMI | Child UMI | Hamming distance | Child count | Threshold | Decision | Reason |
|---|---|---:|---:|---:|---|---|
| AACCGGTT | AACCGGTA | 1 | 80 | 60.5 | Fail | One-base mismatch passes, but abundance is too high |
| AACCGGTT | AACCGGTC | 1 | 75 | 60.5 | Fail | One-base mismatch passes, but abundance is too high |

This shows that a one-base UMI difference alone is not sufficient for merging. The abundance rule must also pass.

---

## 4. Non-transitive merging

Once a child UMI has been merged into a parent UMI, it is marked as assigned and cannot later become a parent itself.

This prevents chain-merging effects such as:

```text
A → B → C
```

For example:

| UMI | Read count |
|---|---:|
| AACCGGTT | 120 |
| AACCGGTA | 80 |
| AACCGATA | 5 |

`AACCGGTA` differs from `AACCGGTT` by one nucleotide, but it fails merging because its read count is too high:

```text
80 > 60.5
```

Therefore, `AACCGGTA` remains an independent parent UMI.

Later, `AACCGATA` can be evaluated against `AACCGGTA`. It differs by one nucleotide and passes the abundance rule:

```text
maximum allowed child count = 50% × (80 + 1) = 40.5

5 ≤ 40.5
```

So `AACCGATA` can be merged into `AACCGGTA`.

After `AACCGATA` is merged, it cannot act as a parent for another UMI. This prevents sequential chain merging and keeps the correction conservative.

---
## 5. Final correction results

The table below summarizes the final correction outcome after applying all correction criteria.

| Parent UMI | Parent count | Child UMIs | Child UMI counts | Corrected to | Corrected count | Hamming distance (base pair mismatch) | Abundance threshold | Final status | Reason |
|---|---:|---|---|---|---:|---|---|---|---|
| AACCGGTT | 120 | AACCGGAT, TCCCGGTT, AACCTGTT | 24, 4, 3 | AACCGGTT | 151 | 1, 1, 1 | 60.5 | Corrected | Passed base pair mismatch and abundance criteria |
| AACCGGTA | 80 | AACCGATA | 5 | AACCGGTA | 85 | 1 | 40.5 | Corrected | Passed base pair mismatch and abundance criteria |
| AACCGGTC | 75 | None | NA | AACCGGTC | 75 | 1 | 60.5 | Retained | Base pair mismatch passes, but abundance threshold fails |
| AACCGATT | 64 | None | NA | AACCGATT | 64 | 2 | 60.5 | Retained | Base pair mismatch exceeds MAX_DISTANCE |
| AACCGCTA | 8 | None | NA | AACCGCTA | 8 | 2 | 60.5 | Retained | Base pair mismatch exceeds MAX_DISTANCE |
| GGGCGGTT | 2 | None | NA | GGGCGGTT | 2 | 3 | 60.5 | Retained | Base pair mismatch exceeds MAX_DISTANCE |


