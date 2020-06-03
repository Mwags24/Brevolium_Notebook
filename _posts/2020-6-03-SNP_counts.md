---
layout: post
title: "table with snp counts"
categories: 
tags: 
---

# the number of snps for each filtering step




|**File**|**Filter applied**|**Number of  SNPs**|
|brevolium_snps_biallelic.recode.vcf | -min-meanDP 10 |kept 347031 out of a possible 1415812 Sites|
| brevolium_snps_biallelic_10x.recode.vcf | –max-missing 0.5 –minQ 30 | 48145 out of a possible 347031 Sites |
|brevolium_snps_biallelic_10x_miss50.recode.vcf | –maf 0.01 | 30795 out of a possible 48145 Sites |
| brevolium_snps_biallelic_10x_miss50_maf01.recode.vcf | –thin 1000 | kept 7877 out of a possible 30795 Sites |
| brevolium_snps_biallelic_10x_miss50_maf01_thin1000.recode.vcf | perl filter_hwe_by_pop.pl | Kept 7043 of a possible 7877 loci |



# final file:

|brevolium_snps_biallelic_10x_miss50_maf01_thin1000_HWEpop.recode.vcf| 7043 sites|