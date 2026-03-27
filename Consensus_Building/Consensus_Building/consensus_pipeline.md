# ONT Consensus Sequence Pipeline

This report includes analysis using custom scripts.

For reference, established end-to-end pipelines for ONT UMI-based consensus generation include:

1. Umi-pipeline-nf - [GitHub](https://github.com/genepi/umi-pipeline-nf)  
2. pipeline-umi-amplicon - [GitHub](https://github.com/nanoporetech/pipeline-umi-amplicon?utm_source=chatgpt.com)  

---

## Workflow Outline

1. Input Reads Preparation  
2. Primer Detection & UMI Extraction  
3. UMI Correction  
4. UMI Family Filtering  
5. Consensus Generation  
6. Polishing  
7. Final Sequences + Report  

---

## Step 1: Input Reads Preparation

FASTQ reads were used directly after basecalling and demultiplexing.  
No adapter trimming was performed at this stage to ensure that primer sequences, spacer regions, and Unique Molecular Identifiers (UMIs) remained intact for accurate downstream detection and extraction.

---

## Step 2: Primer Detection & UMI Extraction

Primer detection was performed using approximate string matching with the edlib aligner in semi-global (HW) mode. A range of maximum edit distance thresholds (MAX_ERROR = 0–8) was evaluated to assess the effect of mismatch tolerance on UMI recovery. For each read, all candidate primer match locations identified within the specified error threshold were evaluated, and the optimal match was selected based on the minimum edit distance.

A strict structural constraint was applied downstream of the primer: an exact match to the spacer sequence (GTG) was required immediately following the primer. Reads satisfying this condition were used to extract an 8 bp UMI (UMI_LEN = 8) located directly after the spacer. Primer mismatch counts were recalculated using global alignment (NW mode) restricted to the primer region to ensure accurate error quantification.

UMI detection was performed on both forward and reverse complement orientations of each read. For reverse-strand matches, positional coordinates were transformed to the original read orientation. The final assignment for each read was determined by selecting the candidate with the lowest mismatch count across both strands.

To evaluate parameter sensitivity, UMI extraction was repeated across all defined MAX_ERROR values (0–8). For each threshold, the total number of reads with valid UMI structures and the corresponding proportion relative to total reads were computed, along with the incremental gain in UMI recovery compared to the previous threshold. This parameter sweep enabled identification of an optimal mismatch threshold balancing sensitivity (UMI recovery) and specificity (correct primer detection) for downstream analysis.

Below is a comparison using MAX_ERROR = 4 across all barcodes.

### UMI Extraction Summary per Barcode

| Barcode   | Total Reads | Reads with UMI | Reads without UMI | UMI (%) |
|----------|------------|----------------|-------------------|---------|
| barcode01 | 23599 | 12216 | 11383 | 51.76 |
| barcode02 | 3804  | 2175  | 1629  | 57.18 |
| barcode03 | 16340 | 6973  | 9367  | 42.67 |
| barcode04 | 15960 | 8614  | 7346  | 53.97 |
| barcode05 | 22519 | 8459  | 14060 | 37.56 |
| barcode06 | 40088 | 23365 | 16723 | 58.28 |
| barcode07 | 10023 | 5703  | 4320  | 56.90 |
| barcode08 | 45611 | 27993 | 17618 | 61.37 |
| barcode09 | 9815  | 6646  | 3169  | 67.71 |

*Note: “Reads with UMI” corresponds to total UMIs prior to clustering, as each read is associated with a single UMI.*

### MAX_ERROR Sweep Results

The complete dataset for all evaluated MAX_ERROR thresholds (0–8) is available below:

1. [Barcode01](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode01/Results/umi_sweep.csv)  
2. [Barcode02](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode02/Results/umi_sweep.csv)  
3. [Barcode03](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode03/Results/umi_sweep.csv)  
4. [Barcode04](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode04/Results/umi_sweep.csv)  
5. [Barcode05](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode05/Results/umi_sweep.csv)  
6. [Barcode06](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode06/Results/umi_sweep.csv)  
7. [Barcode07](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode07/Results/umi_sweep.csv)  
8. [Barcode08](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode08/Results/umi_sweep.csv)  
9. [Barcode09](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode09/Results/umi_sweep.csv)  

### Per-read UMI Information

Detailed per-read information, including identified primer sequences, UMIs, strand orientation, and read lengths, is available via the links below:

*Note: These files are large (they contain all reads with UMIs). It is advisable to download them and open in Excel for better visualization.*

1. [Barcode01](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode01/Results/barcode01.umi_per_read.csv)  
2. [Barcode02](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode02/Results/barcode02.umi_per_read.csv)  
3. [Barcode03](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode03/Results/barcode03.umi_per_read.csv)  
4. [Barcode04](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode04/Results/barcode04.umi_per_read.csv)  
5. [Barcode05](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode05/Results/barcode05.umi_per_read.csv)  
6. [Barcode06](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode06/Results/barcode06.umi_per_read.csv)  
7. [Barcode07](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode07/Results/barcode07.umi_per_read.csv)  
8. [Barcode08](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode08/Results/barcode08.umi_per_read.csv)  
9. [Barcode09](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode09/Results/barcode09.umi_per_read.csv)  

---

## Step 3: UMI Correction

UMI correction was performed using a strand-aware, abundance-guided directional adjacency approach to cluster similar UMIs while minimizing over-collapsing of distinct molecules.

For each strand independently, UMIs were sorted by abundance and treated as candidate root sequences. Each high-abundance UMI was compared against all other UMIs, and neighboring UMIs within a Hamming distance threshold (≤2) were considered for merging. A lower-abundance UMI was absorbed into a higher-abundance UMI only if the abundance criterion (count_high ≥ 2 × count_low − 1) was satisfied.

This approach performs single-step (star-like) collapsing, where UMIs are directly assigned to the most abundant compatible root without iterative propagation through intermediate nodes. As a result, merging is restricted to local neighborhoods, reducing the risk of chain-based over-collapsing.

Overall, this strategy provides a conservative clustering of UMIs into molecular families, balancing error correction with preservation of distinct molecular signals.

UMI correction substantially reduced the number of UMI families across all barcodes, indicating effective collapsing of sequencing and PCR-induced UMI errors. The remaining singleton families represent low-support or unique molecules that could not be confidently merged.

### UMI Correction Summary per Barcode

| Barcode   | Total UMIs | Families Before | Families After | Singleton Families |
|----------|------------|-----------------|----------------|--------------------|
| barcode01 | 12216 | 4978 | 1051 | 184 |
| barcode02 | 2175  | 1027 | 498  | 212 |
| barcode03 | 6973  | 6489 | 1084 | 232 |
| barcode04 | 8614  | 2642 | 815  | 218 |
| barcode05 | 8459  | 7102 | 1093 | 220 |
| barcode06 | 23365 | 2268 | 789  | 144 |
| barcode07 | 5703  | 1564 | 608  | 180 |
| barcode08 | 27993 | 2284 | 873  | 80  |
| barcode09 | 6646  | 834  | 423  | 86  |

### UMI Family Composition After Correction

1. [Barcode01](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode01/Results/barcode01.umi_groups_corrected.csv)  
2. [Barcode02](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode02/Results/barcode02.umi_groups_corrected.csv)  
3. [Barcode03](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode03/Results/barcode03.umi_groups_corrected.csv)  
4. [Barcode04](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode04/Results/barcode04.umi_groups_corrected.csv)  
5. [Barcode05](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode05/Results/barcode05.umi_groups_corrected.csv)  
6. [Barcode06](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode06/Results/barcode06.umi_groups_corrected.csv)  
7. [Barcode07](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode07/Results/barcode07.umi_groups_corrected.csv)  
8. [Barcode08](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode08/Results/barcode08.umi_groups_corrected.csv)  
9. [Barcode09](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode09/Results/barcode09.umi_groups_corrected.csv)  

### Corrected UMI Assignments (Per-Read)

1. [Barcode01](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode01/Results/barcode01.umi_per_read_corrected.csv)  
2. [Barcode02](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode02/Results/barcode02.umi_per_read_corrected.csv)  
3. [Barcode03](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode03/Results/barcode03.umi_per_read_corrected.csv)  
4. [Barcode04](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode04/Results/barcode04.umi_per_read_corrected.csv)  
5. [Barcode05](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode05/Results/barcode05.umi_per_read_corrected.csv)  
6. [Barcode06](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode06/Results/barcode06.umi_per_read_corrected.csv)  
7. [Barcode07](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode07/Results/barcode07.umi_per_read_corrected.csv)  
8. [Barcode08](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode08/Results/barcode08.umi_per_read_corrected.csv)  
9. [Barcode09](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode09/Results/barcode09.umi_per_read_corrected.csv)  

---

## Step 4: UMI Family Filtering (currently ongoing)

----End----
