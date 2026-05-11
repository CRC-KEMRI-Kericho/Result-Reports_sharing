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

| Barcode | Rank | Phred_score_quality_MQ | Max_primer_error | Raw Reads | Reads_retained_after_quality filtering| Reads_assigned_to_UMIs | UMI_percent_of_retained_reads |
|---|---:|---:|---:|---:|---:|---:|---:|
| Barcode01 | 1 | 17 | 0 | 251757 | 152643 | 140858 | 92.28 |
| Barcode02 | 1 | 14 | 0 | 35320 | 16035 | 14070 | 87.75 |
| Barcode03 | 1 | 12 | 2 | 182763 | 84780 | 67467 | 79.58 |
| Barcode04 | 1 | 17 | 0 | 155571 | 93967 | 85246 | 90.72 |
| Barcode05 | 1 | 11 | 1 | 252654 | 137586 | 106532 | 77.43 |
| Barcode06 | 1 | 17 | 0 | 441773 | 281978 | 259820 | 92.14 |
| Barcode07 | 1 | 14 | 0 | 97921 | 56805 | 49163 | 86.55 |

---

### UMI Correction, Family Assignment, and Family Size Thresholds Determination

A study by [**Amstler et al. (2024)**](https://link.springer.com/article/10.1186/s13073-024-01391-8) evaluating UMI-based Oxford Nanopore consensus sequence generation for complex VNTR (Variable Number Tandem Repeat) regions 
showed that family-size thresholds between **6 and 10 reads per UMI cluster** were sufficient to achieve high-quality consensus generation, with:

<img width="826" height="805" alt="image" src="https://github.com/user-attachments/assets/7518bd54-fd98-420b-b028-dab7194a283b" />


- **Q40 consensus accuracy** achieved at approximately **6–10 reads per family**.
- **Q50 consensus accuracy** achieved at slightly higher thresholds.

Further reported that at a family size threshold of **6 reads**, the majority of consensus sequences were already:
- error-free, or
- contained no more than two errors.

For the current analysis, a **family-size threshold of 8 reads** will initially be our threshold as a balance between:

- consensus accuracy,
- UMI recovery,
- and retention of sufficient consensus families.

However, this threshold may vary depending on the barcode-specific assessments summarized in the table below.

---

### UMI Famillies analysis table

| Barcode | Reads_assigned_to_UMIs | UMI_families | Corrected_UMI_families_distance1 | Family_size_>=6 | Family_size_>=7 | Family_size_>=8 | Family_size_>=9 | Family_size_>=10 |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Barcode01 | 140858 | 30154 | 13349 | 3112 | 2747 | 2471 | 2231 | 2055 |
| Barcode02 | 14070 | 3854 | 2820 | 179 | 158 | 145 | 134 | 130 |
| Barcode03 | 67467 | 41752 | 16771 | 3418 | 2860 | 2436 | 2053 | 1723 |
| Barcode04 | 85246 | 15140 | 7933 | 1286 | 1110 | 991 | 885 | 825 |
| Barcode05 | 106532 | 45638 | 16331 | 4590 | 4080 | 3574 | 3183 | 2811 |
| Barcode06 | 259820 | 9868 | 5133 | 1085 | 986 | 931 | 884 | 851 |
| Barcode07 | 49163 | 6728 | 4232 | 587 | 523 | 476 | 436 | 426 |
| Barcode08 | 292198 | 8412 | 4129 | 1101 | 1049 | 1015 | 988 | 976 |
| Barcode09 | 36076 | 1281 | 906 | 485 | 481 | 470 | 467 | 456 |




