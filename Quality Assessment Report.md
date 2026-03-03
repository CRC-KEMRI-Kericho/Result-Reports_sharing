# Quality Reports Analysis

## Step 1: Basecalling 
Tool: **Dorado v1.3.1** [GitHub](https://github.com/nanoporetech/dorado)

Parameters and commands used.
```
dorado basecaller sup -r $DATA_DIR/${pod5_file} \
    --no-trim \
    --device $DEVICE \
    > "$CALLS_BAM"
```

## Step 2: Demultiplexing

Tool: **Dorado v1.3.1** [GitHub](https://github.com/nanoporetech/dorado)

Parameters and command

```
dorado demux \
    --output-dir "$DEMUX_DIR" \
    --kit-name "SQK-NBD114-24" \
    --sample-sheet "${DATA_DIR}/${SAMPLE_SHEET}" 
    "$CALLS_BAM"
```

### Results summary

The basecalled POD5 files contained a total of **238,589 reads**. These reads were demultiplexed into **nine barcodes** using the sequencing kit **SQK-NBD114-24**. Additional parameters are detailed in the commands above.

---

## Step 3: Quality control

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

In summary, read lengths ranged from 1 bp to over 215,000 bp. Quality scores varied across barcodes, spanning Phred scores of 3 to 45. Detailed, per-barcode quality assessment reports are available via the links provided below, before any further filtering.

- [Barcode01](https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode01.fastq.html)
- [Barcode02](https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode02.fastq.html)
- [Barcode03](https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode03.fastq.html)
- [Barcode04](https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode04.fastq.html)
- [Barcode05](https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode05.fastq.html)
- [Barcode06](https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode06.fastq.html)
- [Barcode07](https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode07.fastq.html)
- [Barcode08](https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode08.fastq.html)
- [Barcode09](https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode09.fastq.html)



#### Subsequent Filtering Based on Quality Reports

## Length and Quality Filtering Criteria

Tool: Filtlong version 0.3.1 [GitHub](https://github.com/rrwick/Filtlong)

Given the expected final amplicon size of **5300 bp** (based on the library preparation information summarised below), reads shorter than **4000 bp** and longer than **5600 bp** were excluded from downstream analysis.

### DNA Nano2 Library Information 042325 MEL EC

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

Additionally, Phred score–based quality filtering was applied using barcode-specific cut-offs as shown below:

| Barcode    | Phred Score Quality Cut-off |
|------------|-----------------------------|
| Barcode01  | 7 |
| Barcode02  | 3 |
| Barcode03  | 7 |
| Barcode04  | 7 |
| Barcode05  | 6 |
| Barcode06  | 7 |
| Barcode07  | 7 |
| Barcode08  | 7 |
| Barcode09  | 7 |

The command was run as follows (Example for barcode 01):

**Note:** The phred score quality is modified depending on the barcode, while min_length and max_length are constant for all barcodes (Refer to library preparation information in the table above).

```
filtlong  barcode_01/*.fastq \
          --min_length 4000 \
          --max_length 5600 \
          --min_mean_q 7 > "${barcode_folder}/${barcode_name}_filtered.fastq"
```

The filtered reads quality is re-assessed below

### Quality Re-assessment

Tool: Sequali version 1.0.2 [GitHub](https://github.com/rhpvorderman/sequali)

This step Re-evaluated: 
- read length distributions
- Base quality scores
- overall sequencing performance and other important indicators.

Parameters and the command used:

```
sequali -t 12 --outdir "${barcode_folder}"/Quality_Reports  ${barcode_folder}/*.fastq

# -t 12 - Number of threads/cpus, important in parallelization of read processing.
```

In summary, read lengths ranged from **4000** bp to **5600** bp. Quality scores varied across barcodes.

Detailed, per-barcode quality assessment reports are available via the links provided below, after further filtering.

- [Barcode01](https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode01_filtered.fastq.html)
- [Barcode02](https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode02_filtered.fastq.html)
- [Barcode03](https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode03_filtered.fastq.html)
- [Barcode04](https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode04_filtered.fastq.html)
- [Barcode05](https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode05_filtered.fastq.html)
- [Barcode06](https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode06_filtered.fastq.html)
- [Barcode07](https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode07_filtered.fastq.html)
- [Barcode08](https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode08_filtered.fastq.html)
- [Barcode09](https://crc-kemri-kericho.github.io/Result-Reports_sharing/Quality_Reports/barcode09_filtered.fastq.html)

---
## Step 5 Mapping reads to the reference  

Read alignment was performed using minimap2 with the **map-ont** preset against the HXB2 reference genome. The resulting alignments were sorted and indexed using samtools. An example command for Barcode01 is shown below.

Tool used : Minimap2-2.30 (r1287) [GitHub](https://github.com/lh3/minimap2)

**Samtools version 1.23** was used to sort and index the BAM file.

```
minimap2 -ax map-ont HXB2-Reference.fasta ${basedir}/barcode01/barcode01_filtered.fastq | \
samtools sort -@ $THREADS -o ${basedir}/barcode01/barcode01_filtered.bam


samtools index ${basedir}/barcode01/barcode01_filtered.bam
```
### Mapping results Visualization

Tool: IGV Version 2.19.7 [Website](https://igv.org/doc/desktop/##usage-license-and-source-code)

The generated visualization for the maps can be accessed below:

- [Barcode01](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/igv_files/Barcode01_map.png)
- [Barcode02](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/igv_files/Barcode02_map.png)
- [Barcode03](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/igv_files/Barcode03_map.png)
- [Barcode04](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/igv_files/Barcode04_map.png)
- [Barcode05](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/igv_files/Barcode05_map.png)
- [Barcode06](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/igv_files/Barcode06_map.png)
- [Barcode07](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/igv_files/Barcode07_map.png)
- [Barcode08](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/igv_files/Barcode08_map.png)
- [Barcode09](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/igv_files/Barcode09_map.png)

  **Note** The accompanying Data files have been uploaded in the shared drive  [processed reads](https://hjf.box.com/s/8lspjn8rwbkklrq8xrx9ki4ob44hnkix)
  
### whats' contained in the directory above:

- **Reads** – Demultiplexed and trimmed FASTQ files used for quality control and downstream analyses.

- **Quality_Reports** – Per-barcode Sequali quality assessment reports (before and after filtering).

- **mapped_bam_files** – Sorted and indexed BAM files generated after alignment to the HXB2 reference genome.

- **mapped_reads_igv_visualizations** – IGV-generated visualization files illustrating read mapping coverage and alignment patterns.

<h2 align="center">End of Report</h2>






















