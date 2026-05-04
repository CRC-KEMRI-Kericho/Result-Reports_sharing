## Detailed Parameter analysis assessment

The analysis involved a distributed parameter sweep to evaluate the impact of read quality filtering and UMI detection stringency on UMI family recovery across all the barcodes. :contentReference[oaicite:0]{index=0}  

For each parameter combination, defined by minimum Phred quality score (MQ15–MQ23) and maximum allowed UMI detection error (MAXERR0–MAXERR18), reads were processed through three sequential steps:

1. read pre-processing  
2. primer–spacer–UMI detection  
3. UMI correction using a strand-aware clustering approach  

The sweep explored a total of:

- 9 Phred quality thresholds (15–23)
- 19 UMI detection error levels (0–18)
- 1 spacer mismatch setting (SP=0)

resulting in 171 parameter combinations per barcode.

---

## High-level summaries extracted from the runs

Description of columns:

- **Barcode:** Sample identifier for each dataset.  

- **Raw_Reads:** Reads retained after preprocessing and coordinate filtering.  

- **UMI_Reads:** Reads containing a valid UMI structure.  

- **UMI%:** Percentage of reads with UMIs relative to retained reads.  

- **UMI_families_Dist0_before_correction:** Number of unique UMI families before error correction.  

- **UMI_families_Dist_1_after_correction:** Number of UMI families after correction (collapsed families).  

- **family_size > N:** Number of UMI families with read_count greater than N (e.g., family_size>5 = families supported by >5 reads).  

- **Largest_family_size:** Maximum number of reads observed in a single UMI family.  

---
### Examples

- **Phred score:** Minimum base quality threshold applied to filter low-quality reads.

- **Max error:** Maximum allowed mismatches during UMI detection (0 = exact matching only).


### Phred score quality 17 and Max Error 0:

| Barcode   | Raw_Reads | UMI_Reads | UMI%  | UMI_families_Dist_0 | UMI_families_Dist_1 | family_size>5 | family_size>6 | family_size>7 | family_size>8 | family_size>9 | family_size>10 | family_size>11 | family_size>12 | family_size>13 | family_size>14 | family_size>15 | family_size>16 | family_size>17 | family_size>18 | family_size>19 | family_size>20 | family_size>30 | family_size>40 | family_size>50 | family_size>100 | Largest_family_size |
| --------- | --------- | --------- | ----- | ------------------------------------ | ----------------------------------- | ------------- | ------------- | ------------- | ------------- | ------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | --------------- | ------------------- |
| Barcode01 | 157545    | 142829    | 90.66 | 30509                                | 13477                               | 3163          | 2794          | 2508          | 2263          | 2085          | 1925           | 1769           | 1644           | 1562           | 1489           | 1413           | 1353           | 1300           | 1253           | 1205           | 1169           | 885            | 711            | 604            | 359             | 365                 |
| Barcode02 | 13443     | 11795     | 87.74 | 2665                                 | 2043                                | 141           | 131           | 120           | 112           | 107           | 101            | 96             | 92             | 88             | 85             | 81             | 79             | 78             | 78             | 74             | 72             | 61             | 52             | 44             | 20              | 663                 |
| Barcode03 | 31670     | 21491     | 67.86 | 15508                                | 7957                                | 722           | 506           | 388           | 303           | 237           | 190            | 154            | 123            | 101            | 86             | 79             | 74             | 67             | 62             | 56             | 51             | 23             | 12             | 6              | 0               | 100                 |
| Barcode04 | 94236     | 85365     | 90.59 | 15157                                | 7938                                | 1286          | 1112          | 995           | 886           | 825           | 766            | 715            | 680            | 646            | 624            | 605            | 579            | 565            | 550            | 534            | 522            | 401            | 349            | 311            | 191             | 510                 |
| Barcode05 | 35600     | 21355     | 59.99 | 9772                                 | 5736                                | 602           | 493           | 428           | 352           | 305           | 288            | 269            | 252            | 235            | 212            | 193            | 184            | 171            | 162            | 152            | 144            | 93             | 75             | 50             | 15              | 203                 |
| Barcode06 | 282510    | 260060    | 92.05 | 9891                                 | 5146                                | 1084          | 988           | 932           | 884           | 852           | 826            | 809            | 789            | 782            | 772            | 748            | 740            | 732            | 725            | 717            | 708            | 672            | 651            | 637            | 600             | 918                 |
| Barcode07 | 46047     | 40623     | 88.22 | 3976                                 | 2739                                | 443           | 406           | 384           | 360           | 347           | 328            | 315            | 300            | 293            | 282            | 274            | 269            | 262            | 256            | 244            | 235            | 213            | 197            | 185            | 146             | 451                 |
| Barcode08 | 319762    | 292934    | 91.61 | 8430                                 | 4149                                | 1103          | 1048          | 1014          | 991           | 978           | 961            | 951            | 937            | 934            | 928            | 924            | 918            | 909            | 905            | 904            | 901            | 882            | 874            | 871            | 840             | 812                 |
| Barcode09 | 40392     | 36185     | 89.58 | 1303                                 | 924                                 | 485           | 481           | 470           | 467           | 457           | 452            | 444            | 427            | 418            | 406            | 397            | 387            | 379            | 370            | 367            | 361            | 280            | 228            | 200            | 145             | 296                 |



