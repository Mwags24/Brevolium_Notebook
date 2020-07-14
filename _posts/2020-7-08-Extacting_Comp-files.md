---
layout: post
title: "Finding comp files"
categories: 
tags: 
---

# Using Bluewaves to pull out the needed files


## comp38000

{bash}
mkdir ../phylogenetics
cd ../phylogenetics

ln -s /data/pradalab/mgomez/brevolium/read_group/*bam .
ln -s /data/pradalab/mgomez/brevolium/read_group/*bai . 

nano comp38000_c0_seq1.sh


#!/bin/bash
#SBATCH -t 24:00:00
#SBATCH --nodes=1 --ntasks-per-node=1
#SBATCH --mail-type=BEGIN  --mail-user=myles_wagner@my.uri.edu
#SBATCH --mail-type=END  --mail-user=myles_wagner@my.uri.edu
#SBATCH --mail-type=FAIL  --mail-user=myles_wagner@my.uri.edu
cd $SLURM_SUBMIT_DIR
module load SAMtools/1.9-iccifort-2019.1.144-GCC-8.2.0-2.31.1
for file in /data/pradalab/Brevolium_depth/vcf_files/phylogenetics/*.bowtie2.bam_rmdup.bam_sorted.bam_RD.bam
  do samtools view -bh $file "comp38000_c0_seq1" >${file/bowtie2.bam_rmdup.bam_sorted.bam_RD.bam/}_comp38000_c0_seq1.bam
  done
ln -s /data/pradalab/mgomez/brevolium/read_group/*comp38000_c0_seq1.bam .

sbatch comp38000_c0_seq1.sh


## comp40829

nano comp40829_c0_seq1.sh


#!/bin/bash
#SBATCH -t 24:00:00
#SBATCH --nodes=1 --ntasks-per-node=1
#SBATCH --mail-type=BEGIN  --mail-user=myles_wagner@my.uri.edu
#SBATCH --mail-type=END  --mail-user=myles_wagner@my.uri.edu
#SBATCH --mail-type=FAIL  --mail-user=myles_wagner@my.uri.edu
cd $SLURM_SUBMIT_DIR
module load SAMtools/1.9-iccifort-2019.1.144-GCC-8.2.0-2.31.1
for file in /data/pradalab/mgomez/brevolium/read_group/*.bowtie2.bam_rmdup.bam_sorted.bam_RD.bam
  do samtools view -bh $file "comp40829_c0_seq1" >${file/bowtie2.bam_rmdup.bam_sorted.bam_RD.bam/}_comp40829_c0_seq1.bam
  done

  ln -s /data/pradalab/mgomez/brevolium/read_group/*comp40829_c0_seq1.bam .

sbatch comp40829_c0_seq1.sh