+++
date = "2018-02-06"
draft = false
title = "Natural Variation in Gene Expression Modulates the Severity of Mutant Phenotypes"
author = "Yanyu Liang"
ghcommentid = 5
tags = ["epistasis"]
topics = ["genetics"]
+++

## Biological question

Mutation in monogenic disease can cause disease phenotype at various level of severity.

For instance, cystic fiberosis (CF) is caused by a single gene, *CFTR*, the homozygous individuals with exactly the same allele $\delta$F508 present a wide range of clinical symptoms. It is due to "modifier genes", *MBL2* and *TGF-$\beta$*.

Such observation is general in many Mendelian diseases. Namely, the disease is predictable but the severity of it is highly unknown due to the variation of genetic background.

So, the biological question is: How does genetic background affect the severity of a mutation? (How ubiquitous? Is there underlying pattern?)

## Main finding

## Experimental approach

### Gene set

There are many known RNAi knockdown phenotypes in *C. elegans* (i.e. sterility, lethality, tissue development defect, etc). 1,353 genes were selected and their outcomes were tested on two *C. elegans* isolates (N2 Bristol and CB4856; two distinct genetic backgrounds; differ 1 SNP per 800 bp on average).

### Quantifying phenotype

#### Fact

*C. elegans* life: L1 -> L2 -> L3 -> adults

#### Procedure

15 L1 worms + RNAi -> -> 4-day observation -> -> 15 adults with their L1, L2, L3 progeny. The outcome is compared with respect to negative control to negative control to be quantified.

#### Measurement

![Figure 1](/victoria-2015-cell/fig1.png)

#### Correcting for RNAi uptake

RNAi has different efficacy in N2 and CB4856 due to null mutation in *ppw-1* in CB4856. It has been corrected for cases where N2 has a more severe phenotype in N2.

#### False positives of RNAi approach

8 genes with differential severity in RNAi experiment were confirmed by genetic mutants. 6 out of 8 genes were detected with the same effect.

## Results

### Functional enrichment

For genes causing more severe phenotypes in N2/CB4856, whether they tend to have similar function? For instance, genes affecting N2 enriched in electron transport chain (ETC) and P granule regulator whereas genes affecting CB4856 enriched in protein synthesis and fibrous organelle (FO). The same sensitivity trend was found using chemical to interfere the worm.

![Figure 4](/victoria-2015-cell/fig4.png)


### Variation in gene expression

#### Functional module activity ~ severity

20% genes have differential severity but the coding sequences are almost the same between two worms, so that they hypothesized that the difference is due to expression level difference of the gene.

For the four functional modules which enrich genes with the same direction, the expression level of the proteins in the module (module baseline activity) is consistent with the severity result (high severity -> high sensitivity -> low baseline activity)

![Figure 5A (note that the RNA-seq was done in wildtype w/o any treatment)](/victoria-2015-cell/fig5a.png)

#### Gene baseline expression ~ severity

In particular, for the detected genes (which is a member of the module), its baseline expression level in two worms consistent with their severity as well.

#### Altering gene baseline expression -?-> severity

*vab-10* is in FO module which has high activity in N2. N2 strain with *vab-10* homozygous hypomorphic allele decreases the baseline activity of *vab-10*.

![Figure 5B](/victoria-2015-cell/fig5b.png)

#### Altering functional module activity -?-> severity

*unc-52* is also in FO module.

![Figure 5C](/victoria-2015-cell/fig5c.png)

#### Replication in CB4856

*cgh-1* is in P granule module which has high activity in CB4856. Also, *pos-1* and *mex-3* are in P granule module.

![Figure 5D](/victoria-2015-cell/fig5d.png)

The effect is more than additive.

### Gene expression is predictive for severity

They explored the relationship between gene expression and severity by adding two more *C. elegans* isolates, AB1 and ED3040. They focused on the ETC functional module. (A: gene expression level; B: severity in each worm type; C: severity against expression level (relative to species average); D: sensitivity to chemical; E: correlation of expression and severity in mammalian cell (18 cell lines were used); F: one instance of E)

![Figure 6](/victoria-2015-cell/fig6.png)

## Discussion

Genetic background impacts the severity of the genetic perturbation. In particular, natural variation of gene expression impacts the severity of mutation. In other words, the effect size of mutation depends on the genetic background.
