---
layout: post
title: "Poster"
categories: 
tags: 
---

# Below are resources to use while viewing my poster

## The full poster


![Poster]({{ site.baseurl }}/images/Myles_Wagner_JPEG.jpg "Poster")


# Introduction

* Corals have a symbiotic relationship with dinoflagellate algae within their cells.​
* Corals and their symbiont can be dispersed over great distances, but organisms that live at different depths experience different conditions. ​
* We used extensive genomic tools to undestand  the major physiological differences between two symbiont species that are specialized to live in different habitats that are as close as 200 meters.​
* It is well documented that there are at least six genera of symbionts associated with coral (Lajunesse 2018).​
* A study found evidence that suggested a population of the genus Brevolium differed genetically across a depth gradient​
* Few studies have used transcriptome data to classify Symbiodincidae genuses 
* It is unknown what mechanisms are selected for between populations segregated by depth


# Methods

* Transcriptome Data was taken from symbionts​
* SNP data was used to run PCAs and Admixture​
* Phylogenetic tree made using 28S genetic marker including each Symbiodincidae genus​
* Go enrichment analysis of genes associated with Biological processes between the two populations​


# Results

**Figure 1**

![Brevolium]({{ site.baseurl }}/images/Symbiodiniaceae_Tree_With_Brevolium.png "Brevolium Tree")

Figure 1. This is a 1000 bootstrap RAxML phylogenetic tree built using Geneious using the 28s molecular marker. Four samples from the deep population (orange) and Four from the Shallow species (green) were compared to each type species of the seven described Symbiodiniaceae genera, as well as each described Brevolium species (blue).​

 
[Use this link to see a more detailed description of the methods used to create the phylogenetic tree.]({{ site.baseurl }}{% post_url 2020-7-14-Phylogenetic_tree %})

**Figure 2**

![Enrichment]({{ site.baseurl }}/images/GO_d2s_BP.png "Enrichment analysis")

Figure 2.  Gene Ontology enrichment analysis of the genes controlling biological processes that are under selection. The font indicates the level of significance. Blue indicates up regulated and red indicates down regulated genes.​

[Use this link to see a more detailed description of the methods used to create the Enrichment analysis tree.]({{ site.baseurl }}{% post_url 2020-7-07-GO_Enrichment %})


### Distance tree
![DistnceTree]({{ site.baseurl }}/images/DistanceTree_noNA.pdf "Distance Tree")

**Figure 3**. Phylogenetic analysis of two populations of Brevolium From the Carribean. The populations are physically separated by a depth kline. Genetically they are separated by a distance of approximately .3 or 30% genetic variance. The orange group is the shallower group and the green group is the deeper group.


### PCA

|**(A)**|**(B)**|
|![PCA]({{ site.baseurl }}/images/10x_PCA_noNA.pdf "PCA") | ![Eigenvalues]({{ site.baseurl }}/images/PCA_Eigenvalues_noNA.pdf "Eigenvalues") |

**Figure 4**. **(A)**Principal Component Analysis using PCA1 and PCA2. The two populations are segregated by PCA1. **(B)** The Eigenvalues showing the amount of variance described by each PCA. PCA1 describes most of the variance

### K2 Admixture

![K2]({{ site.baseurl }}/images/Admixture_K2_plot.jpg "Admixture K2 plot")

**Figure 5** An Admixture plot showing the K = 2 values. Assuming that there are two populations.

[Use this link to see a more detailed description of the methods used to create the three above graphs.]({{ site.baseurl }}{% post_url 2020-5-26-DAPC %})


# Discussion

As seen in the PCR graphs there is a very clear genetic difference between the two symbiont populations. Enough difference to classify the populations as different species (30%), could even be enough to consider them indifferent geneses.​
Transcriptome data was unused prior – allows for more accurate identification as well as identification of the genes under selection. Becoming more common in identification studies in other animals.​
Genes that encode for metabolism and photosynthesis were found to be under selection.​
Identifying and understanding the differences in symbionts can help better inform conservation efforts.​

​

# Conclusion

* The Family of Simbiodinacidea is not yet fully taxinomically understood
* Two corals from the same species can have two different species of symbiont within them 
* Genes that control photosynthesis are upregulated in deep corals.



## Further Research

Taxonomically identify the shallow species seen in this research, and use transcriptome data to identify more symbiont species, and use it to identify how they differ in mechanisms related to photosynthesis.​
​


### Acknowledgements
​
I would like to thank my mentors Dr. Carlos Prada and Matias Gomez for being so supportive and making this project possible. A huge thank you to everyone who worked hard to put together this Coastal Fellows program despite the challanging circumstances we faced this summer. It is people like that who give students like myself the opportunity to follow our passion in science and begin our careers as scientists.​
The Coastal Fellows Program is supported by the URI Offices of the President and Provost and the College of Environment and Life Sciences.


### Literature Cited

Prada, Carlos. et al.  2014. “Cryptic Diversity Hides Host and Habitat Specialization in a Gorgonian-Algal Symbiosis.” Molecular Ecology 23, 3330-3340.​

​
LaJeunesse, Todd C. et al. 2018. “Systematic Revision of Symbiodiniaceae Highlights the Antiquity and Diversity of Coral Endosymbionts.” Current Biology 28, 1-11​

​
Wright, R. M., Aglyamova, G. V., Meyer, E. and Matz, M. V. Gene expression associated with white syndromes in a reef-building coral, Acropora hyacinthus. BMC Genomics 2015, 16: 371.