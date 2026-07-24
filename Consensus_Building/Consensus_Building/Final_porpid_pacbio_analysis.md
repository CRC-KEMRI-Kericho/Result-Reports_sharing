# Porpid Pipeline Analysis

## Data quality assessment

**[Summary quality assessment report](https://crc-kemri-kericho.github.io/Result-Reports_sharing/Consensus_Building/Consensus_Building/Results/pacbio/multiqc_report/multiqc_report.html)**
  
## PORPID Pipeline Parameters

| Parameter | Default | Modification |
|------------|---------|--------------|
| **Demultiplexing** | | |
| `chunk_size` | `100000` | `1000000` |
| `error_rate` | `0.01` | No change |
| `min_length` | `2100` | `4000` |
| `max_length` | `4300` | `6000` |
| `max_reads` | `100000` | `1000000000` *(effectively disables downsampling)* |
| `verbose` | `"false"` | No change |
| **PORPID** | | |
| `fs_thresh` | `1` | `5` |
| `lda_thresh` | `0.995` | Disabled (0.0) |
| **Consensus Generation** | | |
| `agreement_thresh` | `0.7` | No change |
|`min_agreement_rescue`|`0.5`|New introduced parameter to rescue consensus sequences rejected with single positions agreement < agreement_thresh but agreement > min_agreement_rescue |
| `af_thresh` | `0.35` | Disabled (0.0)|

## Analysis Results

### UMI Extraction, Consensus Generation, and Alignment

#### VEGA5_bc2001

- [UMI Extraction and Analysis](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/final_report_results/VEGA5_bc2001/VEGA5_bc2001-index.html)
- [Post-processing Analysis](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/final_report_results/VEGA5_bc2001/AF_771-report.html)
- [Whole Sample Consensus Alignment](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/final_report_results/VEGA5_bc2001/AF_771.html)
- [FASTA Sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/final_report_results/VEGA5_bc2001/AF_771-degapped.fasta)

#### VEGA5_bc2002

- [UMI Extraction and Analysis](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/final_report_results/VEGA5_bc2002/VEGA5_bc2002-index.html)
- [Post-processing Analysis](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/final_report_results/VEGA5_bc2002/AF_885-report.html)
- [Whole Sample Consensus Alignment](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/final_report_results/VEGA5_bc2002/AF_885.html)
- [FASTA Sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/final_report_results/VEGA5_bc2002/AF_885-degapped.fasta)

#### VEGA5_bc2004

- [UMI Extraction and Analysis](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/final_report_results/VEGA5_bc2004/VEGA5_bc2004-index.html)
- [Post-processing Analysis](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/final_report_results/VEGA5_bc2004/AF_529-report.html)
- [Whole Sample Consensus Alignment](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/final_report_results/VEGA5_bc2004/AF_529.html)
- [FASTA Sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/final_report_results/VEGA5_bc2004/AF_529-degapped.fasta)

#### VEGA5_bc2005

- [UMI Extraction and Analysis](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/final_report_results/VEGA5_bc2005/VEGA5_bc2005-index.html)
- [Post-processing Analysis](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/final_report_results/VEGA5_bc2005/AF_961-report.html)
- [Whole Sample Consensus Alignment](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/final_report_results/VEGA5_bc2005/AF_961.html)
- [FASTA Sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/final_report_results/VEGA5_bc2005/AF_961-degapped.fasta)

#### VEGA5_bc2008

- [UMI Extraction and Analysis](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/final_report_results/VEGA5_bc2008/VEGA5_bc2008-index.html)
- [Post-processing Analysis](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/final_report_results/VEGA5_bc2008/AF_459-report.html)
- [Whole Sample Consensus Alignment](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/final_report_results/VEGA5_bc2008/AF_459.html)
- [FASTA Sequences](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/final_report_results/VEGA5_bc2008/AF_459-degapped.fasta)

## umi Summary

| Sample | UMI Families |
|--------|-------------:|
| VEGA5_bc2001 | 328 |
| VEGA5_bc2002 | 636 |
| VEGA5_bc2004 | 334 |
| VEGA5_bc2005 | 225 |
| VEGA5_bc2008 | 401 |


