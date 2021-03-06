---
layout: post
title: "Phylogenetic Tree"
categories: 
tags: 
---

# Making a Phylogenetic tree with known symbiont species and our samples

These trees were made using RAxML with 1000 bootstraps

## First a base Sybiodinase tree was created

The 28s ribosomal subunit was used as the molecular marker and all of the sequences were pulled from NCBI from LaJunesse's paper 


## Base Tree
![Base]({{ site.baseurl }}/images/Base_Symbiodiniaceae_Tree.png "Base Tree")

This tree confirmed the tree shown in LaJunesse's paper.



## Adding the comp sequences

Both the comp38000 and comp40829 sequences were tested and used to make trees
However comp38000 turned out to not have long enough sequences and no good reads could be extracted.
Comp 40829 had long reads and the extractions were easy to utilize.

## creating FASTA files

Using the extracted comp40829 sequences four samples were seleced from the Deep group and the shallow group.

![Samples]({{ site.baseurl }}/images/Symbiodiniaceae_Tree_With_Samples.png "Samples Tree")



## Adding Brevolium

Our samples are expected to be Brevolium so I added all the described Brevolium species by LaJunesse to the tree.

![Brevolium]({{ site.baseurl }}/images/Symbiodiniaceae_Tree_With_Brevolium.png "Brevolium Tree")


# MrBayes Tree

A tree was then made using MrBayes with a 1,100,000 chain length


![MrBayes]({{ site.baseurl }}/images/MrBayes_Full_Tree.png "MrBayes Tree")
MrBayes_Full_Tree.png