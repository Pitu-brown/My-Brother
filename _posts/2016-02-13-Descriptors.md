---
layout: post
title: Molecular Descriptors
subtitle: Generating Molecular & Fingerprint Descriptors using R programming language
---

Understanding biological, chemical and physical properties of chemical compounds is central issue in pharmaceutical bioinformatics and to what accuracy we can predict these properties sorely depends on how a chemical compounds is described. Many molecular descriptors have been introduced with the aim of finding the information rich and most suited descriptors to relate these properties. In here, molecular and fingerprint descriptors will be calculated using the AChE data set. The data set contains SMILES notation of AChE inhibitors which are standardized using the following options: strip salt, aromataize, tautomerize, neutralize and remove explicit hydrogens. We will be using RCurl and rcdk R package to get calculate descriptors both for molecular and fingerprint descirptors. At first, let us get the compounds from the [AChE repo](https://raw.githubusercontent.com/sawsimeon/AChE/master/AChE.smi). Once the smiles are loaded, we will 


~~~
library(RCurl)
library(rcdk)
x <- getURL("https://raw.githubusercontent.com/sawsimeon/AChE/master/AChE.smi")
y <- read.csv(text = x, header = FALSE)
names(y) <- "smiles"
smiles <- y$smiles
smiles <- as.character(smiles)
mol <- parse.smiles(smiles)
~~~