### Phred score quality 18 and Max Error 0: 

| Barcode   | Raw_Reads | UMI_Reads | UMI%  | UMI_families_Dist_0 | UMI_families_Dist_1 | family_size>5 | family_size>6 | family_size>7 | family_size>8 | family_size>9 | family_size>10 | family_size>11 | family_size>12 | family_size>13 | family_size>14 | family_size>15 | family_size>16 | family_size>17 | family_size>18 | family_size>19 | family_size>20 | family_size>30 | family_size>40 | family_size>50 | family_size>100 | Largest_family_size |
| --------- | --------- | --------- | ----- | ------------------------------------ | ----------------------------------- | ------------- | ------------- | ------------- | ------------- | ------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | --------------- | ------------------- |
| Barcode01 | 148970    | 135653    | 91.06 | 29273                                | 13013                               | 3065          | 2687          | 2416          | 2181          | 1993          | 1843           | 1688           | 1589           | 1493           | 1427           | 1368           | 1306           | 1250           | 1210           | 1169           | 1122           | 857            | 682            | 591            | 345             | 339                 |
| Barcode02 | 11880     | 10484     | 88.25 | 2227                                 | 1766                                | 128           | 118           | 107           | 103           | 96            | 94             | 84             | 83             | 79             | 78             | 77             | 77             | 76             | 73             | 71             | 69             | 56             | 46             | 41             | 18              | 616                 |
| Barcode03 | 24722     | 16093     | 65.10 | 11880                                | 6504                                | 441           | 292           | 215           | 151           | 114           | 92             | 82             | 72             | 61             | 55             | 46             | 40             | 39             | 37             | 37             | 34             | 14             | 9              | 4              | 0               | 88                  |
| Barcode04 | 86145     | 78472     | 91.09 | 14051                                | 7532                                | 1188          | 1035          | 931           | 828           | 770           | 719            | 683            | 653            | 621            | 597            | 576            | 554            | 542            | 531            | 509            | 495            | 391            | 334            | 295            | 180             | 465                 |
| Barcode05 | 27932     | 15566     | 55.73 | 7014                                 | 4454                                | 416           | 338           | 283           | 255           | 232           | 218            | 207            | 186            | 167            | 158            | 149            | 144            | 134            | 127            | 119            | 115            | 77             | 54             | 36             | 9               | 178                 |
| Barcode06 | 257407    | 238341    | 92.59 | 8917                                 | 4770                                | 1017          | 939           | 886           | 847           | 818           | 802            | 786            | 764            | 746            | 741            | 735            | 724            | 716            | 711            | 702            | 697            | 665            | 646            | 630            | 593             | 841                 |
| Barcode07 | 40630     | 36073     | 88.78 | 3193                                 | 2291                                | 399           | 370           | 347           | 331           | 313           | 302            | 293            | 279            | 272            | 264            | 256            | 248            | 240            | 234            | 227            | 222            | 206            | 188            | 177            | 142             | 403                 |
| Barcode08 | 290777    | 267806    | 92.10 | 7555                                 | 3797                                | 1061          | 1016          | 984           | 971           | 955           | 944            | 931            | 928            | 923            | 914            | 908            | 903            | 901            | 899            | 897            | 895            | 878            | 874            | 868            | 829             | 740                 |
| Barcode09 | 36696     | 33068     | 90.11 | 1202                                 | 864                                 | 481           | 477           | 468           | 460           | 449           | 441            | 430            | 417            | 403            | 393            | 381            | 372            | 365            | 362            | 354            | 343            | 260            | 212            | 193            | 133             | 267                 |


