DataPathwayGuidedRF
================

This R package provides the experimental benchmark data sets for the paper "Integrating biological knowledge and gene expression data using pathway guided random forests: A benchmarking study". Normalized data sets were obtained from GEO and the Summarized Experiment objects in this package contain these data sets further preprocessed. For more details about the preprocessing please read the methods section of the paper.

Installation
------------

Since the data is stored in as a Summarized Experiment object, we have to install the package SummarizedExperiment from Bioconductor:

``` r
if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")

BiocManager::install("SummarizedExperiment")
```

You can install the most recent version of DataPathwayGuidedRF from GitHub as follows:

``` r
library(devtools)
install_github("szymczak-lab/DataPathwayGuidedRF")
```

Obtain data and information about samples and genes
---------------------------------------------------

We will demonstrate how to extract the data and information from the data set GSE8671.

First, we load the packages and the data:

``` r
library(DatapwguidedRF)
library(SummarizedExperiment)
data(GSE8671)
```

To obtain the data:

``` r
data = assays(GSE8671)$expr
```

To obtain information about the samples (The column outcome corresponds to the outcome that was used in the paper):

``` r
samples.info = colData(GSE8671)
```

To obtain information about the genes:

``` r
genes.info = rowData(GSE8671)
```
