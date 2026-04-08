# Report on Failed Reads Analysis

An analysis of the failed reads reveals two primary categories:

## 1. Reads with high primer mismatches and spacer errors

These reads contain primer-like sequences; however, the number of mismatches exceeds the defined threshold (≥ 8 mismatches), and the spacer sequence is either incorrect or degraded.

| barcode   | primer only reads | Detailed csv |
|-----------|------------------|--------------|
| Barcode01 | 270              | [Per Read csv](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/No_Primer_spcer_umi_reads_analysis/barcode01.primer_only_reads.csv) |
| Barcode02 | 98               | [Per Read csv](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/No_Primer_spcer_umi_reads_analysis/barcode02.primer_only_reads.csv) |
| Barcode03 | 289              | [Per Read csv](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/No_Primer_spcer_umi_reads_analysis/barcode03.primer_only_reads.csv) |
| Barcode04 | 244              | [Per Read csv](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/No_Primer_spcer_umi_reads_analysis/barcode04.primer_only_reads.csv) |
| Barcode05 | 279              | [Per Read csv](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/No_Primer_spcer_umi_reads_analysis/barcode05.primer_only_reads.csv) |
| Barcode06 | 501              | [Per Read csv](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/No_Primer_spcer_umi_reads_analysis/barcode06.primer_only_reads.csv) |
| Barcode07 | 111              | [Per Read csv](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/No_Primer_spcer_umi_reads_analysis/barcode07.primer_only_reads.csv) |
| Barcode08 | 735              | [Per Read csv](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/No_Primer_spcer_umi_reads_analysis/barcode08.primer_only_reads.csv) |
| Barcode09 | 110              | [Per Read csv](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/No_Primer_spcer_umi_reads_analysis/barcode09.primer_only_reads.csv) |

---

## 2. Reads lacking detectable primer or primer-like sequences

These reads do not contain any detectable primer sequence or sufficiently similar sequence to pass the detection threshold.

### Summary per barcode

| barcode   | Dominant 5' end pattern            | Dominant 5' end pattern length (bp) | Dominant 3' end pattern             | Dominant 3' end pattern length (bp) | Reads_without_primer_spacer_with_dominant_pattern | Reads_with_Primer_Spacer_UMI_detected | Reads_with_Primer_Spacer_UMI_with_dominant_pattern_match |
|-----------|------------------------------------|-------------------------------------|-------------------------------------|-------------------------------------|---------------------------------------------------|---------------------------------------|----------------------------------------------------------|
| barcode01 | TGACTAGCGGAGGCTAGAAGGAGAGA         | 26                                  | CTTGTAGCAAGTGTTACTGTAAAAAA          | 26                                  | 9800                                              | 11137                                 | 10567                                                    |
| barcode02 | TAAAGTTAGCAGGAAGATGGCCAGTAAAA      | 29                                  | GTCTCTCTTGGTAGACCAGGTCGAGCCCG       | 29                                  | 691                                               | 1977                                  | 1320                                                     |
| barcode03 | TAAAGCTAGCAGGAAGATGGCCAGTA         | 26                                  | ATAGTGAGTCATCAGGACGGAGCGGA          | 26                                  | 2337                                              | 6320                                  | 1602                                                     |
| barcode04 | TGACTAGCGGAGGCTAGAAGGAGAGA         | 26                                  | TTGTAGCAAGTGTTACTGTAAAAAAT          | 26                                  | 6492                                              | 7657                                  | 7261                                                     |
| barcode05 | TAAAGCTAGCAGGAAGATGGCCAGTA         | 26                                  | ATAGTGAGTCATCAGGACGGAGCGGA          | 26                                  | 3425                                              | 7361                                  | 1801                                                     |
| barcode06 | TGACTAGCGGAGGCTAGAAGGAGAGA         | 26                                  | TTGTAGCAAATGTTATTGTAAAAAAT          | 26                                  | 14687                                             | 21337                                 | 20199                                                    |
| barcode07 | TAAAGCTAGCAGGAAGATGGCCAGTA         | 26                                  | TCTCTCTTGGTAGACCAGGTCGAGCCCG        | 28                                  | 1606                                              | 5232                                  | 2428                                                     |
| barcode08 | TGACTAGCGGAGGCTAGAAGGAGAGA         | 26                                  | CTCTCCTTCTAGCCTCCGCTAGTCAA          | 26                                  | 12073                                             | 25450                                 | 16652                                                    |
| barcode09 | TAAAGTTAGCAGGAAGATGGCCAGTAAA       | 28                                  | GGTCTCTCTTGTAGACCAGGTTGAGCCCG       | 29                                  | 1899                                              | 5608                                  | 3644                                                     |

