---
layout: post
title: "FST calculation"
categories: 
tags: 
---



## Calculating FST in bash

    vcftools --vcf brevolium_snps_biallelic_10x_miss50_maf01_thin1000_HWEpop.recode.vcf --weir-fst-pop Mappingfile_popS.txt --weir-fst-pop Mappingfile_popD.txt --out pop1_vs_pop2


After filtering, kept 45 out of 47 Individuals
Outputting Weir and Cockerham Fst estimates.
Fst: Only using diploid sites.
Weir and Cockerham mean Fst estimate: **0.40116**
Weir and Cockerham weighted Fst estimate: 0.8228

A FST value of .4 is a very significant level

in other descriptions, a fst value of .15 is a clear seperation in population, and a fst value of .3 has been used to differentiate two species. 

for two Brevolium species that are very close in proximity to each other a fst value of .4 seems like  clear indication that the two populations are indeed two seperate species