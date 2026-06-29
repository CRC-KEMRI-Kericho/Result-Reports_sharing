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

| Barcode | Consensus Alignment | Consensus Mapping Against HXB2 |
|---------|----------------------|-------------------------------|
| Barcode01 | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode01/Barcode01_all_family_consensus_aligned.html">Aligned consensus visualization</a> | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode01/Barcode01_HXB2_mapping_report.html">Consensus mapping</a> |
| Barcode02 | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode02/Barcode02_all_family_consensus_aligned.html">Aligned consensus visualization</a> | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode02/Barcode02_HXB2_mapping_report.html">Consensus mapping</a> |
| Barcode03 | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode03/Barcode03_all_family_consensus_aligned.html">Aligned consensus visualization</a> | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode03/Barcode03_HXB2_mapping_report.html">Consensus mapping</a> |
| Barcode05 | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode05/Barcode05_all_family_consensus_aligned.html">Aligned consensus visualization</a> | Not available |

---

# Clean Family Alignments

## Barcode01

| Family | Alignment |
|---------|-----------|
| AAAAGTAG | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode01/clean_families/AAAAGTAG.html">Aligned sequences</a> |
| AAAGATGC | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode01/clean_families/AAAGATGC.html">Aligned sequences</a> |
| AACAATTG | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode01/clean_families/AACAATTG.html">Aligned sequences</a> |
| AACATCGC | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode01/clean_families/AACATCGC.html">Aligned sequences</a> |
| AACCACGT | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode01/clean_families/AACCACGT.html">Aligned sequences</a> |

---

## Barcode02

| Family | Alignment |
|---------|-----------|
| AAAATACC | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode02/clean_families/AAAATACC.html">Aligned sequences</a> |
| AAATCGGC | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode02/clean_families/AAATCGGC.html">Aligned sequences</a> |
| AACCCGT | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode02/clean_families/AACCCGT.html">Aligned sequences</a> |
| AACTACTG | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode02/clean_families/AACTACTG.html">Aligned sequences</a> |
| AAGGTCCG | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode02/clean_families/AAGGTCCG.html">Aligned sequences</a> |
| ACGGGCGT | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode02/clean_families/ACGGGCGT.html">Aligned sequences</a> |
| AGGCGTGC | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode02/clean_families/AGGCGTGC.html">Aligned sequences</a> |

---

## Barcode03

| Family | Alignment |
|---------|-----------|
| AAGAGGAA | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode03/clean_families/AAGAGGAA.html">Aligned sequences</a> |
| GGGGGGTA | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode03/clean_families/GGGGGGTA.html">Aligned sequences</a> |
| GTGAACGC | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode03/clean_families/GTGAACGC.html">Aligned sequences</a> |
| TCGTTAGT | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode03/clean_families/TCGTTAGT.html">Aligned sequences</a> |
| TGTCCTTA | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode03/clean_families/TGTCCTTA.html">Aligned sequences</a> |

---

## Barcode05

| Family | Alignment |
|---------|-----------|
| AAAACGTG | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode05/clean_families/AAAACGTG.html">Aligned sequences</a> |
| AAAGGAAT | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode05/clean_families/AAAGGAAT.html">Aligned sequences</a> |
| ACACCCTG | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode05/clean_families/ACACCCTG.html">Aligned sequences</a> |
| ACAGTGAT | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode05/clean_families/ACAGTGAT.html">Aligned sequences</a> |
| ACATAGTG | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode05/clean_families/ACATAGTG.html">Aligned sequences</a> |

---

# Heterogeneous Families

| Barcode | Family | Alignment | Informative Sites |
|---------|--------|-----------|-------------------|
| Barcode01 | AAAGATGC | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode01/Heterogenous_families/AAAGATGC_heterogenous.html">Aligned sequences</a> | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode01/Heterogenous_families/AAAGATGC_cluster4_10_snp_columns.csv">Informative sites</a> |
| Barcode03 | GTGAACGC | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode03/Heterogenous_families/GTGAACGC_heterogenous.html">Aligned sequences</a> | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode03/Heterogenous_families/GTGAACGC_cluster1_46_snp_columns.csv">Informative sites</a> |
| Barcode05 | ATACGTGT | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode05/Heterogenous_families/ATACGTGT_heterogenous.html">Aligned sequences</a> | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode05/Heterogenous_families/ATACGTGT_snp_columns.csv">Informative sites</a> |
| Barcode05 | GCGGCCTA | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode05/Heterogenous_families/GCGGCCTA_heterogenous.html">Aligned sequences</a> | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode05/Heterogenous_families/GCGGCCTA_snp_columns.csv">Informative sites</a> |
| Barcode05 | TTCACAAG | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode05/Heterogenous_families/TTCACAAG_heterogenous.html">Aligned sequences</a> | <a href="https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Divergent_Heterogenous_families_analysis/Barcode05/Heterogenous_families/TTCACAAG_snp_columns.csv">Informative sites</a> |