---

### Descriptions

- **Dominant 5' end pattern** → Most abundant sequence motif identified at the 5′ end of reads lacking primer/spacer/UMI.

- **Dominant 5' end pattern length (bp)** → Length (in base pairs) of the dominant 5′ end pattern.

- **Dominant 3' end pattern** → Most abundant sequence motif identified at the 3′ end of reads lacking primer/spacer/UMI.

- **Dominant 3' end pattern length (bp)** → Length (in base pairs) of the dominant 3′ end pattern.

- **Reads_without_primer_spacer_with_dominant_pattern** → Number of reads lacking primer/spacer/UMI that still contain either dominant 5′ or 3′ end pattern.

- **Reads_with_Primer_Spacer_UMI_detected** → Total number of reads in which primer, spacer, and UMI were successfully identified.

- **Reads_with_Primer_Spacer_UMI_with_dominant_pattern_match** → Number of UMI-positive reads that also contain at least one of the dominant end patterns.

---

#### Detailed positions of dominant patterns within UMI-positive reads

This section maps the positions of dominant end patterns (derived from no-primer/spacer reads) within reads where primer, spacer, and UMI were successfully detected.

- **pattern_side** → Indicates whether the dominant motif originates from the 5′ or 3′ end.

- **source_pattern** → Dominant pattern identified from no-primer/spacer reads.

- **pattern_length** → Length of the dominant pattern.

- **pattern_reads_no_umi** → Number of no-primer/spacer reads supporting this pattern.

- **matched_pattern** → Sequence observed in the read (forward or reverse complement).

- **orientation** → Alignment orientation relative to the source pattern.

- **read_id** → Identifier of the read containing the match.

- **match_start / match_end** → 1-based coordinates of the pattern within the read.

- **read_length** → Total read length.

- **strand** → Orientation based on UMI detection.

- **primer_spacer_umi_start / primer_spacer_umi_end** → Coordinates of the primer + spacer + UMI region.

---

| Barcode   | Detailed csv |
|-----------|--------------|
| Barcode01 | [Per Read positions csv](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/No_Primer_spcer_umi_reads_analysis/barcode01.top_no_umi_patterns_in_umi_reads.csv) |
| Barcode02 | [Per Read positions csv](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/No_Primer_spcer_umi_reads_analysis/barcode02.top_no_umi_patterns_in_umi_reads.csv) |
| Barcode03 | [Per Read positions csv](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/No_Primer_spcer_umi_reads_analysis/barcode03.top_no_umi_patterns_in_umi_reads.csv) |
| Barcode04 | [Per Read positions csv](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/No_Primer_spcer_umi_reads_analysis/barcode04.top_no_umi_patterns_in_umi_reads.csv) |
| Barcode05 | [Per Read positions csv](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/No_Primer_spcer_umi_reads_analysis/barcode05.top_no_umi_patterns_in_umi_reads.csv) |
| Barcode06 | [Per Read positions csv](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/No_Primer_spcer_umi_reads_analysis/barcode06.top_no_umi_patterns_in_umi_reads.csv) |
| Barcode07 | [Per Read positions csv](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/No_Primer_spcer_umi_reads_analysis/barcode07.top_no_umi_patterns_in_umi_reads.csv) |
| Barcode08 | [Per Read positions csv](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/No_Primer_spcer_umi_reads_analysis/barcode08.top_no_umi_patterns_in_umi_reads.csv) |
| Barcode09 | [Per Read positions csv](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/No_Primer_spcer_umi_reads_analysis/barcode09.top_no_umi_patterns_in_umi_reads.csv) |

---

**END OF REPORT**
