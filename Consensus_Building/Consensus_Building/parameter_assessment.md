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

MAXERR0 counts rows from `BarcodeXX.umi_per_read.csv`; MAXERR1-18 count rows from `BarcodeXX_combined_primer_spacer_umi.csv`.

| Barcode | Raw Reads | Primer Max error=0 | Primer Max error=1 | Primer Max error=2 | Primer Max error=3 | Primer Max error=4 | Primer Max error=5 | Primer Max error=6 | Primer Max error=7 | Primer Max error=8 | Primer Max error=9 | Primer Max error=10 | Primer Max error=11 | Primer Max error=12 | Primer Max error=13 | Primer Max error=14 | Primer Max error=15 | Primer Max error=16 | Primer Max error=17 | Primer Max error=18 |
|--------|-----------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|
| Barcode01 | 216323 | 167527(77.4%) | 170812(79.0%) | 170888(79.0%) | 170781(78.9%) | 170909(79.0%) | 170951(79.0%) | 170980(79.0%) | 170991(79.0%) | 170987(79.0%) | 170987(79.0%) | 170987(79.0%) | 170987(79.0%) | 170987(79.0%) | 170987(79.0%) | 170987(79.0%) | 170987(79.0%) | 170987(79.0%) | 170987(79.0%) | 170987(79.0%) |
| Barcode02 | 24081 | 18712(77.7%) | 18888(78.4%) | 18978(78.8%) | 19012(79.0%) | 19021(79.0%) | 19024(79.0%) | 19027(79.0%) | 19027(79.0%) | 19027(79.0%) | 19027(79.0%) | 19027(79.0%) | 19027(79.0%) | 19027(79.0%) | 19027(79.0%) | 19027(79.0%) | 19027(79.0%) | 19027(79.0%) | 19027(79.0%) | 19027(79.0%) |
| Barcode03 | 125717 | 79683(63.4%) | 81061(64.5%) | 83311(66.3%) | 83468(66.4%) | 83531(66.4%) | 83577(66.5%) | 83609(66.5%) | 83612(66.5%) | 83612(66.5%) | 83612(66.5%) | 83612(66.5%) | 83612(66.5%) | 83612(66.5%) | 83612(66.5%) | 83612(66.5%) | 83612(66.5%) | 83612(66.5%) | 83612(66.5%) | 83612(66.5%) |
| Barcode04 | 129951 | 103063(79.3%) | 105121(80.9%) | 105198(81.0%) | 105303(81.0%) | 105199(81.0%) | 105214(81.0%) | 105233(81.0%) | 105242(81.0%) | 105237(81.0%) | 105237(81.0%) | 105237(81.0%) | 105237(81.0%) | 105237(81.0%) | 105237(81.0%) | 105237(81.0%) | 105237(81.0%) | 105237(81.0%) | 105237(81.0%) | 105237(81.0%) |
| Barcode05 | 173847 | 101755(58.5%) | 107414(61.8%) | 107742(62.0%) | 107928(62.1%) | 108101(62.2%) | 108168(62.2%) | 108187(62.2%) | 108188(62.2%) | 108188(62.2%) | 108188(62.2%) | 108188(62.2%) | 108188(62.2%) | 108188(62.2%) | 108188(62.2%) | 108188(62.2%) | 108188(62.2%) | 108188(62.2%) | 108188(62.2%) | 108188(62.2%) |
| Barcode06 | 384197 | 313873(81.7%) | 319055(83.0%) | 319472(83.2%) | 319811(83.2%) | 320008(83.3%) | 320085(83.3%) | 320140(83.3%) | 320138(83.3%) | 320105(83.3%) | 320105(83.3%) | 320105(83.3%) | 320105(83.3%) | 320105(83.3%) | 320105(83.3%) | 320105(83.3%) | 320105(83.3%) | 320105(83.3%) | 320105(83.3%) | 320105(83.3%) |
| Barcode07 | 76121 | 59443(78.1%) | 60830(79.9%) | 60923(80.0%) | 61001(80.1%) | 61015(80.2%) | 61036(80.2%) | 61043(80.2%) | 61043(80.2%) | 61043(80.2%) | 61043(80.2%) | 61043(80.2%) | 61043(80.2%) | 61043(80.2%) | 61043(80.2%) | 61043(80.2%) | 61043(80.2%) | 61043(80.2%) | 61043(80.2%) | 61043(80.2%) |
| Barcode08 | 435014 | 356338(81.9%) | 362483(83.3%) | 362548(83.3%) | 362895(83.4%) | 363164(83.5%) | 363262(83.5%) | 363331(83.5%) | 363361(83.5%) | 363358(83.5%) | 363358(83.5%) | 363358(83.5%) | 363358(83.5%) | 363358(83.5%) | 363358(83.5%) | 363358(83.5%) | 363358(83.5%) | 363358(83.5%) | 363358(83.5%) | 363358(83.5%) |
| Barcode09 | 59261 | 48060(81.1%) | 48538(81.9%) | 48615(82.0%) | 48673(82.1%) | 48685(82.2%) | 48701(82.2%) | 48707(82.2%) | 48708(82.2%) | 48708(82.2%) | 48708(82.2%) | 48708(82.2%) | 48708(82.2%) | 48708(82.2%) | 48708(82.2%) | 48708(82.2%) | 48708(82.2%) | 48708(82.2%) | 48708(82.2%) | 48708(82.2%) |


