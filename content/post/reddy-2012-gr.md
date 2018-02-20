+++
date = "2018-02-20"
draft = false
title = "Effects of sequence variation on differential allelic transcription factor occupancy and gene expression"
author = "Gao Wang"
ghcommentid = 6
tags = ["regulatory sequences"]
topics = ["regulatory genomics"]
+++

By Reddy T. et al (2012) Genome Research.

First, for audience not very familiar with the context:

- Transcription factors: Bind specific DNA motif & controls gene expression
- Chromatin Immunoprecipitation Sequencing: [Cartoon: ChIP-Seq with chips](https://v.qq.com/iframe/player.html?vid=o1323heyigc)
- Differential allelic <TF occupancy / expression>: 
  - Alleles are different versions of the same gene. 
  - To focus on allelic imbalance means to focus on heterozygotes
- Differential allelic TF occupancy (DATO):
  - preference to bind one allele over another, within the same cell type 
- Allele specific expression (ASE): 
  - Explained in part as functional consequence of differential allelic TF binding 
- *EP300*: histone acetyltransferase p300, makes DNA more accessible to TF

This paper was published in 2012: when exome sequencing was just becoming widely adopted.

## Question

Variant discovery & annotation
- variant --> disease (GWAS / exome sequencing)
- variant --> expression --> disease (eQTL/tWAS)
- variant --> TF occupancy imbalance --> expression & disease (this paper)

This paper studies impact of genetic variation on gene regulation. Specifically it aims to identify DATO sites and understand their properties wrt gene expression and disease

## Conclusion
- Variation in core TF binding motifs: small in fraction, large in effects wrt DATO 
- DATO sites significantly enriched disease variants particularly autoimmune disease

## Approach

Measure allelic differences in expression in the same cells. RNA-Seq + Chip-Seq
- **why**: RNA-seq only limits to heterozygous exonic variants

Method:
- Genome-wide RNA-Seq
- TF occupancy of RNA Pol2 of *EP300* and of 24 sequences specific TFs
- 1000 Genomes female LCL
- Aligned sequence reads to both the maternal and paternal versions of the genome

## Results

### TF hubs

- TF cluster on the same alleles in regions of open chromatin
- **why**: 
- DATO evenly distributed across autosomes
- 30% are in *hubs* (more than 2 TF), compared to 15% non-DATO as hubs
  - Sites are **cooperative**
  - hubs are sensitive to variation
- DATO in hubs often reside on the same allele (**Figure 1B**), a pattern non-exist in non-DATO
  - Existence of coordinated differential allelic gene regulation
  - Except for co-occupancy in a few cases such as *EP300*, these (novel) hubs are generally not explained by known PPI
- Variants in hubs are more conserved (**Figure 1D**)
  
### DATO variants

- Strong enrichment of DATO variants within 50bp of maximal ChIP signal
- Heterozygous variants in motif are 3 times more likely to occur in DATO sites
- Variants in DNA binding motif (of strong effects) explains only 12% DATO

### DATO and allele specific expression (ASE)

- Using RNA-Seq alone, 9% genes with exonic heterozygous variants (4194 transcripts) have ASE
  - Effect sizes are small for autosomal genes
  - 4194 transcripts represents only 39% of transcripts in sample
- Using RNA Pol2 ChIP-Seq, 6.3% (out of 10,353) with variants in RNA Pol2 sites have ASE 
  - Cross clone variations: strong concordance in ASE on autosomes
  - These variants significantly but imperfectly explains variations in expression
- Combined results: 910 genes in sample have ASE

### Heritibility: DATO vs ASE

- The stronger allele in DATO sites has greater ChIP-Seq signal in corresponding parent in 81% of the cases 
  - Compared to 60% for ASE
- DATO is more strongly determined by local sequences

### ASE genes are lower expressed and more tissue specific

Highly expressed genes are more conserved: a closer link between gene expression and evolutionary conservation than previously been shown.

### TF occupancy explains variation in gene expression

- DATO are significantly closer to genes with ASE than without
  - 6.8% sites within 100kb of ASE genes has DATO
  - 3.9% sites within non-ASE genes has DATO
- non-DATO no closer to genes with ASE
- Strong positive DATO and ASE correlation observed within 100bp of TSS
  - i.e, highly predictive

### Disease significance of DATO
- 155 autosomal variants in TF binding sites associated with disease
- 21 of them are DATO variants

