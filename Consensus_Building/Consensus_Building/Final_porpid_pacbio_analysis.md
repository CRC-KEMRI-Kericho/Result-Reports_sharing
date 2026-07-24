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

