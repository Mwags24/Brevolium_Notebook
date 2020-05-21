---
layout: post
title: "Making Graphs of Depths"
categories: 
tags: 
---

## A Graph for all depths (5x, 10x, 15x, 20x, 25x, 30x)


In order to make graphs I loaded the files into R

Using this code in my local terminal I downloaded the files I needed onto my computer

    scp -r myles_wagner@bluewaves.uri.edu:/data/pradalab/Brevolium_depth/vcf_files/brevolium_snps_biallelic_mac3_miss50_10x.recode.vcf /Users/myles/Desktop/brevolium

Then in R I used the following code to create some preliminary graphs.

library(ggplot2)
library(vcfR)
library(adegenet)

VCF_23123_SNPs <- read.vcfR ("brevolium_snps_biallelic_mac3_miss50_5x.recode.vcf")

VCF_23123_SNPs

genlight_23123_SNPs <- vcfR2genlight(VCF_23123_SNPs)
genlight_23123_SNPs


genlight_23123_SNPs_pca <- glPca(genlight_23123_SNPs, nf=3)

genlight_23123_SNPs_pca_scores <- as.data.frame(genlight_23123_SNPs_pca$scores)
genlight_23123_SNPs_pca_scores


set.seed(9)
p <- ggplot(genlight_23123_SNPs_pca_scores, aes(x=PC1, y=PC2))
p <- p + geom_point(size=2)
p <- p + geom_hline(yintercept = 0)
p <- p + geom_vline(xintercept = 0)
theme<-theme(panel.background = element_blank(),panel.border=element_rect(fill=NA),panel.grid.major =
               element_blank(),panel.grid.minor = element_blank(),strip.background=element_blank(),
             axis.text.x=element_text(colour="black"),axis.text.y=element_text(colour="black"),
             axis.ticks=element_line(colour="black"),plot.margin=unit(c(1,1,1,1),"line"))
p <- p +theme
p

# Load pop data

```{r}
pop.data <- read.table("mappingfile_2.txt", sep = "\t", header = TRUE)
pop.data
```

# Assign pop (genotype and environment) data to the genlight object

```{r}
strata(genlight_23123_SNPs) <- pop.data
strata(genlight_23123_SNPs) 

```

```{r}
library(adegenet)
genlight_23123_SNPs@pop <- genlight_23123_SNPs@strata$environment
cols <- diverge_hcl(n=nPop(genlight_23123_SNPs))

genlight_23123_SNPs_pca <- glPca(genlight_23123_SNPs, nf=3)
genlight_23123_SNPs_pca_scores <- as.data.frame(genlight_23123_SNPs_pca$scores)

genlight_23123_SNPs_pca_scores$pop <- pop(genlight_23123_SNPs)
genlight_23123_SNPs_pca_scores


```


```{r}
set.seed(9)
p <- ggplot(genlight_23123_SNPs_pca_scores, aes(x=PC1, y=PC2, colour=pop))
p <- p + geom_point(size=2)
p <- p + scale_color_manual(values = cols) 
p <- p + geom_hline(yintercept = 0) 
p <- p + geom_vline(xintercept = 0) 
p <- p + theme_bw()
p



This was repeated for each depth and produced the following graphs

## 5x

![5x]({{ site.baseurl }}/images/5x_Depth_pop.pdf "5x")

## 10x

![10x]({{ site.baseurl }}/images/10x_Depth_pop.pdf "10x")

## 15x

![15x]({{ site.baseurl }}/images/15x_Depth_pop.pdf "15x")


## 20x

![20x]({{ site.baseurl }}/images/20x_Depth_pop.pdf "20x")

## 25x

![25x]({{ site.baseurl }}/images/25x_Depth_pop.pdf "25x")


## 30x

![30x]({{ site.baseurl }}/images/30x_Depth_pop.pdf "30x")


Those grphs were all colored based on where the sample was found (S=shallow, D=Deep)
I can also color based on the genotype that is assosiated with the symbiont 

## 10x colored by genotype

![10x]({{ site.baseurl }}/images/10x_Depth_genotype.pdf "10x")

## 30x colored by genotype

![30x]({{ site.baseurl }}/images/30x_Depth_genotype.pdf "30x")

This shows an extremely evident segregation between populations with the shallow genotype from populations with the deep genotyoe 