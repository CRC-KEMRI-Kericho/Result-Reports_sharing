# Quality Reports Analysis

## 1. Basecalling and Demultiplexing

The basecalled POD5 files contained a total of **238,589 reads**. These reads were demultiplexed into nine barcodes using the sequencing kit **SQK-NBD114-24**.

Basecalling and demultiplexing were performed using **Dorado v1.3.1** with the following parameters:

dorado basecaller sup -r $DATA_DIR/${pod5_file} --no-trim --device $DEVICE > "$CALLS_BAM"

---

## 2. Quality Control

Adapter, barcode, and primer trimming were carried out using Dorado based on the provided primer and barcode sequences for the kit.

Read quality was assessed using **Sequali**:  
https://github.com/rhpvorderman/sequali

### Read Length Distribution

Reads ranged from:

- < 20 bp  
- > 215,000 bp  

Given the expected final amplicon size of **5300 bp**, reads shorter than **4000 bp** and longer than **5600 bp** were excluded from downstream analysis.

### Quality Filtering

- Majority of reads had Phred scores > 20  
- Low-quality reads (Phred < 7) were removed using **Filtlong**  
  https://github.com/rrwick/Filtlong  

Additional QC metrics evaluated:

- N content per sequence  
- GC percentage  
- Other standard QC parameters  

---

## Detailed Quality Reports

### Barcode01
- Before filtering: https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode01.fastq.html  
- After filtering: https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode01_filtered.fastq.html  

### Barcode02
- Before filtering: https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode02.fastq.html  
- After filtering: https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode02_filtered.fastq.html  

### Barcode03
- Before filtering: https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode03.fastq.html  
- After filtering: https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode03_filtered.fastq.html  

### Barcode04
- Before filtering: https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode04.fastq.html  
- After filtering: https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode04_filtered.fastq.html  

### Barcode05
- Before filtering: https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode05.fastq.html  
- After filtering: https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode05_filtered.fastq.html  

### Barcode06
- Before filtering: https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode06.fastq.html  
- After filtering: https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode06_filtered.fastq.html  

### Barcode07
- Before filtering: https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode07.fastq.html  
- After filtering: https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode07_filtered.fastq.html  

### Barcode08
- Before filtering: https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode08.fastq.html  
- After filtering: https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode08_filtered.fastq.html  

### Barcode09
- Before filtering: https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode09.fastq.html  
- After filtering: https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode09_filtered.fastq.html  

### Unclassified Reads
- Before filtering: https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/unclassified.fastq.html  
- After filtering: https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/unclassified_filtered.fastq.html  

---

## 3. Downstream Analysis

### Sample Metadata

| Sample | Region | Final Product Size | Forward Primer | cDNA Primer | Barcode |
|--------|--------|-------------------|----------------|-------------|----------|
| AD_207_LH | LH | 5300 | gag763 | PB_A(X)_JL68Rv2 | NB01 |
| AD_207_RH | RH | 5300 | PolK3 | PB_A(X)_oligodT_20 | NB02 |
| AD_555_RH | RH | 5300 | PolK3 | PB_A(X)_oligodT_20 | NB03 |
| AD_724_LH | LH | 5300 | gag763 | PB_A(X)_JL68Rv2 | NB04 |
| AD_715_RH | RH | 5300 | PolK3 | PB_A(X)_oligodT_20 | NB05 |
| AD_990_LH | LH | 5300 | gag763 | PB_A(X)_JL68Rv2 | NB06 |
| AD_990_RH | RH | 5300 | PolK3 | PB_A(X)_oligodT_20 | NB07 |
| 40100+40436_LH | LH | 5300 | gag763 | PB_A(X)_JL68Rv2 | NB08 |
| 40100+40436_RH | RH | 5300 | PolK3 | PB_A(X)_oligodT_20 | NB09 |

---

### Current Focus: AD_207

The sequenced regions correspond to:

- gag (LH region)  
- pol (RH region)  

Reads from AD_207_LH (Barcode01) and AD_207_RH (Barcode02) were mapped to the HIV-1 HXB2 reference genome using **minimap2**:  
https://github.com/lh3/minimap2

Genomic positions with read depth ≥ 1000 were selected to highlight strong sequencing support.

The plot shows that the 3′ region of LH reads overlaps with the 5′ region of RH reads, suggesting the possibility of generating a gag–pol consensus sequence.

---

## Outstanding Questions

1. Should LH and RH reads be concatenated per sample to generate a full gag–pol consensus, or analyzed separately?  
2. Would the resulting gag–pol consensus sequence be suitable for intactness analysis?
