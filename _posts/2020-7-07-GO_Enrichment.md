---
layout: post
title: "Enrichment analysis"
categories: 
tags: 
---


# Examining Results From a prior Enrichment Analysis

We used the GO Enrichment analysis found here:
https://github.com/z0on/GO_MWU

This test used the 'Mann-Whitney U test' method. that means that instead of looking at significant genes, it looks at the entire dataset. It looks for where similar genes are bunched up in the table of gene significance levels.

### Here is one of the output graphs


![Enrichment]({{ site.baseurl }}/images/GO_d2s_BP.png "Enrichment analysis")

The font indicates the level of significance. The colors in the graph either indicate up regulated or down regulated genes, 

If there is no branch length difference between two of the Gene clusters it means they are likely regulated by the same gene, so in this example "translation" and "cytoplasmic translation" so their significance is driven by the same genes


## Results

Four catagories of results were output: d2s, s2d, depth, and species

Each of these had three different graphs: MF (Molecular Function), CC (Cellular component), and BP (Biological process)

## Biological process

### deep to shallow
![BP-d2s]({{ site.baseurl }}/images/MWU_BP_d2s.r_DE_resultsFOLDCHANGE.pdf "Enrichment analysis")

### depth
![BP-depth]({{ site.baseurl }}/images/MWU_BP_depth.r_DE_results_FOLDCHANGE.pdf "Enrichment analysis")

### shallow to deep
![BP-s2d]({{ site.baseurl }}/images/MWU_BP_s2d.r_DE_results_adjp.pdf "Enrichment analysis")

### species
![BP-species]({{ site.baseurl }}/images/MWU_BP_species.r_DE_results_FOLD_CHANGE.pdf "Enrichment analysis")

## Cellular Component

### deep to shallow
![CC-d2s]({{ site.baseurl }}/images/MWU_CC_d2s.r_DE_resultsFOLDCHANGE.pdf "Enrichment analysis")

### depth
![CC-depth]({{ site.baseurl }}/images/MWU_CC_depth.r_DE_results_FOLDCHANGE.pdf "Enrichment analysis")

### species
![CC-species]({{ site.baseurl }}/images/MWU_CC_species.r_DE_results_FOLD_CHANGE.pdf "Enrichment analysis")



## Molecular Function

### deep to shallow
![MF-d2s]({{ site.baseurl }}/images/MWU_MF_d2s.r_DE_resultsFOLDCHANGE.pdf "Enrichment analysis")

### depth
![MF-depth]({{ site.baseurl }}/images/MWU_MF_depth.r_DE_results_FOLDCHANGE.pdf "Enrichment analysis")

### species
![MF-species]({{ site.baseurl }}/images/MWU_MF_species.r_DE_results_FOLD_CHANGE.pdf "Enrichment analysis")

### shallow to deep
![MF-s2d]({{ site.baseurl }}//images/MF_s2d.r_DE_results_FOLD_CHANGE.pdf "Enrichment analysis")

