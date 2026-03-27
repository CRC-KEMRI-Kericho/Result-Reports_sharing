# ONT Consensus Sequence Pipeline

This report includes analysis using custom scripts.  

However, it is important to note that the following end-to-end pipelines exist for generating consensus sequences specifically from ONT data.

1.  Umi-pipeline-nf - [GitHub](https://github.com/genepi/umi-pipeline-nf)
2.  pipeline-umi-amplicon - [GitHub](https://github.com/nanoporetech/pipeline-umi-amplicon?utm_source=chatgpt.com)

## Workflow outline

1. Input Reads Preparation
2. Primer Detection & Orientation
3. UMI Extraction
4. UMI Correction
5. UMI Clustering
6. UMI Family Filtering
7. Consensus Generation
8. Polishing
9. Final Sequences + Report


### Step 1: Input Reads Preparation

FASTQ reads were used directly after basecalling and demultiplexing. 
No adapter trimming was performed at this stage to ensure that the primer sequences, spacer regions, and Unique Molecular Identifiers (UMIs) remained intact for accurate downstream detection and extraction.

### Step: 2. Primer Detection & UMI Extraction

Primer detection was performed using approximate string matching with the edlib aligner in semi-global (HW) mode. A range of maximum edit distance thresholds (MAX_ERROR = 0–8) was systematically evaluated to assess the effect of mismatch tolerance on UMI recovery. For each read, all candidate primer match locations identified within the specified error threshold were evaluated, and the optimal match was selected based on the minimum edit distance.

A strict structural constraint was applied downstream of the primer: an exact match to the spacer sequence (GTG) was required immediately following the primer. Reads satisfying this condition were used to extract an 8 bp UMI (UMI_LEN = 8) located directly after the spacer. Primer mismatch counts were recalculated using global alignment (NW mode) restricted to the primer region to ensure accurate error quantification.

UMI detection was performed on both forward and reverse complement orientations of each read. For reverse-strand matches, positional coordinates were transformed to the original read orientation. The final assignment for each read was determined by selecting the candidate with the lowest mismatch count across both strands.

To evaluate parameter sensitivity, UMI extraction was repeated across all defined MAX_ERROR values (0–8). For each threshold, the total number of reads with valid UMI structures and the corresponding proportion relative to total reads were computed, along with the incremental gain in UMI recovery compared to the previous threshold. This parameter sweep enabled identification of an optimal mismatch threshold balancing sensitivity (UMI recovery) and specificity (correct primer detection) for downstream analysis.

Below is a comparison using a MAX_ERROR of 4 for all the barcodes.


#### UMI Extraction Summary per Barcode

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


The complete results for MAX_ERROR values ranging from 0 to 8 are available here: 

#### MAX_ERROR Sweep Results per Barcode

1. [Barcode01](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode01/Results/umi_sweep.csv)  
2. [Barcode02](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode02/Results/umi_sweep.csv)  
3. [Barcode03](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode03/Results/umi_sweep.csv)  
4. [Barcode04](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode04/Results/umi_sweep.csv)  
5. [Barcode05](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode05/Results/umi_sweep.csv)  
6. [Barcode06](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode06/Results/umi_sweep.csv)  
7. [Barcode07](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode07/Results/umi_sweep.csv)  
8. [Barcode08](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode08/Results/umi_sweep.csv)  
9. [Barcode09](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/barcode09/Results/umi_sweep.csv)  
