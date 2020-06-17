---
layout: post
title: "Rough Draft #1"
categories: 
tags: 
---

# Up to date Full first draft


# Abstract

Corals rely on a symbiotic dinoflagellate for much of the coral's energy needs. Until recently these symbionts were all classified under the genus symbiodinium. However as Genetic and Phylogenetic analysis became more readily used it was shown that the symbionts are not just a single genus but a wide variety of genetically different groups. Brevolium is one of these symbiont groups. The brevolium group can be found in Eunicea flexuosa, a soft octocoral in the Caribbean that has a wider variety of habitable environments, specifically different populations of this coral can be found at varying depths. In this study the Brevolium within Eunicea flexuosa are tested using a genome wide association study to determine how these populations of symbionts differ from each other. Genome wide association tests have not been performed on sister Symbiodiniaceae species. The results point to the conclusion that these two populations of symbiont are in fact genetically separate. An FST value of .4, a PCA analysis, and Distance tree all place these two populations as separate species segregated by depth. Using PCAdapt to determine the SNPs under selection allowed us to see that the genes that differ between the two populations are the genes related to (hopefully something good). This showed that the symbionts are able to adapt to different (Maybe light levels). Recognizing and identifying specific species of Brevolium that have different sets of adaptations will be an important part of conservation. The genome wide data analysis was extremely clear suggesting this type of analysis has the power to identify cryptic species of closely related Symbiodiniaceae species.

# Introduction

Corals around the world have established endosymbiotic relationships with dinoflagellates. Corals require the energy produced by the algae through photosynthesis. The symbiotic algae benefits from the relationship by having a constant light source and receiving recycled inorganic nutrients. This endosymbiotic pair are reef builders and provide a home for countless marine species. There are many varieties of corals, the two main groups include hard and soft corals (explanation). The knowledge of how many species of coral is well documented, however the symbiont family tree is far from being fully established.
Until just recently these symbionts were classified under a single genus called Symbiodinium. However, as we further study this symbiont it is more clear how diverse this group of organisms are. The genus Symbiodinium has been split into many genera (Cladocopium, Brevolium, Fugacium, Durusdinium, Greakladium, Effrenium, Symbiodinium) (LaJeunesse 2018). The species within these genera are not yet fully established.

The soft coral *Eunicea flexuosa* is commonly associated with the *Brevolium* family of symbiont. *E. flexuosa* is an octocoral from the family Plexauridae. It is a broadcast spawner and acquires its symbiont horizontally from the environment. This allows for the coral to have different symbionts between generations.This horizontal acquisition means that while the corals may spread beyond its native home, the symbiont will not spread between ecosystems as easily, being limited to transfer through the water column or by proximity with another coral. Symbionts therefore have become more adapted to the populations they originate from, adapting to the depth, light levels, and pressure of its environment. Only recently have we recognized the wide variety of morphological, physiological, genetic and physical characteristics within these symbionts.
Brevolium has been shown to be a diverse genus with species spread across the Caribbean (Lewis 2018). as Lewis said these putative species still need further testing. There are still many species being discovered. Identifying not only unique species but also the unique traits of the different species. Understanding the specific environmental conditions symbiont species are able to survive in will be a crucial component of future conservation of coral reefs. 

Here, we use a population genetics approach to determine the genetic difference between populations of Brevolium. Using Genome wide analysis of SNPs we determine the distance between populations genetically. Prior studies have observed a diversity of Symbiodiniaceae greater than currently cataloged, however this will be one of the first to use genome wide association. 
Using the Single Nucleotide Polymorphisms (SNPs) we are also able to study which genes might be responsible for the difference in populations of Brevolium. Programs like Bayescan and PCAdapt can be used to find SNPs under selection. Looking at what genes the SNPs under selection are located on can help determine what traits may be the source of selection between the populations. 
Understanding the differences between Brevolium species, and symbiont species in general is becoming increasingly important as conservation efforts try to find possible solutions for coral degradation as ocean temperatures rise. Knowing the symbionts that are best adapted for certain temperatures or depths can help select the best candidates for reseeding of reefs with corals.

