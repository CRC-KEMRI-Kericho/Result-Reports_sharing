## Parameter Assessment

The evaluation focused on three key parameters: minimum read quality (`MIN_QUAL = 9 and 10`), spacer mismatch tolerance (`SPACER_MAX_ERROR = 0`), and primer mismatch allowance (`MAX_ERROR = 0, 10–18`). A total of 20 parameter combinations were systematically tested to measure their impact on read retention, UMI recovery, and overall processing efficiency. The objective was to identify settings that maximize accurate UMI extraction while minimizing false-positive assignments and loss of biologically valid reads.

### Phred Score Quality of the filtered reads across Barcodes

| Barcode | Min Phred quality score | Selected quality score | Detailed quality assessment |
|--------|--------------------------|----------------------|-----------------------------|
| Barcode01 | <=3 | >=7 | [Barcode01 Complete Quality reports](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Report_quality_data/Barcode01_raw.html), [Average quality scores](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Quality_shots/Barcode01_AVQ.png), [Graph](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Quality_shots/Barcode01_AVQ_viz.png) |
| Barcode02 | <=2 | >=6 | [Barcode02 Complete Quality reports](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Report_quality_data/Barcode02_raw.html), [Average quality scores](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Quality_shots/Barcode02_AVQ.png), [Graph](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Quality_shots/Barcode02_AVQ_viz.png) |
| Barcode03 | <=2 | >=6 | [Barcode03 Complete Quality reports](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Report_quality_data/Barcode03_raw.html), [Average quality scores](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Quality_shots/Barcode03_AVQ.png), [Graph](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Quality_shots/Barcode03_AVQ_viz.png) |
| Barcode04 | <=4 | >=7 | [Barcode04 Complete Quality reports](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Report_quality_data/Barcode04_raw.html), [Average quality scores](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Quality_shots/Barcode04_AVQ.png), [Graph](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Quality_shots/Barcode04_AVQ_viz.png) |
| Barcode05 | <=3 | >=6 | [Barcode05 Complete Quality reports](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Report_quality_data/Barcode05_raw.html), [Average quality scores](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Quality_shots/Barcode05_AVQ.png), [Graph](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Quality_shots/Barcode05_AVQ_viz.png) |
| Barcode06 | <=4 | >=7 | [Barcode06 Complete Quality reports](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Report_quality_data/Barcode06_raw.html), [Average quality scores](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Quality_shots/Barcode06_AVQ.png), [Graph](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Quality_shots/Barcode06_AVQ_viz.png) |
| Barcode07 | <=4 | >=6 | [Barcode07 Complete Quality reports](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Report_quality_data/Barcode07_raw.html), [Average quality scores](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Quality_shots/Barcode07_AVQ.png), [Graph](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Quality_shots/Barcode07_AVQ_viz.png) |
| Barcode08 | <=4 | >=7 | [Barcode08 Complete Quality reports](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Report_quality_data/Barcode08_raw.html), [Average quality scores](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Quality_shots/Barcode08_AVQ.png), [Graph](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Quality_shots/Barcode08_AVQ_viz.png) |
| Barcode09 | <=3 | >=6 | [Barcode09 Complete Quality reports](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Report_quality_data/Barcode09_raw.html), [Average quality scores](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Quality_shots/Barcode09_AVQ.png), [Graph](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/Parameter_Asssessment/Quality_shots/Barcode09_AVQ_viz.png) |

### Min Phred score Quality 9

| Barcode | Raw Reads | Primer Max error=0 | Primer Max error=1 | Primer Max error=2 | Primer Max error=3 | Primer Max error=4 | Primer Max error=5 | Primer Max error=6 | Primer Max error=7 | Primer Max error=8 | Primer Max error=9 | Primer Max error=10 | Primer Max error=11 | Primer Max error=12 | Primer Max error=13 | Primer Max error=14 | Primer Max error=15 | Primer Max error=16 | Primer Max error=17 | Primer Max error=18 |
|--------|-----------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|
| Barcode01 | 216323 | 167527 | 170151 | 170471 | 170679 | 170828 | 170876 | NA | NA | NA | NA | 170924 | 170924 | 170924 | 170924 | 170924 | 170924 | 170924 | 170924 | 170924 |
| Barcode02 | 24081 | 18712 | 18883 | 18976 | 19012 | 19021 | 19024 | NA | NA | NA | NA | 19027 | 19027 | 19027 | 19027 | 19027 | 19027 | 19027 | 19027 | 19027 |
| Barcode03 | 125717 | 79683 | 81026 | 83287 | 83450 | 83515 | 83562 | NA | NA | NA | NA | 83597 | 83597 | 83597 | 83597 | 83597 | 83597 | 83597 | 83597 | 83597 |
| Barcode04 | 129951 | 103063 | 104701 | 104912 | 105035 | 105135 | 105162 | NA | NA | NA | NA | 105195 | 105195 | 105195 | 105195 | 105195 | 105195 | 105195 | 105195 | 105195 |
| Barcode05 | 173847 | 101755 | 107263 | 107650 | 107848 | 108036 | 108104 | NA | NA | NA | NA | 108125 | 108125 | 108125 | 108125 | 108125 | 108125 | 108125 | 108125 | 108125 |
| Barcode06 | 384197 | 313873 | 318515 | 319059 | 319434 | 319720 | 319807 | NA | NA | NA | NA | 319907 | 319907 | 319907 | 319907 | 319907 | 319907 | 319907 | 319907 | 319907 |
| Barcode07 | 76121 | 59443 | 60798 | 60899 | 60979 | 61006 | 61028 | NA | NA | NA | NA | 61036 | 61036 | 61036 | 61036 | 61036 | 61036 | 61036 | 61036 | 61036 |
| Barcode08 | 435014 | 356338 | 361510 | 362126 | 362510 | 362890 | 363015 | NA | NA | NA | NA | 363159 | 363159 | 363159 | 363159 | 363159 | 363159 | 363159 | 363159 | 363159 |
| Barcode09 | 59261 | 48060 | 48510 | 48601 | 48662 | 48674 | 48690 | NA | NA | NA | NA | 48699 | 48699 | 48699 | 48699 | 48699 | 48699 | 48699 | 48699 | 48699 |




| Barcode | PME=0 | PME=1 | PME=2 | PME=3 | PME=4 | PME=5 | PME=6 | PME=7 | PME=8 | PME=9 | PME=10 | PME=11 | PME=12 | PME=13 | PME=14 | PME=15 | PME=16 | PME=17 | PME=18 |
|--------|-------|-------|-------|-------|-------|-------|-------|-------|-------|-------|--------|--------|--------|--------|--------|--------|--------|--------|--------|
| Barcode01 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode02 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode03 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode04 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode05 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode06 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode07 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode08 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode09 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |

### Min Phred score Quality 10

| Barcode | PME=0 | PME=1 | PME=2 | PME=3 | PME=4 | PME=5 | PME=6 | PME=7 | PME=8 | PME=9 | PME=10 | PME=11 | PME=12 | PME=13 | PME=14 | PME=15 | PME=16 | PME=17 | PME=18 |
|--------|-------|-------|-------|-------|-------|-------|-------|-------|-------|-------|--------|--------|--------|--------|--------|--------|--------|--------|--------|
| Barcode01 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode02 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode03 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode04 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode05 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode06 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode07 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode08 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
| Barcode09 | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD | TBD |
