# Comparison of Final Consensus Outputs Between the In-house and Customized PORPID Pipelines

## 1. Number of Final Consensus Outputs

This comparison includes final consensus sequences generated using:

1. The **in-house pipeline**.
2. The **customized PORPID pipeline**.
3. The **customized PORPID pipeline with rescue logic applied**.

For the PORPID rescue analysis, rejected consensus sequences were rescued and included in the final consensus output when rejection was caused by a **single position** with a minimum agreement **below 0.70 but at or above 0.50**.

| Sample | No. of In-house Seqs | No. of PORPID Seqs | No. of PORPID Seqs With Rescue | No. of Common UMIs | Difference (In-house − PORPID) |
|---|---:|---:|---:|---:|---:|
| bc2001 | 442 | 414 | 436 | 387 | +28 |
| bc2002 | 793 | 257 | 789 | 229 | +536 |
| bc2003 | 1,698 | 1,512 | 1,601 | 1,440 | +186 |
| bc2004 | 464 | 414 | 436 | 395 | +50 |
| bc2005 | 287 | 261 | 282 | 247 | +26 |
| bc2006 | 737 | 491 | 717 | 464 | +246 |
| bc2007 | 691 | 622 | 650 | 598 | +69 |
| bc2008 | 407 | 452 | 474 | 364 | −45 |
| bc2009 | 4,416 | 4,170 | 4,170 | 3,735 | +246 |

---

## 2. Analysis of the Common UMIs

The in-house consensus sequences contained an additional **20-bp motif** at the 3′ end:

```text
AAGCCTCAATAAAGCTTGCC
```

This motif corresponds to part of the **28-bp specific primer sequence**:

```text
AAGCCTCAATAAAGCTTGCCTTGAGTGC
```

Other than this additional primer-derived motif, the lengths of the corresponding sequences from the two pipelines remained identical.

### Alignment Examples

| Common UMI | Alignment |
|---|---|
| `bc2001_ACGCCCTC` | [View alignment](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/pacbio/bc2001_ACGCCCTC.svg) |
| `bc2002_AGGACCAG` | [View alignment](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/pacbio/bc2002_AGGACCAG.svg) |
| `bc2003_ATGGTGAC` | [View alignment](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/pacbio/bc2003_ATGGTGAC.svg) |
| `bc2004_GGACCCTA` | [View alignment](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/pacbio/bc2004_GGACCCTA.svg) |
| `bc2005_TGGGATTC` |  [View alignment](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/pacbio/bc2005_TGGGATTC.svg) |

---

## 3. Recommendations

The **in-house pipeline** is recommended for adoption. However, the following points should be discussed before finalizing the pipeline configuration:

- **Specific primer trimming:** Decide whether the specific primer sequence should be **fully trimmed** from the final consensus sequences or **left fully intact**. This requires further consultation.
- **Minimum Phred quality score:** Consider increasing the current minimum Phred quality score from **Q18**, given improvements in sequencing technology and the associated reduction in sequencing errors.
- **Minimum UMI family size:** Consider increasing the minimum family size from the current **5 reads to 7 reads** to improve confidence in consensus sequence generation and consensus-call quality.


