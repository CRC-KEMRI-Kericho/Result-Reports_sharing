# Reads Statistical analyses

## Phred score quality frequency distribution table

| Q Score | Frequency (Reads) | Weighted contribution (Q × Reads) |
|---|---:|---:|
| 1 | 13 | 13 |
| 2 | 603 | 1,206 |
| 3 | 2,388 | 7,164 |
| 4 | 3,377 | 13,508 |
| 5 | 5,358 | 26,790 |
| 6 | 13,948 | 83,688 |
| 7 | 30,539 | 213,773 |
| 8 | 37,242 | 297,936 |
| 9 | 36,022 | 324,198 |
| 10 | 47,076 | 470,760 |
| 11 | 66,183 | 728,013 |
| 12 | 80,726 | 968,712 |
| 13 | 88,077 | 1,145,001 |
| 14 | 91,054 | 1,274,756 |
| 15 | 100,083 | 1,501,245 |
| 16 | 120,521 | 1,928,336 |
| 17 | 147,870 | 2,513,790 |
| 18 | 186,671 | 3,360,078 |
| 19 | 233,211 | 4,431,009 |
| 20 | 262,386 | 5,247,720 |
| 21 | 232,592 | 4,884,432 |
| 22 | 144,494 | 3,178,868 |
| 23 | 65,079 | 1,496,817 |
| 24 | 423,608 | 10,166,592 |
| 25 | 7,248 | 181,200 |
| 26 | 1,865 | 48,490 |
| 27 | 472 | 12,744 |
| 28 | 98 | 2,744 |
| 29 | 40 | 1,160 |
| 30 | 16 | 480 |
| 31 | 4 | 124 |
| 32 | 7 | 224 |
| 33 | 1 | 33 |
| 34 | 1 | 34 |
| 35 | 2 | 70 |

---

# Descriptive statistical analyses

## Minimum Phred quality score

The minimum Phred quality score corresponds to the lowest observed Q score with at least one read.

**Minimum Q score = Q1**

---

## Maximum Phred quality score

The maximum Phred quality score corresponds to the highest observed Q score with at least one read.

**Maximum Q score = Q35**

---

## Mode Phred quality score

The mode corresponds to the most frequently occurring Phred quality score in the dataset.

**Mode Q score**

**Q24 = 423,608 reads**

---

## Weighted mean Phred quality score

Because the data represent a frequency distribution, the mean quality score was calculated using a weighted mean rather than a simple arithmetic mean.

That is: 

<img width="282" height="78" alt="image" src="https://github.com/user-attachments/assets/7fe9e2e0-adb5-4995-b695-e47289e270f0" />

simplified as below:


<img width="430" height="58" alt="image" src="https://github.com/user-attachments/assets/3fc148c8-ff77-421d-be3a-3d43c64fb27c" />



**Weighted Mean Q score = Sum(Q score × Number of reads) / Sum(Number of reads)**

Where:

- **Q score** = Phred quality score

- **Number of reads** = frequency of reads observed at that Q score

---

## Total weighted contribution

**Sum(Q × Reads) = 44,514,948**

## Total reads

**Sum(Reads) = 2,428,875**

## Weighted mean calculation

**Mean Q score = 44,514,948 / 2,428,875**

**Mean Q score = 18.3261**

Rounded to two decimal places:

**Mean Q score = 18.33**

---

# Summary statistics

| Statistic | Description | Value |
|---|---|---:|
| Minimum Q score | Lowest observed quality score | Q1 |
| Maximum Q score | Highest observed quality score | Q35 |
| Mean Q score | Weighted mean quality score | 18.33 |
| Mode Q score | Most frequent quality score | Q24 |

---
---End of Report---
