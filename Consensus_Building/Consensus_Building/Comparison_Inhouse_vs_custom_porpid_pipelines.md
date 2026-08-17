# Comparison between In-house and customized Porpid pipeline Final consensus outputs

## 1. Number of final consensus outputs
Here we include the final consensus of the in-house pipeline, the customized Porpid pipeline, and the customized Porpid pipeline rescue logic applied, but with rescued consensus (where rejected consensus is due to a
 single position with a minimum agreement of below 0.7 but above 0.5 were included in the final consensus).

 Sample	No. of In-house seqs	No. of PORPID seqs	No. of PORPID with rescue seqs	No. of common UMIs	Difference (In-house - PORPID)
bc2001	442	414	436	387	28
bc2002	793	257	789	229	536
bc2003	1698	1512	1601	1440	186
bc2004	464	414	436	395	50
bc2005	287	261	282	247	26
bc2006	737	491	717	464	246
bc2007	691	622	650	598	69
bc2008	407	452	474	364	-45
bc2009	4416	4170	4170	3735	246

## 2. Analysis of the common UMIs

The in-house umis had an extra 20 bp motif, **AAGCCTCAATAAAGCTTGCC**, at the 3'-end. The motif corresponds to part of the specific primer sequence (28 bp ) **"AAGCCTCAATAAAGCTTGCC*TTGAGTGC**.

Other than the extra motif, the lengths of all the sequences remain identical.

## ALIGNMENT EXAMPLES

Common umi |Alignment|
AAAATTAC|

## 3.  Alignment of Unique UMIs



## 4. Reccommedations

Adapt the in-house pipeline, however we should deliberate the below key questions for the in-house pipeline:
     - Either fully trim the specific primer sequence or leave it fully intact (For further consultations)
     - Whether to increase the minimum Phred score quality from the current 18, since sequencing technology has also improved, reducing the number of errors incorporated during sequencing.
     - Whether to increase the minimum family size from the current 5 to 7 to increase on the consensus call confidence/quality


