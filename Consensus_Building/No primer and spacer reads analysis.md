# Report on failed Reads  analysis

An analysis on the failed reads shows two categories of reads:

1. Reads that the primer had higher mismatches than the set threshold of 8 and the spacer has errors.

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


2. Reads that have no primer or primer like sequence or something that is close to a primer.

An overall summary of per barcode;

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

Detailed positions where the Dominant patterns in reads with no primer/spacer are found in reads with Primer, spacer, and umi were identified.

Barcode

