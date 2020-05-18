---
layout: post
title: "Playing with Depth"
categories: 
tags: 
---

##

After first filtering for a file that only kept variants that have been successfully genotyped in 50% of individuals, a minimum quality score of 30, and a minor allele count of 3.
the file brevolium_snps_biallelic_mac3_miss50.recode.vcf can be further filtered based on depth level.

# Depth is the mount of times the program reads through the file
depth is a tradeoff between the amount of data and the accuracy.
The higher the depth the more accurate it is, however the more SNPs that get filtered out because of lower Depth
I will be playing with different depth levels (5x, 10x, 15x, 20x, 25x, and 30x) to see which has the optimal amount of data vs accuracy.


# 10x
    first I tried with 10x
vcftools --gzvcf  brevolium_snps_biallelic_mac3_miss50.recode.vcf --min-meanDP 10 --recode --recode-INFO-all --out brevolium_snps_biallelic_mac3_miss50_10x

After filtering, kept 23123 out of a possible 163858 Sites


# 5x
vcftools --gzvcf  brevolium_snps_biallelic_mac3_miss50.recode.vcf --min-meanDP 5 --recode --recode-INFO-all --out brevolium_snps_biallelic_mac3_miss50_5x

After filtering, kept 58462 out of a possible 163858 Sites


# 15x
vcftools --gzvcf  brevolium_snps_biallelic_mac3_miss50.recode.vcf --min-meanDP 15 --recode --recode-INFO-all --out brevolium_snps_biallelic_mac3_miss50_15x

After filtering, kept 13240 out of a possible 163858 Sites


# 20x
vcftools --gzvcf  brevolium_snps_biallelic_mac3_miss50.recode.vcf --min-meanDP 20 --recode --recode-INFO-all --out brevolium_snps_biallelic_mac3_miss50_20x

After filtering, kept 9134 out of a possible 163858 Sites


# 25x
vcftools --gzvcf  brevolium_snps_biallelic_mac3_miss50.recode.vcf --min-meanDP 25 --recode --recode-INFO-all --out brevolium_snps_biallelic_mac3_miss50_25x

After filtering, kept 6743 out of a possible 163858 Sites


# 30x
vcftools --gzvcf  brevolium_snps_biallelic_mac3_miss50.recode.vcf --min-meanDP 30 --recode --recode-INFO-all --out brevolium_snps_biallelic_mac3_miss50_30x

After filtering, kept 5330 out of a possible 163858 Sites