**This is the first to analyze with genome-wide data a diversification process in two sister species of Symbiodiniaceae**


# Methods


Original sampling occurred in the Bahamas, Panama, Puerto Rico, and Curaçao  (Prada 2013). Eunicea flexuosa samples were taken at a shallow and a deep depth for each of the four sites. The depths of the coral from each site were recorded and used to separate them into two populations. The Brevolium within the coral was also genetically sequenced.
The genetic information was transitioned from BAM files to a vcf file using SNP calling. vcftools (vcftools reference) was used to filter these SNP files using the following tools. First a minimum depth of 10x was established. The tool --miss .50  filtered out any snp with over 50% missing information. The minimum allele count was set at .01 and the file was thinned using --thin 1000. 
Principal component analysis (PCA) was run on the filtered vcf file. Using vcfR (reference) the vcf file was combined with a mapping file continuing population information and turned into a genlight object. This genlight object was used to create a distance tree, PCA plot, Eigenvalues plot, DAPC, and compoplot.
A Hardy weinberg filter was applied using vcftools to further filter the data based on their populations.
Using Admixture 8 files with K values from 1 to 8 were generated and the file with the least cross-validation error was selected. Using this file and the mapping file barplots were created for each of the K values.
A Weir and Cockerham FST calculation was performed using vcftools.
Bayescan and PCAdapt analyses were performed in order to determine which SNPs were under selection and which were neutral SNPs. The SNPs under selection and the information on the chromosome and position they are found in were then exported. Each of the genes surrounding each SNP were run through BLAST on NCBI to determine what genes were under selection. 



# Results

## Figures

### Distance tree
![DistnceTree]({{ site.baseurl }}/images/DistanceTree_noNA.pdf "Distance Tree")

**Figure 1**. Phylogenetic analysis of two populations of Brevolium From the Carribean. The populations are physically separated by a depth kline. Genetically they are separated by a distance of approximately .3 or 30% genetic variance.



### PCA

|**(A)**|**(B)**|
|![PCA]({{ site.baseurl }}/images/10x_PCA_noNA.pdf "PCA") | ![Eigenvalues]({{ site.baseurl }}/images/PCA_Eigenvalues_noNA.pdf "Eigenvalues") |

**Figure 2**. **(A)**Principal Component Analysis using PCA1 and PCA2. The two populations are segregated by PCA1. **(B)** The Eigenvalues showing the amount of variance described by each PCA. PCA1 describes most of the variance

### K3 Admixture
![K3]({{ site.baseurl }}/images/Admixture_K3_plot.pdf "Admixture K3 plot")

**Figure 3** An Admixture plot showing the K = 3 values. Assuming that there are three populations.


FST value was 0.40116

* NCBI tree rooting our population into larger tree
* Value Tables?
   * Filtering steps
   * Bayescan/PCAdapt


# Discussion

The results from this experiment suggest that the two populations of brevolium found at seperate depths within Eunicea flexuosa are distinct species. While occupying the same species of coral. The difference between the two populations is extremely clear with no outliers, and this has led us to consider that these two populations may be two different species. The lineage and diversity of the Brevolium genus is not well described, so the discovery of the separation between two species that occupy the same coral host could lead to some important conclusions. This study uses a promising analytical method that has not been considered in previous studies. 

**SNP counts**
The basis of this analysis was done with genome wide population genomics through the use of SNPs. SNPs are single nucleotide variations in a genome of an individual. These SNPs can be very helpful in determining the composition of a population. Individuals within a single population will have many of the same SNPs since they are passed on through generations. Over time as populations become distinct more SNPs will become indicative of each population making the divide between populations clearer. Using programs, populations can be mapped based upon their SNPs. This experiment used the programs, Principal Component Analysis (PCAs), Bayescan, PCAdapt, and Admixture to observe how the populations were segregated. All of these outputted results that were clear and pointed to a very defined difference in population that also gives evidence that these are in fact cryptic species of Brevolium.
In order to successfully analyse SNP data it needs to be filtered first. The Filtering steps that were used took the initial 1415812 SNPs and reduced it count down to 7043 (Table 1(of filtering steps)). The remaining SNPs only accounted for the well defined and clean SNPs. Each filtering step reduced the amount of SNPs without reducing the overall information found within. Once the SNPs were cleaned the programs that analysed could output clear non-messy information.

