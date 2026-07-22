# Minimum Agreement Rejected Families Analysis

## Overall Summary

> **Note:** The results we discussed yesterday were generated using a **mean Phred score threshold which was (35.6)**. During our discussion, I stated that the analysis had been performed using the PORPID default Phred score threshold of **20**, which was incorrect. I have corrected this, and the results below reflect the analysis performed using the **default Phred score threshold (20)**. The primary difference is an increase in the number of umi families generated (both rejected and final umi families increase).

| Sample | Total Families | Min-Agreement Rejected Families | Single-Position Rejects (*min_agreement* < 0.7) | Multiple position_rejects (*min_agreement* < 0.7) | Rejects Distribution Graph | Final Consensus Sequences |
|:------:|:--------------:|:-------------------------------------:|:-----------------------------------------------:|:--------------------------:|:-----------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------:|
| **VEGA5_bc2001** | 470 | 61 | 27 | 34| [View Distribution Graph](https://github.com/user-attachments/assets/58bce775-9aeb-4dc2-8ddd-6ed33a3ef5dc) | 409 |
| **VEGA5_bc2002** | 839 | 91 | 41 |  50|[View Distribution Graph](https://github.com/user-attachments/assets/86e3be82-4f48-4c18-80aa-e391a4f5dd96) | 748 |
| **VEGA5_bc2004** | 449 | 39 | 26 | 13|[View Distribution Graph](https://github.com/user-attachments/assets/6018fa96-fe81-47f7-bc27-59d6a0c45d9f) | 410 |
| **VEGA5_bc2005** | 287 | 19 | 14 | 5|[View Distribution Graph](https://github.com/user-attachments/assets/fa6b0e33-92a7-4d9f-935c-c319784e3960) | 268 |
| **VEGA5_bc2008** | 481 | 29 | 22 | 7|[View Distribution Graph](https://github.com/user-attachments/assets/53ed87f6-0f57-418f-bfa3-dc472a3c4ed1) | 452 |

### Single-Position Base Ratios

***Note***: The hyphens (-) show position which had gaps.

- **[VEGA5_bc2001](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/AF_771.single_position_rejects.csv)**
- **[VEGA5_bc2002](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/AF_885.single_position_rejects.csv)**
- **[VEGA5_bc2004](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/AF_529.single_position_rejects.csv)**
- **[VEGA5_bc2005](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/AF_961.single_position_rejects.csv)**
- **[VEGA5_bc2008](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/blob/main/Consensus_Building/Consensus_Building/Results/pacbio/postproc/AF_459.single_position_rejects.csv)**



### Alignment of the Whole-Sample Consensus Sequences

-  **[VEGA5_bc2001 Consensus Sequences](https://crc-kemri-kericho.github.io/Result-Reports_sharing/Consensus_Building/Consensus_Building/Results/pacbio/postproc/AF_771.html)**
-  **[VEGA5_bc2002 Consensus Sequences](https://crc-kemri-kericho.github.io/Result-Reports_sharing/Consensus_Building/Consensus_Building/Results/pacbio/postproc/AF_885.html)**
-  **[VEGA5_bc2004 Consensus Sequences](https://crc-kemri-kericho.github.io/Result-Reports_sharing/Consensus_Building/Consensus_Building/Results/pacbio/postproc/AF_529.html)**
-  **[VEGA5_bc2005 Consensus Sequences](https://crc-kemri-kericho.github.io/Result-Reports_sharing/Consensus_Building/Consensus_Building/Results/pacbio/postproc/AF_961.html)**
-  **[VEGA5_bc2008 Consensus Sequences](https://crc-kemri-kericho.github.io/Result-Reports_sharing/Consensus_Building/Consensus_Building/Results/pacbio/postproc/AF_459.html)**

## Summary

- All results shown above were generated using the **PORPID default Phred score threshold of 20**.
- The **Rejects Distribution Graph** links provide the distribution of nucleotide positions with **min_agreement < 0.7** among rejected UMI families for each sample.
