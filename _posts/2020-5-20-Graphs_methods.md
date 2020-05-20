---
layout: post
title: "Making Graphs of Missing Info"
categories: 
tags: 
---

## Graphs Showing Missing Info 

Using the tables of Missing info found {add link here} A boxplot was created of all depths showing the outliers 

![Boxplot]({{ site.baseurl }}/images/Missing_info_boxplot.pdf "Boxplot of all Depths")

Any individule with over .2 missing info was labled

The next box plot only has individules at 10x depth
![Boxplot10x]({{ site.baseurl }}/images/Missing_info_boxplot_10x.pdf "Boxplot of 10x")


Next a bar graph was created that showed the average missing info over all depths of each individule 

![Bargraph]({{ site.baseurl }}/images/Missing_info_bargraph.pdf "Bargraph of all Depths")

This Bargraph was made again but only for individules at 10x depth

![Bargraph10x]({{ site.baseurl }}/images/Missing_info_bargraph_10x.pdf "Bargraph of 10x")

The individules with over .1 missing info were labeled 


In order to better see the Individules this graph was flipped on its side and ordered

![Bargraph10xordered]({{ site.baseurl }}/images/Missing_info_bargraph_ordered.pdf "Bargraph of 10x")



# Methods so far

## List version

* Data was collected by Carlos Prada
* Data was retreived from the HPC
* A copy was created 
* Using VCFtools the data was filtered 
* Mainly anything with more than 50% missing info was removed, only biallelic SNPs, a minor allel count of 3, and a minimum quality score of 30
* Then the data was filtered for different depths (5x, 10x, 15x, 20x, 25x, 30x)
* PCA (principle component analysis) were run for each depth 
* The sampling location and the genotype of the sample were used to show how the populations were segregated 
* missing data was looked at, in the form of graphs, to see what individules should be removed

### Papers I read 

Long prereproductive selection and divergence by depth in a Caribbean candelabrum coral - Carlos Prada 2012
