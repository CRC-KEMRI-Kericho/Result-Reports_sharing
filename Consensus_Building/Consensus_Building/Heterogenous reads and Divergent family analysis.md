# Heterogeneous Read and Divergent UMI Family Analysis

To improve the accuracy of consensus sequence generation, two additional quality-control steps were incorporated into the UMI consensus pipeline:

1. **Sequence identity filtering using VSEARCH**
2. **Within-family SNP-based haplotyping**

## 1. Sequence Identity Filtering Using VSEARCH

Reads within each UMI family were clustered using **VSEARCH** based on nucleotide sequence identity. Three clustering thresholds were evaluated:

- **99% identity:** Over-segmented UMI families into numerous small clusters, including many singletons.
- **98% identity:** Preserved genuine UMI families while effectively separating divergent read populations, providing the best balance between family retention and sequence discrimination.
- **97% identity:** Retained most families as a single large cluster, providing insufficient separation of divergent reads.

Based on these observations, a **98% sequence identity threshold** was selected. Within each UMI family, **all clusters containing at least 10 reads (≥10)** were retained for downstream multiple sequence alignment and consensus generation, while smaller clusters were discarded.

## 2. Within-Family SNP-Based Haplotyping

Clusters retained after VSEARCH filtering were screened for within-family sequence heterogeneity using SNP-based haplotyping.

An alignment position was considered an informative SNP when:

- the **major allele frequency was <80%**, and
- the **minor allele frequency was >30%** of reads within the family.

Reads were grouped according to their SNP haplotypes across all informative positions. Families containing one or more informative SNPs were classified as **heterogeneous**. Supported haplotypes containing **≥10 reads** were retained as independent subfamilies for downstream consensus generation, while the parent heterogeneous families and their informative SNP positions were retained for manual inspection.

These quality-control steps improve the reliability of UMI-family consensus generation by identifying and separating:

- mixed UMI families,
- UMI collisions,
- mis-grouped reads,
- PCR artefacts,
- Nanopore sequencing artefacts,
- chimeric reads, and
- families containing multiple haplotypes.

## Results

### Per Barcode Consensus Alignment

| Barcode | Consensus Alignment | Consensus Mapping to HXB2 |
|---------|----------------------|-------------------------------|
| Barcode02 | [Aligned consensus visualization](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode02/Barcode02_all_family_consensus_aligned.html) | [Consensus mapping](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode02/Barcode02_HXB2_mapping_report.html) |
| Barcode03 | [Aligned consensus visualization](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode03/Barcode03_all_family_consensus_aligned.html) | [Consensus mapping](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode03/Barcode03_HXB2_mapping_report.html) |
| Barcode05 | [Aligned consensus visualization](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode05/Barcode05_all_family_consensus_aligned.html) | [Consensus mapping](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode05/Barcode05_HXB2_mapping_report.html) |

**Note:**

Barcode01 contains many consensus sequences to display in this report. Download the aligned FASTA file [Barcode01_aligned_consensus_sequences](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode01/Barcode01_all_family_consensus_aligned.fasta) and visualize it using Jalview or another compatible multiple sequence alignment viewer.

---

## Clean Family Alignments

## Barcode01

| Family | Alignment |
|---------|-----------|
| AAAAGTAG | [Aligned sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode01/clean_families/AAAAGTAG.html) |
| AAAGATGC | [Aligned sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode01/clean_families/AAAGATGC.html) |
| AACAATTG | [Aligned sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode01/clean_families/AACAATTG.html) |
| AACATCGC | [Aligned sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode01/clean_families/AACATCGC.html) |
| AACCACGT | [Aligned sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode01/clean_families/AACCACGT.html) |

---

## Barcode02

| Family | Alignment |
|---------|-----------|
| AAATCGGC | [Aligned sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode02/clean_families/AAATCGGC.html) |
| AACCCGTT | [Aligned sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode02/clean_families/AACCCGT.html) |
| AACTACTG | [Aligned sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode02/clean_families/AACTACTG.html) |
| AAGGTCCG | [Aligned sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode02/clean_families/AAGGTCCG.html) |
| ACGGGCGT | [Aligned sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode02/clean_families/ACGGGCGT.html) |
| AGGCGTGC | [Aligned sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode02/clean_families/AGGCGTGC.html) |

---

## Barcode03

| Family | Alignment |
|---------|-----------|
| AAGAGGAA | [Aligned sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode03/clean_families/AAGAGGAA.html) |
| GGGGGGTA | [Aligned sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode03/clean_families/GGGGGGTA.html) |
| GTGAACGC | [Aligned sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode03/clean_families/GTGAACGC.html) |
| TCGTTAGT | [Aligned sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode03/clean_families/TCGTTAGT.html) |
| TGTCCTTA | [Aligned sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode03/clean_families/TGTCCTTA.html) |

---

## Barcode05

| Family | Alignment |
|---------|-----------|
| AAAACGTG | [Aligned sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode05/clean_families/AAAACGTG.html) |
| AAAGGAAT | [Aligned sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode05/clean_families/AAAGGAAT.html) |
| ACACCCTG | [Aligned sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode05/clean_families/ACACCCTG.html) |
| ACAGTGAT | [Aligned sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode05/clean_families/ACAGTGAT.html) |
| ACATAGTG | [Aligned sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode05/clean_families/ACATAGTG.html) |

---

## Heterogeneous Families

| Barcode | Family | Alignment | Informative SNPs |
|---------|--------|-----------|-------------------|
| Barcode05 | TTCACAAG | [Aligned sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode05/Heterogenous_families/TTCACAAG_heterogenous.html) | [Informative sites](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode05/Heterogenous_families/TTCACAAG_snp_columns.csv) |
| Barcode03 | GTGAACGC | [Aligned sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode03/Heterogenous_families/GTGAACGC_heterogenous.html) | [Informative sites](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode03/Heterogenous_families/GTGAACGC_cluster1_46_snp_columns.csv) |
| Barcode05 | ATACGTGT | [Aligned sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode05/Heterogenous_families/ATACGTGT_heterogenous.html) | [Informative sites](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode05/Heterogenous_families/ATACGTGT_snp_columns.csv) |
| Barcode05 | GCGGCCTA | [Aligned sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode05/Heterogenous_families/GCGGCCTA_heterogenous.html) | [Informative sites](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode05/Heterogenous_families/GCGGCCTA_snp_columns.csv) |