**PCA**
The Principle Component Analysis (PCA) showed the two populations segregated from each other (Figure 2a) and the Eigenvalues showed that almost all of the difference can be defined by PC1. When a PCA has a very high Eigenvalue for PC1 it means that it can be described by just that single analysis and therefore the difference between populations is clear. The PCAs were run at many different levels of filtering of the original SNPs. All PCAs showed the same population divide. There were two outliers that did not fall into either population.

**Admixture**
Admixture is a program that will create a compopolot that separates SNPs into different numbers of populations. This program outputted 8 possibilities ranging from one population to eight populations. each was given a value that indicates the likelihood that this model was accurate. The lowest, and therefore most accurate, model was the model indicating two populations. Figure 3 shows The model indicating three populations. The green bars in the center are signifying the two outliers seen before that do not fall into either population. The deep and shallow populations' bars are almost entirely solid colors indicating they have almost no crossover, and that it is very high certainty that they are separate.

**Bayescan and PCAdapt**
Both show the same conclusions as the PCAs. These programs help find SNPs that are under selection. The SNPs that are under selection should be associated with genes that make the Brevolium species better adapted to either the shallow or deep population. Bayescan is a stricter program and did not find SNPs under selection. However out of the 7877 SNPs used in the PCAdapt program 61 SNPs under selection were found.
SNPs under selection and Neutral SNPs both contribute to the genetic variation between populations since neutral SNPs are still passed on within populations. The SNPs under selection provide genes that change the fitness of an organism. Looking at what that gene codes for can give a lot of information on the difference between the populations. Since two different species of Symbiont are very difficult to separate by physical morphology, genetics provides the most telling distinction between species. Knowing the expression of the genes that are under selection gives us a tangible way of differentiating between two species.

**Distance Tree and NCBI**
Using the SNP data a distance tree was created that clearly shows the genetic difference between the populations. There is a genetic distance of about .3 which has been described in other research as similar to the difference between (Cats and dogs - placeholder example). This makes it clear that these populations should be considered separate populations. Using NCBI the tree was rooted into the larger brevolium genus and Symbiodinium family.
The genetic difference between these two populations of symbiont is far greater than the genetic difference between the two populations of E. flexuosa they are associated with.
**FST**
The FST value of 0.40116 is further evidence suggesting these two populations are indeed two separate species. In other studies a FST value ot .3 has been used to describe the difference between bird species (Lewis?).

**Genes from NCBI**
Using the SNP and genetic information from these corals we were able to identify which genes are most relevant to the separation of the shallow and deep population.

**Environmental implications**
Corals have been well classified and studied since their importance to the ocean's health is well recognized, however the organism that is essential to corals ability to survive has not been given the same attention. Now that we have recognized how diverse the symbionts that provide for corals are we need to grasp a full understanding of how they have evolved and adapted to their environments. Knowledge of how different species of symbionts are able to handle stress events could lead to much more informed conservation work that takes into consideration what species of symbiont is being used within transplanted coral.




# Conclusion

The two populations of Brevolium found within Eunicea flexuosa at different depths have been identified as likely candidates to be cryptic species based upon the population genomics used in this experiment. Further the genes that separate these populations have been identified to be associated with (placeholder). The evidence that there are two species of symbiont living in close proximity to each other within a single species of coral suggests that there could be a much higher magnitude of symbiont species that recently suggestested. This Study has also shown the effectiveness of genome wide analysis, a method previously untested.
