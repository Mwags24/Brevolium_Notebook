---
layout: post
title: "Using VCF tools"
categories: 
tags: 
---

Using the VCF tools option in Linux The data files can be filtered through


# First the VCFtools program needs to be loaded in
module load VCFtools/0.1.16-foss-2019a-Perl-5.28.1

## Using the --depth function
This creates a file containing the mean depth per individule
    vcftools --vcf brevolium_raw.vcf --out brevolium_raw --depth
the output file has the suffix '.idepth'

### Expected outcome
    cat brevolium_raw.idepth

INDV	N_SITES	MEAN_DEPTH
S90	1326660	14.1327
S80	1098888	6.79234
S71	1343853	11.3103
S65	1331395	11.7045
S62	1304419	9.2436
S87	1281493	9.8145
S56	1325419	11.1403
S52	1337691	12.1971
S35	835561	8.16803
S40	1325628	9.77757
S25	928928	11.2846
S19	1346640	12.1804
S14	585957	3.54756
S13	1375005	11.9268
S12	1455930	14.9953
S89	1463627	19.5856
S22	1270094	9.32603
S07	1300064	10.9489
D24	962399	12.964
D38	1527047	21.362
D87	1515347	23.2589
D18	1509404	19.2986
S75	1338863	12.4316
D03	1404264	15.6164
S21	548330	3.04315
D08	1188787	14.3086
D19	1040351	15.7893
D13	1580221	31.4833
D29	1481881	17.8994
D56	1312759	13.3561
D01	1522299	23.3388
D14	1491556	19.1482
S53	1282118	9.28263
D70	955310	7.94261
D20	1404956	19.5861
D52	1326282	9.67281
D58	1522385	22.0112
S03	1709011	198.949
D68	1493371	21.2695
S86	870281	6.70721
S20	838024	10.363
D60	1550237	24.8184
D64	1300547	17.876
D62	1469438	21.0366
D74	1543555	26.2155
D78	1361722	14.4019
D80	1382187	14.0585

## Using the --missing-indv tool
this creates a file that reports the missingness on a per-individule basis
    vcftools --vcf brevolium_raw.vcf --out brevolium_raw --missing-indv

the output file has the suffix '.imiss'
    cat brevolium_raw.imiss 
### Expected outcome
INDV	N_DATA	N_GENOTYPES_FILTERED	N_MISS	F_MISS
S90	1715603	0	388943	0.226709
S80	1715603	0	616715	0.359474
S71	1715603	0	371750	0.216688
S65	1715603	0	384208	0.223949
S62	1715603	0	411184	0.239673
S87	1715603	0	434110	0.253036
S56	1715603	0	390184	0.227433
S52	1715603	0	377912	0.220279
S35	1715603	0	880042	0.512964
S40	1715603	0	389975	0.227311
S25	1715603	0	786675	0.458541
S19	1715603	0	368963	0.215063
S14	1715603	0	1129646	0.658454
S13	1715603	0	340598	0.19853
S12	1715603	0	259673	0.15136
S89	1715603	0	251976	0.146873
S22	1715603	0	445509	0.259681
S07	1715603	0	415539	0.242212
D24	1715603	0	753204	0.439032
D38	1715603	0	188556	0.109907
D87	1715603	0	200256	0.116726
D18	1715603	0	206199	0.12019
S75	1715603	0	376740	0.219596
D03	1715603	0	311339	0.181475
S21	1715603	0	1167273	0.680386
D08	1715603	0	526816	0.307073
D19	1715603	0	675252	0.393595
D13	1715603	0	135382	0.0789122
D29	1715603	0	233722	0.136233
D56	1715603	0	402844	0.234812
D01	1715603	0	193304	0.112674
D14	1715603	0	224047	0.130594
S53	1715603	0	433485	0.252672
D70	1715603	0	760293	0.443164
D20	1715603	0	310647	0.181072
D52	1715603	0	389321	0.22693
D58	1715603	0	193218	0.112624
S03	1715603	0	6592	0.00384238
D68	1715603	0	222232	0.129536
S86	1715603	0	845322	0.492726
S20	1715603	0	877579	0.511528
D60	1715603	0	165366	0.0963894
D64	1715603	0	415056	0.24193
D62	1715603	0	246165	0.143486
D74	1715603	0	172048	0.100284
D78	1715603	0	353881	0.206272
D80	1715603	0	333416	0.194343


# Using --remove-indels and --recode 
## --remove-indels
this command will remove sites that contain variants that alter the length og the REF allele.

## --recode and --recode-INFO-all
this command will make the output include all the information from the original raw vcf file

    vcftools --vcf brevolium_raw.vcf --remove-indels --recode --recode-INFO-all --out brevolium_snps 


## Filtering by depth from the recoded vcf

    vcftools --vcf brevolium_raw.vcf --depth  --recode-INFO-all --out brevolium_raw 


    vcftools --vcf brevolium_snps.recode.vcf --out brevolium_snps --depth
### Expected output
    cat brevolium_snps.idepth
