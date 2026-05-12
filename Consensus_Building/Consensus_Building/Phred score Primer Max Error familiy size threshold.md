# Phred Score and Primer Maximum Error Selection

### Workflow

1. Identify the highest UMI recovery percentage obtained for each barcode/sample/participant.

2. Among runs with near-optimal UMI recovery, prioritize the:
   - Highest Phred quality score (**MQ**) to favor higher-quality reads.
   - Lowest primer mismatch tolerance (**MAXERR**) to enforce stricter primer matching conditions.

This approach balances:
- Read quality,
- UMI recovery efficiency and,
- primer specificity.

### Top Parameter Combinations per barcode based on the above criteria

| Barcode | Phred_score_quality_MQ | Max_primer_error | Raw Reads | Reads_retained_after_Quality_filtering | Reads_assigned_to_UMIs | UMI_percent_of_retained_reads |
|---|---:|---:|---:|---:|---:|---:|
| Barcode01 | 14 | 0 | 251757 | 165143 | 151067 | 91.48 |
| Barcode02 | 11 | 1 | 35320 | 18141 | 15731 | 86.72 |
| Barcode03 | 10 | 4 | 182763 | 95965 | 76130 | 79.33 |
| Barcode04 | 14 | 0 | 155571 | 105033 | 94246 | 89.73 |
| Barcode05 | 9 | 3 | 252654 | 152802 | 118478 | 77.54 |
| Barcode06 | 13 | 0 | 441773 | 321313 | 291637 | 90.76 |
| Barcode07 | 10 | 2 | 97921 | 63886 | 55442 | 86.78 |
| Barcode08 | 14 | 0 | 511993 | 356964 | 323660 | 90.67 |
| Barcode09 | 13 | 3 | 99123 | 45577 | 40682 | 89.26 |

---

## UMI Correction

#### 3 main points/Rules:

- Only a single mismatch is allowed when comparing UMIs.
- Low-abundance child UMIs are merged into higher-abundance parent UMIs.
- No chain merging is allowed, which prevents overcollapsing

| Barcode | Reads_assigned_to_UMIs | UMI_families | Corrected_UMI_families_distance1 |
|---|---:|---:|---:|
| Barcode01 | 151067 | 32111 | 14061 |
| Barcode02 | 15731 | 4870 | 3398 |
| Barcode03 | 76130 | 45276 | 17706 |
| Barcode04 | 94246 | 16643 | 8508 |
| Barcode05 | 118478 | 49032 | 17327 |
| Barcode06 | 291637 | 11707 | 5818 |
| Barcode07 | 55442 | 9643 | 5385 |
| Barcode08 | 323660 | 9937 | 4697 |
| Barcode09 | 40682 | 1541 | 1067 |

---
## Family Assignment and Family Size Thresholds

A study by [**Amstler et al. (2024)**](https://link.springer.com/article/10.1186/s13073-024-01391-8) evaluating UMI-based Oxford Nanopore consensus sequence generation for complex VNTR (Variable Number Tandem Repeat) regions 
showed that family-size thresholds between **6 and 10 reads per UMI cluster** were sufficient to achieve high-quality consensus generation, with:

<img width="826" height="805" alt="image" src="https://github.com/user-attachments/assets/7518bd54-fd98-420b-b028-dab7194a283b" />


- **Q40 consensus accuracy** achieved at approximately **6–10 reads per family**.
- **Q50 consensus accuracy** achieved at slightly higher thresholds.

Further reported that at a family size threshold of **6 reads**, the majority of consensus sequences were already:
- error-free, or
- contained no more than two errors.

For the current analysis, a **family-size threshold of 6 reads** will initially be our threshold as a balance between:

- consensus accuracy,
- UMI recovery,
- and retention of sufficient consensus families.

### UMI Famillies analysis table

| Barcode | Corrected_UMI_families_distance1 | Family_size_>=6 | Family_size_>=7 | Family_size_>=8 | Family_size_>=9 | Family_size_>=10 |
|---|---:|---:|---:|---:|---:|---:|
| Barcode01 | 14061 | 3311 | 2903 | 2606 | 2373 | 2184 |
| Barcode02 | 3398 | 199 | 171 | 152 | 143 | 134 |
| Barcode03 | 17706 | 4063 | 3334 | 2781 | 2324 | 1896 |
| Barcode04 | 8508 | 1414 | 1218 | 1076 | 960 | 889 |
| Barcode05 | 17327 | 5782 | 4839 | 4120 | 3529 | 3085 |
| Barcode06 | 5818 | 1213 | 1108 | 1035 | 969 | 916 |
| Barcode07 | 5385 | 766 | 635 | 558 | 507 | 477 |
| Barcode08 | 4697 | 1183 | 1111 | 1070 | 1034 | 1004 |
| Barcode09 | 1067 | 494 | 486 | 478 | 475 | 472 |

----End of Report----




