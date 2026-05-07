# Phred Score and Primer Maximum Error Selection

### Workflow

1. Calculate the percentage of original reads successfully assigned to UMIs to assess overall UMI recovery efficiency.

2. Identify the highest UMI recovery percentage obtained for each barcode to determine the best-performing parameter combination.

3. Among runs with near-optimal UMI recovery, prioritize the:
   - Highest Phred quality score (**MQ**) to favor higher-quality reads.
   - Lowest primer mismatch tolerance (**MAXERR**) to enforce stricter primer matching conditions.

This approach balances:
- read quality,
- UMI recovery efficiency,
- and primer specificity.

---

### Family Size Thresholds

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

### Top Parameter Combinations

The top three parameter combinations identified for each barcode are summarized in the table below.