### Min Phred score Quality 10

MAXERR0 counts rows from `BarcodeXX.umi_per_read.csv`; MAXERR1-18 count rows from `BarcodeXX_combined_primer_spacer_umi.csv`.

| Barcode | Raw Reads | Primer Max error=0 | Primer Max error=1 | Primer Max error=2 | Primer Max error=3 | Primer Max error=4 | Primer Max error=5 | Primer Max error=6 | Primer Max error=7 | Primer Max error=8 | Primer Max error=9 | Primer Max error=10 | Primer Max error=11 | Primer Max error=12 | Primer Max error=13 | Primer Max error=14 | Primer Max error=15 | Primer Max error=16 | Primer Max error=17 | Primer Max error=18 |
|--------|-----------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|
| Barcode01 | 214180 | 166587(77.8%) | 169784(79.3%) | 169862(79.3%) | 169758(79.3%) | 169863(79.3%) | 169902(79.3%) | 169926(79.3%) | 169937(79.3%) | 169933(79.3%) | 169933(79.3%) | 169933(79.3%) | 169933(79.3%) | 169933(79.3%) | 169933(79.3%) | 169933(79.3%) | 169933(79.3%) | 169933(79.3%) | 169933(79.3%) | 169933(79.3%) |
| Barcode02 | 23747 | 18525(78.0%) | 18696(78.7%) | 18784(79.1%) | 18817(79.2%) | 18826(79.3%) | 18829(79.3%) | 18832(79.3%) | 18832(79.3%) | 18832(79.3%) | 18832(79.3%) | 18832(79.3%) | 18832(79.3%) | 18832(79.3%) | 18832(79.3%) | 18832(79.3%) | 18832(79.3%) | 18832(79.3%) | 18832(79.3%) | 18832(79.3%) |
| Barcode03 | 123502 | 78578(63.6%) | 79882(64.7%) | 82098(66.5%) | 82248(66.6%) | 82310(66.6%) | 82354(66.7%) | 82384(66.7%) | 82387(66.7%) | 82387(66.7%) | 82387(66.7%) | 82387(66.7%) | 82387(66.7%) | 82387(66.7%) | 82387(66.7%) | 82387(66.7%) | 82387(66.7%) | 82387(66.7%) | 82387(66.7%) | 82387(66.7%) |
| Barcode04 | 128711 | 102513(79.6%) | 104512(81.2%) | 104593(81.3%) | 104695(81.3%) | 104597(81.3%) | 104611(81.3%) | 104629(81.3%) | 104638(81.3%) | 104633(81.3%) | 104633(81.3%) | 104633(81.3%) | 104633(81.3%) | 104633(81.3%) | 104633(81.3%) | 104633(81.3%) | 104633(81.3%) | 104633(81.3%) | 104633(81.3%) | 104633(81.3%) |
| Barcode05 | 170619 | 100192(58.7%) | 105705(62.0%) | 106031(62.1%) | 106209(62.2%) | 106371(62.3%) | 106433(62.4%) | 106451(62.4%) | 106452(62.4%) | 106452(62.4%) | 106452(62.4%) | 106452(62.4%) | 106452(62.4%) | 106452(62.4%) | 106452(62.4%) | 106452(62.4%) | 106452(62.4%) | 106452(62.4%) | 106452(62.4%) | 106452(62.4%) |
| Barcode06 | 380791 | 312312(82.0%) | 317382(83.3%) | 317791(83.5%) | 318111(83.5%) | 318290(83.6%) | 318365(83.6%) | 318415(83.6%) | 318412(83.6%) | 318380(83.6%) | 318380(83.6%) | 318380(83.6%) | 318380(83.6%) | 318380(83.6%) | 318380(83.6%) | 318380(83.6%) | 318380(83.6%) | 318380(83.6%) | 318380(83.6%) | 318380(83.6%) |
| Barcode07 | 75226 | 58996(78.4%) | 60356(80.2%) | 60447(80.4%) | 60519(80.4%) | 60533(80.5%) | 60552(80.5%) | 60557(80.5%) | 60557(80.5%) | 60557(80.5%) | 60557(80.5%) | 60557(80.5%) | 60557(80.5%) | 60557(80.5%) | 60557(80.5%) | 60557(80.5%) | 60557(80.5%) | 60557(80.5%) | 60557(80.5%) | 60557(80.5%) |
| Barcode08 | 430918 | 354351(82.2%) | 360333(83.6%) | 360405(83.6%) | 360731(83.7%) | 360993(83.8%) | 361085(83.8%) | 361156(83.8%) | 361185(83.8%) | 361182(83.8%) | 361182(83.8%) | 361182(83.8%) | 361182(83.8%) | 361182(83.8%) | 361182(83.8%) | 361182(83.8%) | 361182(83.8%) | 361182(83.8%) | 361182(83.8%) | 361182(83.8%) |
| Barcode09 | 58666 | 47766(81.4%) | 48233(82.2%) | 48307(82.3%) | 48363(82.4%) | 48373(82.5%) | 48388(82.5%) | 48394(82.5%) | 48395(82.5%) | 48395(82.5%) | 48395(82.5%) | 48395(82.5%) | 48395(82.5%) | 48395(82.5%) | 48395(82.5%) | 48395(82.5%) | 48395(82.5%) | 48395(82.5%) | 48395(82.5%) | 48395(82.5%) |














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




