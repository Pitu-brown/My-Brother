---
layout: post
title: Molecular modelling
subtitle: A Brief Introduction
---

If it is not possible to obtain the crystal structure, it is pretty common to predict the structure based on protein sequence. Protein structure prediction can be classified into two types, which are ab initio and homology protein modelling (comparative modelling). Although ab initio methods are still not accurate enough to be useful in drug design projects, homology modelling is extensively  used in pharmaceutical industry. In homology modelling , amino acid sequence of the target protein is aligned with the template. Based on this sequence identity, the target's 3D structure can be built by exchainging the target's aligned amino acids with those of the template. In addition, physics-based energy calculatings to minimize the energy of the structure and other close to the true strucutre. As a rule-of-thumb, the sequence identity of the protein should be at least 30 % with the template, then it is possible to apply homology modeling. I did a homology modelling using the [modeller](https://salilab.org/modeller/) and you can look at the process in [this jupyter notebook](https://github.com/sawsimeon/Modeller/blob/master/Modeller%20Tutorial.ipynb) along with data set as well as resulting output in [here](https://github.com/sawsimeon/Modeller).
