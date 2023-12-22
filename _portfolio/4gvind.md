---
title: "NEURO"
excerpt: "RNA seq pipeline for processing of human Illumina reads into differential expression counts <br/><img src='/images/500x300.png'>"
collection: portfolio
---

This project was done as part of CSC542 - Bioinformatics I, where we were investigating for overlapping gene expression in various neurodegenerative diseases. Potential genetic correlation could lead to an improved idea of the underlying causes of Alzheimer's, Parkinson's, or Lou Gehrig's disease (ALS). 

In particular, I modified an existing RNA pipeline to work for our purposes. We used several industry standard tools for our analysis:

- Snakemake for pipeline definition
- FastQC/Trimmomatic for trimming raw reads
- HISAT2 for sequence alignment
- HTSeq for gene count

These gene counts were then fed into an R script (written separately) that calculated the differential expression counts and summarized the results in relevant heatmaps and other plots.

This pipeline was run one of the clusters available to URI students, and was used to process 58 human brain samples across the aforementioned diseases for our analysis. For alignment, the human genome released in 2022 was utilized, which did add a novel dimension to our analysis. The particular human reference genome utilized in our analysis was released during development of our pipeline, so at the time the results generated were unable to have been previously attained. 