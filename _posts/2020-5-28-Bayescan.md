---
layout: post
title: "Bayescan"
categories: 
tags: 
---

# Continuing work with Bayescan



## The Same steps were performed but the data was split into two populations instead of one

### Rewrote BSsnp.spid

in the BSsnp file this code was added:  VCF_PARSER_POP_FILE_QUESTION=./popmap.txt

### a new bayescan file was written
java -jar PGDSpider_2.1.1.5/PGDSpider2-cli.jar -inputfile brevolium_snps_biallelic_10x_miss50.recode.vcf -outputfile brevolium_snps_biallelic_10x_miss50_pop.bayescan -spid BSsnp.spid

### The analysis was run using the HPC bluewaves 
```
#!/bin/bash
#SBATCH -t 72:00:00
#SBATCH --nodes=1 --ntasks-per-node=20
#SBATCH --mail-type=BEGIN  --mail-user=myles_wagner@my.uri.edu
#SBATCH --mail-type=END  --mail-user=myles_wagner@my.uri.edu
#SBATCH --mail-type=FAIL  --mail-user=myles_wagner@my.uri.edu
cd $SLURM_SUBMIT_DIR
module load BayeScan/2.1-foss-2016b 
bayescan_2.1 brevolium_snps_biallelic_5x.bayescan -o brevolium_snps_biallelic_5x.bayescan.out put -n 5000 -thin 10 -nbp 20 -pilot 5000 -burn 50000 -pr_odds 100 -threads 20
```

Job ID: 1226871
Cluster: bluewaves
User/Group: myles_wagner/pradalab
State: COMPLETED (exit code 0)
Nodes: 1
Cores per node: 20
CPU Utilized: 1-04:37:02
CPU Efficiency: 30.89% of 3-20:38:00 core-walltime
Job Wall-clock time: 04:37:54
Memory Utilized: 23.74 MB
Memory Efficiency: 0.02% of 128.00 GB


## SNPs under selection
```
> BayeScan_Results_pop$outliers
integer(0)
> BayeScan_Results_pop$nb_outliers
[1] 0
```
Since both of these values came out as 0 it suggests that there are no SNPs under selection

# Graphs

![Bayescanlog10]({{ site.baseurl }}/images/Bayescan_pop_log10.pdf "Bayescan")


![Bayescanalpha]({{ site.baseurl }}/images/Bayescan_pop_alpha.pdf "Bayescan pop alpha")


![Bayescanalpha]({{ site.baseurl }}/images/Bayescan_pop_Fst1.pdf "Bayescan pop Fst1")


![BayescanLogL]({{ site.baseurl }}/images/Bayescan_pop_logL.pdf "Bayescan pop LogL")





# Repeated with less filtered file
since no resluts were being shown after using the vcf file that was filtered with 10x depth and a few other filters, a file with minimal filtering was tried 

#######Not Done Yet###########

#repeated with an even less filtered file (5x depth only) 

vcftools --gzvcf  brevolium_snps_biallelic.recode.vcf --min-meanDP 5 --recode --recode-INFO-all --out brevolium_snps_biallelic_5x


java -jar PGDSpider_2.1.1.5/PGDSpider2-cli.jar -inputfile brevolium_snps_biallelic_5x.recode.vcf -outputfile brevolium_snps_biallelic_5x.bayescan -spid BSsnp.spid


### nano bayescan.sh
```
#!/bin/bash
#SBATCH -t 72:00:00
#SBATCH --nodes=1 --ntasks-per-node=20
#SBATCH --mail-type=BEGIN  --mail-user=myles_wagner@my.uri.edu
#SBATCH --mail-type=END  --mail-user=myles_wagner@my.uri.edu
#SBATCH --mail-type=FAIL  --mail-user=myles_wagner@my.uri.edu
cd $SLURM_SUBMIT_DIR
module load BayeScan/2.1-foss-2016b 
bayescan_2.1 brevolium_snps_biallelic_5x.bayescan -o brevolium_snps_biallelic_5x.bayescan.out put -n 5000 -thin 10 -nbp 20 -pilot 5000 -burn 50000 -pr_odds 100 -threads 20
```

### sbatch bayescan.sh


