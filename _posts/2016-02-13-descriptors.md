---
layout: post
title: Molecular Descriptors
subtitle: Generating Molecular & Fingerprint Descriptors using R programming language
---

Understanding biological, chemical and physical properties of chemical compounds is central issue in pharmaceutical bioinformatics and to what accuracy we can predict these properties sorely depends on how a chemical compounds is described. Many molecular descriptors have been introduced with the aim of finding the information rich and most suited descriptors to relate these properties. In here, molecular and fingerprint descriptors will be calculated using the AChE data set and also the fingerprint descriptors. Molecular fingerprint descriptors are distince for the chemical compounds that represent, like a human fingerprint that are distince for the person they belong to. They pinpoint posiiton in the fingerprint sequence to represnet some feature of the molecule. The data set contains SMILES notation of AChE inhibitors which are standardized using the following options: strip salt, aromataize, tautomerize, neutralize and remove explicit hydrogens. We will be using RCurl and rcdk R package to get calculate descriptors both for molecular and fingerprint descirptors. At first, let us get the compounds from the [AChE repo](https://raw.githubusercontent.com/sawsimeon/AChE/master/AChE.smi). Once the smiles are loaded, we convert the SMILES into a java object, which can be used to get the molecular descriptors. To speed up things we will just use only 10 compounds. 


~~~
library(RCurl)
library(rcdk)
x <- getURL("https://raw.githubusercontent.com/sawsimeon/AChE/master/AChE.smi")
y <- read.csv(text = x, header = FALSE)
names(y) <- "smiles"
smiles <- y$smiles
smiles <- as.character(smiles)
mols <- parse.smiles(smiles)[1:10]
~~~

# Molecular Descriptors

### Topological Descriptors

~~~
desc.names <- get.desc.names("topological")
data <- lapply(mols, eval.desc, desc.names)
descriptors <- data.frame(matrix(unlist(data), nrow = length(mols), byrow = T))
colnames(descriptors) <- colnames(data[[1]])
~~~

### Geometrical Descriptors

~~~
desc.names <- get.desc.names("geometrical")
data <- lapply(mols, eval.desc, desc.names)
descriptors <- data.frame(matrix(unlist(data), nrow = length(mols), byrow = T))
colnames(descriptors) <- colnames(data[[1]])
~~~

### Constitutional Descriptors

~~~
desc.names <- get.desc.names("constitutional")
data <- lapply(mols, eval.desc, desc.names)
descriptors <- data.frame(matrix(unlist(data), nrow = length(mols), byrow = T))
colnames(descriptors) <- colnames(data[[1]])
~~~

### Electronic Descriptors

~~~
desc.names <- get.desc.names("electronic")
data <- lapply(mols, eval.desc, desc.names)
descriptors <- data.frame(matrix(unlist(data), nrow = length(mols), byrow = T))
colnames(descriptors) <- colnames(data[[1]])
~~~

# Fingerprints

### MACSS

~~~
fps <- lapply(mols, get.fingerprint, type='maccs')
descriptors <- fp.to.matrix(fps)
~~~

### Signature Fingerprint
~~~
fps <- lapply(mols, get.fingerprint, type='signature')
descriptors <- fp.to.matrix(fps)
~~~

### Circular Fingerprint
~~~
fps <- lapply(mols, get.fingerprint, type='circular')
descriptors <- fp.to.matrix(fps)
~~~

### Extended CDK Fingerprint
~~~
fps <- lapply(mols, get.fingerprint, type='extended')
descriptors <- fp.to.matrix(fps)
~~~

