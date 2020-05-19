---
layout: post
title: "Making Graphs of Depths"
categories: 
tags: 
---

##


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

This was repeated for each depth and produced the following graphs

## 5x

![5x]({{ site.baseurl }}/images/5x_Depth.pdf "5x")