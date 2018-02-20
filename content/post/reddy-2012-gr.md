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
- Chromatin Immunoprecipitation Sequencing: [Cartoon: ChIP-Seq with chips](https://v.qq.com/iframe/player.html?vid=o1323heyigc&amp;width=670&amp)
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

Goal: identify DATO sites and understand their properties wrt gene expression and disease

## Conclusion
- Variation in core TF binding motifs: small in fraction, large in effects wrt DATO 
- DATO sites significantly enriched disease variants particularly autoimmune disease

## Approach

Approach
- measure allelic differences in expression in the same cells. RNA-Seq + Chip-Seq
- **why**: RNA-seq only limits to heterozygous exonic variants
- Aligned sequence reads to both the maternal and paternal versions of the genome

## Results

### TF hubs

- TF cluster on the same alleles in regions of open chromatin
- **why**: 
- DATO evenly distributed across autosomes
- 30% are in *hubs* (more than 2 TF), compared to 15% non-DATO in hubs
- DATO in hubs often reside on the same allele (**Figure 1B**), a pattern non-exist in non-DATO
  - Existence of coordinated differential allelic gene regulation
  - Except for co-occupancy in a few cases such as *EP300*, these (novel) hubs are generally not explained by known PPI
- Variants in hubs are more conserved (**Figure 1D**)
  
### DATO variants

- Strong enrichment of DATO variants within 50bp of maximal ChIP signal
- Heterozygous variants in motif are 3 times more likely to occur in DATO sites
- Variants in DNA binding motif explains only 12% DATO
  - of weak effects