### Phred score quality 19 and Max Error 0: 

| Barcode   | Raw_Reads | UMI_Reads | UMI%  | UMI_families_Dist_0 | UMI_families_Dist_1 | family_size>5 | family_size>6 | family_size>7 | family_size>8 | family_size>9 | family_size>10 | family_size>11 | family_size>12 | family_size>13 | family_size>14 | family_size>15 | family_size>16 | family_size>17 | family_size>18 | family_size>19 | family_size>20 | family_size>30 | family_size>40 | family_size>50 | family_size>100 | Largest_family_size |
| --------- | --------- | --------- | ----- | ------------------------------------ | ----------------------------------- | ------------- | ------------- | ------------- | ------------- | ------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | --------------- | ------------------- |
| Barcode01 | 137012    | 125342    | 91.48 | 27484                                | 12353                               | 2899          | 2564          | 2293          | 2033          | 1846          | 1733           | 1600           | 1507           | 1434           | 1364           | 1293           | 1249           | 1193           | 1154           | 1119           | 1078           | 817            | 642            | 551            | 322             | 305                 |
| Barcode02 | 9878      | 8750      | 88.58 | 1775                                 | 1451                                | 110           | 106           | 97            | 91            | 86            | 80             | 77             | 75             | 75             | 74             | 74             | 72             | 72             | 67             | 65             | 63             | 50             | 43             | 39             | 18              | 524                 |
| Barcode03 | 18406     | 11463     | 62.28 | 8646                                 | 5181                                | 238           | 167           | 113           | 84            | 75            | 59             | 49             | 41             | 40             | 35             | 30             | 29             | 28             | 27             | 25             | 22             | 8              | 5              | 2              | 0               | 77                  |
| Barcode04 | 73811     | 67662     | 91.67 | 12433                                | 6894                                | 1057          | 922           | 837           | 763           | 712           | 674            | 642            | 603            | 572            | 554            | 533            | 507            | 492            | 482            | 472            | 451            | 360            | 318            | 267            | 157             | 396                 |
| Barcode05 | 20941     | 10615     | 50.69 | 4679                                 | 3296                                | 287           | 235           | 210           | 189           | 170           | 151            | 143            | 135            | 127            | 120            | 109            | 104            | 99             | 94             | 89             | 84             | 54             | 32             | 21             | 5               | 141                 |
| Barcode06 | 219687    | 204778    | 93.21 | 7656                                 | 4251                                | 945           | 873           | 833           | 810           | 791           | 771            | 756            | 740            | 729            | 720            | 708            | 704            | 695            | 690            | 686            | 683            | 655            | 636            | 621            | 587             | 727                 |
| Barcode07 | 33674     | 30041     | 89.21 | 2431                                 | 1809                                | 352           | 329           | 310           | 294           | 278           | 269            | 261            | 248            | 239            | 236            | 232            | 224            | 218            | 217            | 212            | 209            | 191            | 178            | 168            | 129             | 351                 |
| Barcode08 | 247508    | 229338    | 92.66 | 6366                                 | 3321                                | 1012          | 977           | 959           | 943           | 932           | 920            | 912            | 907            | 902            | 899            | 897            | 895            | 890            | 888            | 887            | 883            | 875            | 868            | 858            | 822             | 647                 |
| Barcode09 | 31171     | 28286     | 90.74 | 1064                                 | 790                                 | 473           | 468           | 457           | 443           | 431           | 419            | 400            | 391            | 381            | 369            | 356            | 351            | 342            | 331            | 323            | 308            | 234            | 199            | 184            | 109             | 235                 |


