## Parameter Assessment

The evaluation focused on three key parameters: minimum read quality (`MIN_QUAL = 9 and 10`), spacer mismatch tolerance (`SPACER_MAX_ERROR = 0`), and primer mismatch allowance (`MAX_ERROR = 0, 10–18`). A total of 20 parameter combinations were systematically tested to measure their impact on read retention, UMI recovery, and overall processing efficiency. The objective was to identify settings that maximize accurate UMI extraction while minimizing false-positive assignments and loss of biologically valid reads.

### Phred Score Quality of the filtered reads across Barcodes

| Barcode | Min Phred quality score | Chosen quality score | Detailed quality assessment |
|--------|--------------------------|----------------------|-----------------------------|
| Barcode01 | 4 | 7 | [Quality reports](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Report_quality_data/Barcode01_raw.html),[Average quality scores](<img width="321" height="173" alt="Barcode01" src="https://github.com/user-attachments/assets/037f652d-46de-4ef6-914b-cfc2a21dc925" />
), [Graph](file:///C:/Users/Icipe/Downloads/per_sequence_quality_scores.svg) |
| Barcode02 | TBD | 7 | [Quality reports](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Report_quality_data/Barcode02_raw.html) |
| Barcode03 | TBD | 7 | [Quality reports](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Report_quality_data/Barcode03_raw.html) |
| Barcode04 | TBD | 7 | [Quality reports](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Report_quality_data/Barcode04_raw.html) |
| Barcode05 | TBD | 7 | [Quality reports](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Report_quality_data/Barcode05_raw.html) |
| Barcode06 | TBD | 7 | [Quality reports](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Report_quality_data/Barcode06_raw.html) |
| Barcode07 | TBD | 7 | [Quality reports](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Report_quality_data/Barcode07_raw.html) |
| Barcode08 | TBD | 7 | [Quality reports](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Report_quality_data/Barcode08_raw.html) |
| Barcode09 | TBD | 7 | [Quality reports](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Report_quality_data/Barcode09_raw.html) |

### Min Phred score Quality 9

| Barcode | Primer Max error=0 | Primer Max error=10 | Primer Max error=11 | Primer Max error=12 | Primer Max error=13 | Primer Max error=14 | Primer Max error=15 | Primer Max error=16 | Primer Max error=17 | Primer Max error=18 |
|--------|--------------------|---------------------|---------------------|---------------------|---------------------|---------------------|---------------------|---------------------|---------------------|---------------------|
| Barcode01 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode02 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode03 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode04 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode05 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode06 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode07 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode08 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode09 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |

### Min Phred score Quality 10

| Barcode | Primer Max error=0 | Primer Max error=10 | Primer Max error=11 | Primer Max error=12 | Primer Max error=13 | Primer Max error=14 | Primer Max error=15 | Primer Max error=16 | Primer Max error=17 | Primer Max error=18 |
|--------|--------------------|---------------------|---------------------|---------------------|---------------------|---------------------|---------------------|---------------------|---------------------|---------------------|
| Barcode01 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode02 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode03 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode04 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode05 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode06 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode07 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode08 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode09 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
