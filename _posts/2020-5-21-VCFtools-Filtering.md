---
layout: post
title: "Using VCF tools"
categories: 
tags: 
---

# Further Filtering the vcf file

## The filtering steps that have already been run 
### max-missing, mac, minQ
module load VCFtools/0.1.16-foss-2019a-Perl-5.28.1

vcftools --gzvcf brevolium_snps_biallelic.recode.vcf --max-missing 0.5 --mac 3 --minQ 30 --recode --recode-INFO-all --out brevolium_snps_biallelic_mac3_miss50

After filtering, kept 47 out of 47 Individuals
Outputting VCF file...
After filtering, kept 163858 out of a possible 1415812 Sites
Run Time = 142.00 seconds


## --Maf 0.05

Minor allele frequency is 

vcftools --gzvcf brevolium_snps_biallelic.recode.vcf --max-missing 0.5 --mac 3 --minQ 30 --maf 0.05 --recode --recode-INFO-all --out brevolium_snps_biallelic_mac3_miss50_maf05

After filtering, kept 47 out of 47 Individuals
Outputting VCF file...
After filtering, kept 150511 out of a possible 1415812 Sites
Run Time = 311.00 seconds


## hwe 0.05

Hardey Wineburg

vcftools --gzvcf brevolium_snps_biallelic.recode.vcf --max-missing 0.5 --mac 3 --minQ 30 --maf 0.05 --hwe 0.05 --recode --recode-INFO-all --out brevolium_snps_biallelic_mac3_miss50_maf05_hwe05

After filtering, kept 47 out of 47 Individuals
Outputting VCF file...
After filtering, kept 33231 out of a possible 1415812 Sites
Run Time = 30.00 seconds


## --thin 1000

vcftools --gzvcf brevolium_snps_biallelic.recode.vcf --max-missing 0.5 --mac 3 --minQ 30 --maf 0.05 --hwe 0.05 --thin 1000 --recode --recode-INFO-all --out brevolium_snps_biallelic_mac3_miss50_maf05_hwe05_thin1000

After filtering, kept 47 out of 47 Individuals
Outputting VCF file...
After filtering, kept 9955 out of a possible 1415812 Sites
Run Time = 22.00 seconds


# using new vcf to make graphs

## 10x depth

vcftools --gzvcf  brevolium_snps_biallelic_mac3_miss50_maf05_hwe05_thin1000.recode.vcf --min-meanDP 10 --recode --recode-INFO-all --out brevolium_snps_biallelic_mac3_miss50_maf05_hwe05_thin1000_10x

After filtering, kept 47 out of 47 Individuals
Outputting VCF file...
After filtering, kept 1004 out of a possible 9955 Sites
Run Time = 22.00 secondsv


myles_wagner@bluewaves.uri.edu:/data/pradalab/Brevolium_depth/vcf_files/brevolium_snps_biallelic_mac3_miss50_maf05_hwe05_thin1000_10x.recode.vcf /Users/myles/Desktop/brevolium


# Making the PCA graphs


![10xfiltered]({{ site.baseurl }}/images/10x_Depth_pop_filtered "10x PCA after filtering")

![10xfiltered]({{ site.baseurl }}/images/10x_Depth_genotype_filtered "10x PCA after filtering")

### Compare to the graph that has not been as filtered 

![10x]({{ site.baseurl }}/images/10x_Depth_genotype "10x PCA")