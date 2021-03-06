---
layout: post
title: "Rough Draft #1 - Discussion"
categories: 
tags: 
---


# Writing out the discussion so far

## Outline


* Easy to see different populations, possibly different species
* how each method was useful
   * focus more on how each result connects and shows similar results

* Symbionts are critical parts to the reef ecosystem
* Symbionts and Brevolium are still being classified
* How this fits into the broader tree
* If Eunicea flexuosa has two species of symbiont present in two separate populations, could this mean that there are other corals that have separated populations that also have multiple symbionts?
   * how many coral species vs symbiont species identified
* Brevolium is cited as found in shallow water (Lewis), is the population from deeper water considered deeper than normal? could this be a new finding about brevolium?
* In the Environment column of the mapping file some of each population were labeled from being in the opposite environment, were they mixed?
   * If two corals living next to each other have different species of symbiont what does that signify/lead to?
   * What implications on reef diversity does this have?
   * Would this increase or decrease coral survivability?
       * more diversity = more likely some survive a stressful event
* How are symbionts passed on for Eunicea?
   * parents or environment? (horizontal or vertical)?
      * Answer: Eunicia aquires it Horizontally (from the environment)
* Does this symbiont assosiate with any other corals?
   * Is it capable of assosiating with other corals?

# Discussion

The results from this experiment suggest that the two populations of brevolium found at seperate depths within Eunicea flexuosa are distinct species. While occupying the same species of coral. The difference between the two populations is extremely clear with no outliers, and this has led us to consider that these two populations may be two different species. The lineage and diversity of the Brevolium genus is not well described, so the discovery of the separation between two species that occupy the same coral host could lead to some important conclusions.

**SNP counts**
The basis of this analysis was done with population genomics through the use of SNPs. SNPs are single nucleotide variations in a genome of an individual. These SNPs can be very helpful in determining the composition of a population. Individuals within a single population will have many of the same SNPs since they are passed on through generations. Over time as populations become distinct more SNPs will become indicative of each population making the divide between populations clearer. Using programs, populations can be mapped based upon their SNPs. This experiment used the programs, Principal Component Analysis (PCAs), Bayescan, PCAdapt, and Admixture to observe how the populations were segregated. All of these outputted results that were clear and pointed to a very defined difference in population that also gives evidence that these are in fact cryptic species of Brevolium.
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





