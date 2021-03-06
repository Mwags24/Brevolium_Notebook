---
layout: post
title: "Admixture"
categories: 
tags: 
---


# Creating P and Q Admixture files

## Transforming VCF to PLINK


### Making chrom_map file
bcftools view -H brevolium_snps_biallelic_10x_miss50_maf01_thin1000_HWEpop.recode.vcf | cut -f 1 | uniq | awk '{print $0"\t"$0}' > brevolium_snps_biallelic_10x_miss50_maf01_thin1000_HWEpop.chrom_map.txt

### Making .ped and .map files
vcftools --vcf brevolium_snps_biallelic_10x_miss50_maf01_thin1000_HWEpop.recode.vcf --plink --chrom-map brevolium_snps_biallelic_10x_miss50_maf01_thin1000_HWEpop.chrom_map.txt --out brevolium_snps_biallelic_10x_miss50_maf01_thin1000_HWEpop


### Recoding files into .ped files with new IDs
plink --file brevolium_snps_biallelic_10x_miss50_maf01_thin1000_HWEpop --update-ids updateID.txt --make-bed --out brevolium_snps_biallelic_10x_miss50_maf01_thin1000_HWEpop.newID


### Nano admixt_k8.sh

    cd $SLURM_SUBMIT_DIR
    ./admixture brevolium_snps_biallelic_10x_miss50_maf01_thin1000_HWEpop.newID.bed --cv=10 1
    ./admixture     brevolium_snps_biallelic_10x_miss50_maf01_thin1000_HWEpop.newID.bed --cv=10 2
    ./admixture     brevolium_snps_biallelic_10x_miss50_maf01_thin1000_HWEpop.newID.bed --cv=10 3
    ./admixture brevolium_snps_biallelic_10x_miss50_maf01_thin1000_HWEpop.newID.bed --cv=10 4
    ./admixture brevolium_snps_biallelic_10x_miss50_maf01_thin1000_HWEpop.newID.bed --cv=10 5
    ./admixture brevolium_snps_biallelic_10x_miss50_maf01_thin1000_HWEpop.newID.bed --cv=10 6
    ./admixture brevolium_snps_biallelic_10x_miss50_maf01_thin1000_HWEpop.newID.bed --cv=10 7
    ./admixture brevolium_snps_biallelic_10x_miss50_maf01_thin1000_HWEpop.newID.bed --cv=10 8
    for K in {1,2,3,4,5,6,7,8}; do ./admixture --cv=10 -j20 -B brevolium_snps_biallelic_10x_miss50_maf01_thin1000_HWEpop.newID.bed $K | tee log${K}.out; done

### finding lowest cross-validation error
awk '/CV/ {print $3,$4}' log*out | cut -c 4,7-20 > admixt_k8.cv.error

|K clusters|Cross-validation error|
|1 |0.74086|
|2 |0.33707|
|3 |0.40522|
|4 |0.40885|
|5 |0.41461|
|6 |0.42955|
|7 |0.48563|
|8 |0.45484|

number 2 has the least error at 0.33707


awk '{split($1,name,"."); print $1,name[2]}' brevolium_snps_biallelic_10x_miss50_maf01_thin1000_HWEpop.newID.nosex > admixt_k8.list




# R code to plot admixture results

wget https://github.com/speciationgenomics/scripts/raw/master/plotADMIXTURE.r