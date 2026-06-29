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

### Per Barcode consensus Alignment

Barcode | Consensus Alignment | Consensus mapping against HXB2
Barcode01|



### Clean families alignments

Barcode | Aligned fasta visualizations
Barcode01|1. AAATGC.HTML
          |2. 

#### Heterogenous famillies

Barcode | Aligned fasta visualizations





