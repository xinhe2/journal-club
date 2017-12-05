+++
date = "2017-12-05"
draft = false
title = "Spatial reconstruction of single-cell gene expression data"
author = "Shengtong Han"
ghcommentid = 2
tags = ["single cell RNA-seq"]
topics = ["single cell"]
+++

## Problem

-   infer spatial locations of various cell types which will determine
    the cell fate and behavior

-   RNA staining only assays a small number of transcripts and RNA-seq
    can measure the global gene expression, but separates the cells from
    their native spatial context.

-   they develop Seurat to localize the cells by integrating single cell
    RNA-seq data and in situ RNA patterns.

## Modeling

### Overview

Figure 1 gives the overview of the method.

1.  collect single cell RNA-seq data from dissociated cells while,
    spatial original context information is lost

2.  in situ hybridization patterns for a series of landmark genes
    (Landmark genes were selected as those widely expressed across
    lineage and were found to have good predictive power for inferring
    the expression of other genes that are not directly measured in the
    assay.)

3.  use machine learning to infer expression pattern (64 bins)

4.  build expression model of 47 landmark genes in each region of
    interest

5.  infer cell’s spatial origin probabilistically by comparing each
    cell’s expression of landmark genes to expression model of each
    region.

![](/201711/seurat.jpg)

Seurat has the following features

-   due to the sparsity of single cell RNA seq data, use co-expression
    patterns across cells to impute the expression of each landmark gene
    in each cell

-   relates the continuous imputed RNA-seq expression levels of each
    landmark gene to the binary spatial expression values using a
    mixture model

-   constructs a multivariate normal model for the joint expression of
    the landmark genes based on these mixture models

-   infers the spatial origin of each profiled cell by calculating a
    posterior probability for each cell-bin pair, allowing determination
    of the cell’s likely position(s) and confidence in the mapping

### Matching binary in situ hybridizations to continuous, noisy RNA-seq data

-   Single cell RNA-seq data are confounded with technical noise. Seurat
    leverages the fact that RNA-seq measures multiple genes that are
    co-regulated with the landmark genes and uses these genes to impute
    the values of the landmark genes

-   for each landmark gene, Seurat relate its continuous imputed RNA-seq
    expression levels to its binary state in the landmark map. Seurat
    relates the typical bimodal distribution of its imputed expression
    measurements to the on and off modes of the spatial reference map.
    Fit the distribution of imputed values of each landmark gene as a
    mixture of two Gaussian distributions by using R function
    normalmixEM with two modifications.

### Probabilistic inference of spatial origin

-   Seurat constructs a model for the joint expression of the landmark
    genes in each bin based on the parameters of the mixture models and
    the binary spatial reference map, i.e., build 64 distinct
    multivariate normal models.

-   Seurat calculates the likelihood that this cell’s expression of the
    landmark gene reflects the on state, and thus, a probability that
    this cell originated from each of 64 bins marked as on in the
    reference map

-   Seurat infers the posterior probability that a cell is originated
    from each of bins in the reference map

## Possible improvements

-   use continuous gene expression not just ``on'' and ``off'' in reference
    map

-   what other information could be utilized to guide the cell
    assignments

-   is it biologically feasible to use a barcode to label the spatial
    origins for each cell?