### Phred score quality 20 and Max Error 0: 

| Barcode   | Raw_Reads | UMI_Reads | UMI%  | UMI_families_Dist_0 | UMI_families_Dist_1 | family_size>5 | family_size>6 | family_size>7 | family_size>8 | family_size>9 | family_size>10 | family_size>11 | family_size>12 | family_size>13 | family_size>14 | family_size>15 | family_size>16 | family_size>17 | family_size>18 | family_size>19 | family_size>20 | family_size>30 | family_size>40 | family_size>50 | family_size>100 | Largest_family_size |
| --------- | --------- | --------- | ----- | ------------------------------------ | ----------------------------------- | ------------- | ------------- | ------------- | ------------- | ------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | -------------- | --------------- | ------------------- |
| Barcode01 | 120023    | 110426    | 92.00 | 24929                                | 11429                               | 2670          | 2329          | 2053          | 1839          | 1700          | 1585           | 1490           | 1406           | 1318           | 1252           | 1203           | 1151           | 1104           | 1066           | 1025           | 984            | 735            | 583            | 498            | 289             | 279                 |
| Barcode02 | 7356      | 6569      | 89.30 | 1315                                 | 1109                                | 93            | 89            | 83            | 79            | 76            | 72             | 71             | 70             | 68             | 66             | 60             | 58             | 56             | 55             | 55             | 53             | 43             | 37             | 28             | 12              | 399                 |
| Barcode03 | 12522     | 7465      | 59.62 | 5865                                 | 3866                                | 115           | 84            | 61            | 46            | 39            | 33             | 32             | 29             | 29             | 29             | 26             | 21             | 18             | 13             | 11             | 9              | 6              | 1              | 1              | 0               | 63                  |
| Barcode04 | 56627     | 52286     | 92.33 | 10054                                | 5895                                | 883           | 784           | 708           | 656           | 616           | 574            | 537            | 513            | 502            | 481            | 467            | 449            | 434            | 419            | 404            | 394            | 319            | 266            | 230            | 141             | 304                 |
| Barcode05 | 14426     | 6651      | 46.10 | 2940                                 | 2276                                | 191           | 161           | 144           | 132           | 123           | 111            | 103            | 97             | 88             | 81             | 76             | 72             | 66             | 61             | 56             | 54             | 32             | 16             | 11             | 0               | 89                  |
| Barcode06 | 166865    | 156611    | 93.85 | 5951                                 | 3523                                | 853           | 801           | 775           | 756           | 741           | 721            | 714            | 700            | 691            | 685            | 679            | 676            | 672            | 667            | 663            | 660            | 638            | 617            | 607            | 577             | 579                 |
| Barcode07 | 24801     | 22260     | 89.75 | 1709                                 | 1341                                | 298           | 283           | 271           | 252           | 242           | 235            | 227            | 220            | 213            | 206            | 203            | 201            | 199            | 196            | 193            | 190            | 175            | 163            | 154            | 101             | 255                 |
| Barcode08 | 187199    | 174558    | 93.25 | 4881                                 | 2682                                | 949           | 936           | 922           | 912           | 905           | 903            | 898            | 888            | 887            | 885            | 884            | 883            | 881            | 879            | 878            | 877            | 867            | 858            | 851            | 805             | 488                 |
| Barcode09 | 23666     | 21627     | 91.38 | 912                                  | 702                                 | 454           | 438           | 422           | 399           | 383           | 369            | 360            | 351            | 339            | 324            | 313            | 298            | 287            | 279            | 269            | 259            | 198            | 179            | 163            | 71              | 179                 |



The rest of the parameter combinations, totaling up to 171 runs, can be accessed here [High Level summary parameter combination assessments](https://github.com/CRC-KEMRI-Kericho/Result-Reports_sharing/tree/main/Consensus_Building/Consensus_Building/Results/collected_high_level_summaries)


### Best Parameter combinations per Barcode across the 171 runs are shown below: 

**To be shared during the update meeting**

----End of Report---





