---
layout: post
title: "Rough Draft #1"
categories: 
tags: 
---

# Abstract, Methods, Figure discriptions

This is a first rough draft of a paper for this project. I have put bullet points in the sections that I have not written to make a list of things that still need to be added or will be included 

# Abstract
Corals rely on a symbiotic dinoflagellate for much of the coral's energy needs. Until recently these symbionts were all classified under the genus symbiodinium. However as Genetic and Phylogenetic analysis became more readily used it was shown that the symbionts are not just a single Genus but a wide variety of genetically different groups. Brevolium is one of these symbiont groups. The brevolium group can be found in Eunicea flexuosa, a soft octocoral in the Caribbean that has a wider variety of habitable environments, specifically different populations of this coral can be found at varying depths. In this study the Brevolium within Eunicea flexuosa are tested using various genetic and phylogenetic analysis to determine how these populations of symbionts differ from each other. The results point to the conclusion that these two populations of symbiont are in fact genetically separate. An FST value of .4, a PCA analysis, and Distance tree all place these two populations as separate species segregated by depth. Using PCAdapt to determine the SNPs under selection allowed us to see that the genes that differ between the two populations are the genes related to (hopefully something good). This showed that the symbionts are able to adapt to different (Maybe light levels). Recognizing and identifying specific species of Brevolium that have different sets of adaptations will be an important part of conservation. Knowing what symbiont will be best suited to different environments


# Intro

* Coral Symbiont Relationships
    * photosynthesis and light   
* Population genetics 
* Past Coral depth studies  
* How Symbionts are being classified more specifically 
    * Phylogenetics
    * PCA
    * SNPs
    * other methods that need background 
* Climate change and conservation efforts 

* The physical distribution of these symbionts has been studied, but it has not been looked at using SNPs and PCAs





# Methods


Original sampling occurred in the carribean (Prada (year)). Eunicea flexuosa was sampled at (number of sites) sites. The depths of the coral from each site were recorded and used to separate them into two populations. Further genetic sampling placed each coral in either the shallow population or the deep population. The symbiont within the coral was also genetically sequenced.
The information was transitioned to a vcf file and the number of SNPs were filtered using vcf tools (vcftools reference). First a minimum depth of 10x was established. The tool --miss .50  filtered out any snp with over 50% missing information. The minimum allele count was set at .01 and the file was thinned using --thin 1000. Using the thinned file graphs were made following the GBS tutorial. A minimum spanning network, PCA, DAPC, and Distance tree were made. The two populations were separated using their genetic info. A complot was made.
Bayescan and PCAdapt analyses were performed in order to determine which SNPs were under selection.
Hardy wineburg was performed to further filter the data based on their populations.
Using Admixture 8 files with K values from 1 to 8 were generated and the file with the least cross-validation error was selected. Using this file and the mapping file barplots were created

* NCBI used to determine the use of the genes




# Results
 

## Figures

### Distance tree
![DistnceTree]({{ site.baseurl }}/images/DistanceTree_noNA.pdf "Distance Tree")

**Figure 1**. Phylogenetic analysis of two populations of Brevolium From the Carribean. The populations are physically seperated by a depth kline. Genetically they are seperated by a distance of approximatly .3 or 30% genetic varience.



### PCA

|**(A)**|**(B)**|
|![PCA]({{ site.baseurl }}/images/10x_PCA_noNA.pdf "PCA") | ![Eigenvalues]({{ site.baseurl }}/images/PCA_Eigenvalues_noNA.pdf "Eigenvalues") |

**Figure 2**. **(A)**Principle Component Analysis using PCA1 and PCA2. The two populations are segreated by PCA1. **(B)** The Eigenvalues showing the amount of varience discribed by each PCA. PCA1 describes most of the varience

### K3 Admixture
![K3]({{ site.baseurl }}/images/Admixture_K3_plot.pdf "Admixture K3 plot")

**Figure 3** An Admixture plot showing the K = 3 values. Assuming that there are three populations. 




* NCBI tree rooting our poplation into larger tree
* Value Tables?
    * Filtering steps
    * FST value
    * Bayescan/PCAdapt 

 
# Discussion


* Easy to see different populations, possibly different species
* how each method was useful or unuseful
    * focs more on how each result connects and shows similar results 

* Symbionts are critical parts to the reef ecosystem 
* Symbionts and Brevolium are still being classified
* How this fits into the broader tree
* If Eunicea flexousa has two species of symbiont present in two seperate populations, could this mean that there are other corals that have sepereated populations that also have multiple symbionts? 
    * how many coral species vs symbiont species identified 
* Brevolium is cited as found in shallow water (Lewis), is the population from deeper water considered deeper than normal? could this be a new finding about brevolium?



# Conclusion

* These two species are likely different species
* The symbionts that live at Depth are different from the ones that live in shallower water
* Were the genetic differences between the corals segregated by depth similar to the amount of difference between symbiont?
* We do not have a clear enough genetic tree of the symbionts
    * There are likely many more undiscovered species
* possible that there are many more species of symbiont than coral
    * Further study, is this species of symbiont present in different corals but the same environment? 





This research is working off of research by Carlos that is similarly comparing symbiont species based on depth. The previous paper however still considered the symbiont to fall under the genus symbiodinium. this research is also using a population genomic approach coupled with phylogenetics/ the functional analysis of SNPs under selection to determine what traits may contribute to the difference in species. 