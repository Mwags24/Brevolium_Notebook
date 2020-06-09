---
layout: post
title: "Admixture"
categories: 
tags: 
---


# Making graphs using Admixture data


Using the code presented in this tutorial: https://indo-european.eu/human-ancestry/admixture-ancestry-components-r-statistics-plink-convertf-bed-and-ped-files/

I Began creating plots, using this base code

    par(c(1.5, 4, 2.5, 2), cex.lab=0.75,cex.axis=0.6,)
    barplot(t(as.matrix(ordered[,1:2])), col = brewer.pal(3,"Set1"), ylab = "Anc. Proportions", border= NA, space=0,names.arg = barNaming(ordered$Sample), las =2)


|![K2]({{ site.baseurl }}/images/Admixture_K2_plot.pdf "Admixture K2 plot")

|![K3]({{ site.baseurl }}/images/Admixture_K3_plot.pdf "Admixture K3 plot")

|![K4]({{ site.baseurl }}/images/Admixture_K4_plot.pdf "Admixture K4 plot")