INDV	N_SITES	MEAN_DEPTH
S90	1133976	14.2425
S80	942191	6.83384
S71	1148132	11.2811
S65	1138082	11.7504
S62	1115387	9.23265
S87	1096416	9.8425
S56	1133255	11.1623
S52	1143007	12.2825
S35	717060	8.19819
S40	1134517	9.83357
S25	796781	11.3328
S19	1151583	12.1698
S14	503732	3.53866
S13	1174662	12.0501
S12	1242094	15.2034
S89	1247673	19.4987
S22	1086754	9.42089
S07	1111841	11.0829
D24	825762	12.5644
D38	1299579	21.6364
D87	1290298	23.5052
D18	1286467	19.6337
S75	1144263	12.4544
D03	1198911	15.8576
S21	471458	3.0269
D08	1017371	14.2641
D19	891593	15.8124
D13	1342399	32.1329
D29	1263645	18.2468
D56	1121897	13.3069
D01	1296391	23.8613
D14	1271514	19.4801
S53	1096521	9.29517
D70	818926	7.70023
D20	1198580	19.7758
D52	1133730	9.75016
D58	1296116	22.2331
S03	1438073	203.357
D68	1272300	21.4061
S86	746337	6.50517
S20	718746	10.1651
D60	1318519	25.0201
D64	1111569	17.9427
D62	1252891	21.3118
D74	1312982	26.2506
D78	1162190	14.4348
D80	1180084	14.1188

## Filtering the missing individules from the recoded vcf
    vcftools --vcf brevolium_snps.recode.vcf --out brevolium_snps --missing-indv

    cat brevolium_snps.imiss
### Expected output
INDV	N_DATA	N_GENOTYPES_FILTERED	N_MISS	F_MISS
S90	1441692	0	307716	0.213441
S80	1441692	0	499501	0.346469
S71	1441692	0	293560	0.203622
S65	1441692	0	303610	0.210593
S62	1441692	0	326305	0.226335
S87	1441692	0	345276	0.239494
S56	1441692	0	308437	0.213941
S52	1441692	0	298685	0.207177
S35	1441692	0	724632	0.502626
S40	1441692	0	307175	0.213066
S25	1441692	0	644911	0.447329
S19	1441692	0	290109	0.201228
S14	1441692	0	937960	0.650597
S13	1441692	0	267030	0.18522
S12	1441692	0	199598	0.138447
S89	1441692	0	194019	0.134577
S22	1441692	0	354938	0.246195
S07	1441692	0	329851	0.228794
D24	1441692	0	615930	0.427227
D38	1441692	0	142113	0.0985738
D87	1441692	0	151394	0.105011
D18	1441692	0	155225	0.107669
S75	1441692	0	297429	0.206306
D03	1441692	0	242781	0.1684
S21	1441692	0	970234	0.672983
D08	1441692	0	424321	0.294322
D19	1441692	0	550099	0.381565
D13	1441692	0	99293	0.0688725
D29	1441692	0	178047	0.123499
D56	1441692	0	319795	0.221819
D01	1441692	0	145301	0.100785
D14	1441692	0	170178	0.11804
S53	1441692	0	345171	0.239421
D70	1441692	0	622766	0.431969
D20	1441692	0	243112	0.16863
D52	1441692	0	307962	0.213612
D58	1441692	0	145576	0.100976
S03	1441692	0	3619	0.00251024
D68	1441692	0	169392	0.117495
S86	1441692	0	695355	0.482319
S20	1441692	0	722946	0.501457
D60	1441692	0	123173	0.0854364
D64	1441692	0	330123	0.228983
D62	1441692	0	188801	0.130958
D74	1441692	0	128710	0.089277
D78	1441692	0	279502	0.193871
D80	1441692	0	261608	0.181459

## Using --min/max-alleles
this code keeps SNPs with a certain amount of alleles. in this case it is filtered for only bi-allelic SNPs
    vcftools --vcf brevolium_snps.recode.vcf --min-alleles 2 --max-alleles 2 --recode --recode-INFO-all --out brevolium_snps_biallelic


# Using --max-missing, --mac, and --minQ
## --max-missing 
this code filters for variants that that have a certain percentage of individules that have been succsessfully genotyped. 
in this case we filter for 50% (--max-missing 0.5)

takes out anything with over 50% missing information

## --mac
filters for a minimum minor allele count 
in this case we filter for a minor allele count of 3 (--mac 3)
Makes sure that it is homozygeous (2) or heterozygous 
## --minQ
this code dilters for a minimum quality score
in this case we filer for a quality of 30 and up (--minQ 30)

    vcftools --gzvcf brevolium_snps_biallelic.recode.vcf --max-missing 0.5 --mac 3 --minQ 30 --recode --recode-INFO-all --out brevolium_snps_biallelic_mac3_miss50

# Trying different minimum depths 

## 10x
    vcftools --gzvcf  brevolium_snps_biallelic_mac3_miss50.recode.vcf --min-meanDP 10 --recode --recode-INFO-all --out brevolium_snps_biallelic_mac3_miss50_10x

after creating the file with 10x depth I will make plots in R using ggplot2


# (5/22/20) I went back in and refiltered

## started with Depth filter of 10x
vcftools --gzvcf  brevolium_snps_biallelic.recode.vcf --min-meanDP 10 --recode --recode-INFO-all --out brevolium_snps_biallelic_10x
    After filtering, kept 347031 out of a possible 1415812 Sites

## Applying --max-missing, --minQ, and exclusing --mac

vcftools --gzvcf brevolium_snps_biallelic_10x.recode.vcf --max-missing 0.5 --minQ 30 --recode --recode-INFO-all --out brevolium_snps_biallelic_10x_mac3_miss50
    kept 48145 out of a possible 347031 Sites

## --maf 0.01

vcftools --gzvcf brevolium_snps_biallelic_10x_mac3_miss50.recode.vcf --maf 0.01 --recode --recode-INFO-all --out brevolium_snps_biallelic_10x_mac3_miss50_maf01
    After filtering, kept 30795 out of a possible 48145 Sites


## --thin 1000

vcftools --gzvcf brevolium_snps_biallelic_10x_mac3_miss50_maf01.recode.vcf --thin 1000 --recode --recode-INFO-all --out brevolium_snps_biallelic_10x_mac3_miss50_maf01_thin1000
    After filtering, kept 7877 out of a possible 30795 Sites
