---
layout: post
title: "Rough Draft"
categories: 
tags: 
---

# Abstract, Methods, Figure discriptions



# Abstract
Corals rely on a symbiotic dinoflagelate for much of the coral's energy needs. Until recently these symbionts were all classified under the genus symbiodinium. However as Genetic and Phylogenetic analysis became more readily used it was shown that the symbionts are not just a single Genus but a wide variety of genetically different groups. Brevolium is one of these symbiont groups. The brevolium group can be found in Enuicea flexosa a soft octocoral in the Caribean that have a wider variety of habital environments, specifically different populations of this coral can be found at varrying depths. In this study the Brevolium within Enuicea flexosa are tested using various genetic and phylogenetic analysis to determine how these populations of symbiont differ from each other. The results point to the conclusion that these two populations of symbiont are in fact genetically separate. An FST value of .4, a PCA analysis, and Distance tree all place these two populations as separate species segregated by depth. Using PCAdapt to determine the SNPs under selection allowed us to see that the genes that differ between the two populations are the genes related to (hopefully something good). This showed that the symbionts are able to adapt to different (Maybe light levels). Recognizing and identifying specific species of Brevolium that have different sets of adaptations will be an important part of conservation. Knowing what symbiont will be best suited to different environments 





# Methods


Original sampling occurred in the carribean (Prada 20__). Eunicea flexuosa was sampled at ____ sites. The depths of the coral from each site were recorded and used to separate them into two populations. Further genetic sampling placed each coral in either the shallow population or the deep population. The symbiont within the coral was also genetically sequenced.
The information was transitioned to a vcf file and the number of snps were filtered using vcf tools. First a minimum depth of 10x was established. The tool --miss .50  filtered out any snp with over 50% missing information. The minimum allele count was set at .01 and the file was thinned using --thin 1000. Using the thinned file graphs were made following the GBS tutorial. A minimum spanning network, PCA, DAPC,and Distance tree were made. The two populations were separated using their genetic info. A complot was made.
Bayescan and PCAdapt analysises were performed in order to deermine which SNPs were under selection. 
Hardy wineburg was performed to further filter the data based on their populations.
Using Admixture 8 files with K values from 1 to 8 were generated and the file with the least cross-validation error was selected. Using this file and the mapping file barplots were created 
NCBI used to determine the use of the genes









# Figures

### Distance tree
![DistnceTree]({{ site.baseurl }}/images/DistanceTree_noNA.pdf "Distance Tree")

**Figure 1**. Phylogenetic analysis of two populations of Brevolium From the Carribean. The populations are physically seperated by a depth kline. Genetically they are seperated by a distance of approximatly .3 or 30% genetic varience.



### PCA

|**(A)**|**(B)**|
|![PCA]({{ site.baseurl }}/images/10x_PCA_noNA.pdf "PCA") | ![Eigenvalues]({{ site.baseurl }}/images/PCA_Eigenvalues_noNA.pdf "Eigenvalues") |

**Figure 2**. **(A)**Principle Component Analysis using PCA1 and PCA2. The two populations are segreated by PCA1. **(B)** The Eigenvalues showing the amount of varience discribed by each PCA. PCA1 describes most of the varience

### K3 Admixture
![K3]({{ site.baseurl }}/images/Admixture_K3_plot.pdf "Admixture K3 plot")

**Figure 3** An Admixture plot using the K3 values. Assuming that there are three populations. 