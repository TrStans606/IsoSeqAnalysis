# IsoSeqAnalysis
Steps of my analysis used in IsoSeq 

WT steps for the CPR1 gene:
Step 1: Lima
```lima m64146_230816_190133.hifi_reads.bam PacBioPrimers.fa movieX.fl.bam --isoseq --peek-guess```
Step 2: Isoseq Refine
```isoseq refine movieX.fl.3prime_3p--5prime_5p.bam PacBioPrimers.fa movieX.flnc.bam --require-polya```
Step 3: IsoSeq Cluster2
```isoseq cluster2 movieX.flnc.bam WT_clusters.bam```
Step 4: Pbmm2 Allign
```pbmm2 align --preset ISOSEQ --sort WT_clusters.bam CPR1_Genomic_flank_genes_rev_comp.fa WT_CPR1_mapped.bam```
Step 5: Isoseq Collapse
```isoseq collapse WT_CPR1_mapped.bam WT_CPR1_collapsed.gff```
