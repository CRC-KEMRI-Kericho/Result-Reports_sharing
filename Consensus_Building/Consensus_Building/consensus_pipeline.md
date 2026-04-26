# ONT Consensus Sequence Pipeline

This report includes analysis using custom scripts.

For reference, established end-to-end pipelines for ONT UMI-based consensus generation include:

1. Umi-pipeline-nf - [GitHub](https://github.com/genepi/umi-pipeline-nf)  
2. pipeline-umi-amplicon - [GitHub](https://github.com/nanoporetech/pipeline-umi-amplicon?utm_source=chatgpt.com)  

---

## Workflow Outline

1. Input Reads Pre-Processing  
2. Primer Detection & UMI Extraction  
3. UMI Correction  
4. UMI Family Filtering  
5. Consensus Generation  
6. Polishing  
7. Final Sequences + Report  

---

## Step 1: Input Reads Pre-Processing 
 
Basecalled and demultiplexed FASTQ reads were pre-processed by retaining reads with lengths between 1,000 and 50,000 bp and a minimum mean quality score of Q7.

The table below shows the reads before and after filtering

| Barcode      | Reads Before filtering | Reads After filtering | Removed Reads | % of reads Retained |
| ------------ | ---------------------- | --------------------- | ------------- | ---------------------------- |
| Barcode01    |                251,757 |               237,905 |        13,852 |                        94.50 |
| Barcode02    |                 35,320 |                30,651 |         4,669 |                        86.78 |
| Barcode03    |                182,763 |               165,340 |        17,423 |                        90.47 |
| Barcode04    |                155,571 |               149,050 |         6,521 |                        95.81 |
| Barcode05    |                252,654 |               223,828 |        28,826 |                        88.59 |
| Barcode06    |                441,773 |               423,413 |        18,360 |                        95.84 |
| Barcode07    |                 97,921 |                92,504 |         5,417 |                        94.47 |
| Barcode08    |                511,993 |               489,314 |        22,679 |                        95.57 |
| Barcode09    |                 99,123 |                93,150 |         5,973 |                        93.97 |

---

## Step 2: Primer Detection & UMI Extraction

Primer–UMI structures were detected bidirectionally using edlib semi-global matching against the expected primer, allowing up to 8 mismatches with a maximum of 1 mismatch in the core region (positions 4–22), requiring an exact downstream spacer (GTG) plus an 8 bp UMI within the first 200 bp of read ends.

### UMI Extraction Summary per Barcode

| barcode      | Total_Reads | Reads_with_UMI | Primer_Only_Reads | No Primer/Spacer/Degraded | UMI_Percentage |
| ------------ | ----------: | -------------: | ----------------: | --------------------------: | -------------: |
| Barcode01    |     237,905 |        190,961 |            40,105 |                       6,839 |          80.27 |
| Barcode02    |      30,651 |         24,407 |             5,750 |                         494 |          79.63 |
| Barcode03    |     165,340 |        119,407 |            43,953 |                       1,980 |          72.22 |
| Barcode04    |     149,050 |        121,999 |            22,288 |                       4,763 |          81.85 |
| Barcode05    |     223,828 |        152,337 |            60,955 |                      10,536 |          68.06 |
| Barcode06    |     423,413 |        360,000 |            48,488 |                      14,925 |          85.02 |
| Barcode07    |      92,504 |         75,971 |            14,136 |                       2,397 |          82.13 |
| Barcode08    |     489,314 |        416,726 |            51,082 |                      21,506 |          85.17 |
| Barcode09    |      93,150 |         76,529 |            12,122 |                       4,499 |          82.16 |


## Step 3: UMI Correction

UMI correction was performed using a conservative graph-based denoising approach designed to collapse likely sequencing-error UMIs while preserving biologically distinct molecules. Correction decisions were based on UMI sequence similarity, family abundance, and strand orientation, with no use of read sequence alignment or amplicon content.


### Rules/Conditions for UMI Collapsing

**1. Strand-orientation aware correction:** UMIs are corrected separately within each strand orientation, so reads from opposite orientations are never merged, preventing biologically distinct molecules from being incorrectly combined.
   
**2. Distance threshold:** **A child UMI can only collapse into a parent if its Hamming distance from the parent is less than or equal to the allowed mismatch threshold (MAX_DISTANCE), limiting merges to UMIs that differ only by small probable sequencing errors.

**3. Abundance dominance rule:** A merge is only allowed when the parent count is sufficiently larger than the child count, following parent ≥ (2 × child) − 1, reducing the risk of collapsing two genuinely abundant independent molecules.

**4. Abundance-priority parent selection:** The most abundant UMI in each strand orientation is evaluated first and used as the potential parent/root for collapsing lower-count neighbors, helping ensure likely true molecules absorb likely sequencing-error variants.

**5. No chain merging:** Once a low-count UMI is merged into a parent, it cannot later act as a parent for other UMIs, preventing transitive over-collapsing where multiple distinct UMIs are incorrectly merged through an intermediate error UMI.


----End----
