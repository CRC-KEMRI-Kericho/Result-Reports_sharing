# Porpid Pipeline Analysis

Latest update 3 weeks ago (technical update)

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
| `af_thresh` | `0.35` | Disabled (0.0)|
| **Contamination Filtering** | | |
| `cluster_thresh` | `0.015` | No change |
| `proportion_thresh` | `0.2` | No change |
| `dist_thresh` | `0.015` | No change |
| `contam_toggle` | `"on"` | "false" *Disabled* |
| **Post-processing** | | |
| `panel_thresh` | `50` | No change |
| **Archiving** | | |
| `degap` | `"true"` | No change |
| `collapse` | `"true"` | No change |
| `porpid_archive` | `"full"` | No change |

## Analysis Results

### UMI Extraction, Consensus Generation, and Alignment

#### VEGA5_bc2001

-   [UMI Extraction and
    Analysis](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/VEGA5_bc2001/VEGA5_bc2001-index.html)
-   [Post-processing
    Analysis](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/VEGA5_bc2001/AF_771-report.html)
-   [Whole Sample Consensus
    Alignment](https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/VEGA5_bc2001/AF_771.svg)
    
- [Distribution of read counts per UMI family](https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/VEGA5_bc2001/AF_771_final_umi_read_count_distribution.png)

  
#### VEGA5_bc2002

-   [UMI Extraction and
    Analysis](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/VEGA5_bc2002/VEGA5_bc2002-index.html)
-   [Post-processing
    Analysis](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/VEGA5_bc2002/AF_885-report.html)
-   [Whole Sample Consensus
    Alignment](https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/VEGA5_bc2002/AF_885.svg)

#### VEGA5_bc2004

-   [UMI Extraction and
    Analysis](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/VEGA5_bc2004/VEGA5_bc2004-index.html)
-   [Post-processing
    Analysis](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/VEGA5_bc2004/AF_529-report.html)
-   [Whole Sample Consensus
    Alignment](https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/VEGA5_bc2004/AF_529.svg)

#### VEGA5_bc2005

-   [UMI Extraction and
    Analysis](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/VEGA5_bc2005/VEGA5_bc2005-index.html)
-   [Post-processing
    Analysis](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/VEGA5_bc2005/AF_961-report.html)
-   [Whole Sample Consensus
    Alignment](https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/VEGA5_bc2005/AF_961.svg)

#### VEGA5_bc2008

-   [UMI Extraction and
    Analysis](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/VEGA5_bc2008/VEGA5_bc2008-index.html)
-   [Post-processing
    Analysis](https://htmlpreview.github.io/?https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/VEGA5_bc2008/AF_459-report.html)
-   [Whole Sample Consensus
    Alignment](https://raw.githubusercontent.com/CRC-KEMRI-Kericho/Result-Reports_sharing/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/VEGA5_bc2008/AF_459.svg)


## To Discuss:

- Main changes effected on the customized pipeline


