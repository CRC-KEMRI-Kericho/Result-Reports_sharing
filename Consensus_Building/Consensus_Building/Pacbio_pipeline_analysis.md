# PacBio Consensus Phred score Distribution

## Phred score distribution per sequence at different stages of analysis

## 1. Per-sequence quality score before length and quality filtering

PacBio read accuracy (rq) distribution across samples. rq is the PacBio-predicted accuracy of an entire read, expressed as a probability from 0 to 1, 
where values closer to 1 indicate higher predicted read accuracy. The violin width represents the density of reads at each predicted accuracy value.

<img width="800" height="884" alt="all_samples_bam_rq_violin" src="https://github.com/user-attachments/assets/e63d6061-7a1a-4d65-ade0-9f197840aa0c" />

## 2. Quality Distribution after Length, Primer, and Adapter filtering

<img width="800" height="884" alt="all_samples_length_filtered_arithmetic_mean_qv_violin" src="https://github.com/user-attachments/assets/ae927e6d-7013-46d3-ab2d-bc13865a4b03" />

## 3. Quality Distribution for reads that contribute to the final family consensus

<img width="800" height="884" alt="all_samples_family_quality_filtered_read_qv_violin" src="https://github.com/user-attachments/assets/f4d2ab24-cecd-4844-bcdd-d10523346f1f" />

### Additional plot:

<img width="1600" height="800" alt="sequali_per_position_quality_plot" src="https://github.com/user-attachments/assets/25a5a21c-d95b-44e8-beec-737254656bdd" />

