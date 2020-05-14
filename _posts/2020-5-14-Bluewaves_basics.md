---
layout: post
title: "Basics of using Bluewaves"
categories: 
tags: 
---

## Starting to use Bluewaves


### This can act as a reference for how to get started on a project similar to this


Bluewaves is a HPC (High Powered Computing) cluster for the use of researchers at URI.
It allows for the storage, accsessing, and anlysis of data between members of a lab.

I will be using it to first pull the Data I will be working with, then analyse it using tools provided by downloadable packages.

For this work I will just be working on the HEad node of bluewaves (I do not need to submit a job request since the files and alysis are relativly small)

In order to accsess Bluewaves I ssh into it with the following code:
     ssh -l myles_wagner bluewaves.uri.edu
Further, in order to get to the project I am currently working on I can cd into the Brevolium_depth directory using the following code:
    cd /data/pradalab/Brevolium_depth/

# Making a Directory for the data

First I cd'd into the folder containing the data I will be working with and created a working directory
______
 cd /data/pradalab/mgomez/brevolium
 mkdir snp_filter
 cd snp_filter/ 

______

I then created a sof link to my own directory so I could work with it
ln -s ../read_group/brevolium_raw.vcf .

using this new directory I could begin my analysis.


