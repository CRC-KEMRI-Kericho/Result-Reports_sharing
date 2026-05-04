Detailed Parameter analysis assessment

The analysis involved a distributed parameter sweep to evaluate the impact of read quality filtering and UMI detection stringency on UMI family recovery across all the barcodes. 

For each parameter combination, defined by minimum Phred quality score (MQ15–MQ23) and maximum allowed UMI detection error (MAXERR0–MAXERR18), reads were processed through three sequential steps:

(1) read pre-processing 

(2) primer–spacer–UMI detection, and

(3) UMI correction using a strand-aware clustering approach.

The sweep explored a total of:

- 9 Phred quality thresholds (15–23)
- 19 UMI detection error levels (0–18)
- 1 spacer mismatch setting (SP=0)

resulting in 171 parameter combinations per barcode, executed in a distributed manner.

High level summarries extracted from the runs showing 
