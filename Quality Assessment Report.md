# Quality Reports Analysis

## Step 1. Basecalling 
Tool: **Dorado v1.3.1** [Github](https://github.com/nanoporetech/dorado)

Parameters and command used.
```
dorado basecaller sup -r $DATA_DIR/${pod5_file} \
    --no-trim \
    --device $DEVICE \
    > "$CALLS_BAM"
```

## Step 2: Demultiplexing

Tool: **Dorado v1.3.1** [Github](https://github.com/nanoporetech/dorado)

Parameters and command

```
dorado demux \
    --output-dir "$DEMUX_DIR" \
    --kit-name "SQK-NBD114-24" \
    --sample-sheet "${DATA_DIR}/${SAMPLE_SHEET}" 
    "$CALLS_BAM"
```

### Results summary

The basecalled POD5 files contained a total of **238,589 reads**. These reads were demultiplexed into **nine barcodes** using the sequencing kit **SQK-NBD114-24**. Other parameters used are indicated in the commands above.

---

## Step 3 Quality control

Involved: 
- Adapter trimming
- Barcode removal
- Primer trimming

Tool: **Dorado v1.3.1** [Github](https://github.com/nanoporetech/dorado)

Parameters and commands used:

```
dorado trim \
        --sequencing-kit "SQK-NBD114-24" \
        --primer-sequences "primer_seq.fasta" \
        --emit-fastq \
        "${barcode}"/*.bam \
        > "${basedir}/${basename}/${basename}_trimmed.fastq"
```

### Step 4: Read Quality Assessment
Tool: Sequali version 1.0.2 [GitHub](https://github.com/rhpvorderman/sequali)

This step evaluated: 
- read length distributions
- Base quality scores
- overall sequencing performance and other important indicators.

Parameters and the command used:

```
sequali -t 12 --outdir "${barcode_folder}"/Quality_Reports  ${barcode_folder}/*.fastq

# -t 12 - Number of threads/cpus, important in parallelization of read processing.
```

In summary, read lengths ranged from 1 bp to over 215,000 bp. Quality scores varied across barcodes, spanning Phred scores of 3 to 45. Detailed per-barcode quality assessment reports are available via the links provided below.





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
