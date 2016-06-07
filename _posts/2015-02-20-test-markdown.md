---
layout: post
title: Principal Component Analysis (PCA)
subtitle: PCA using R Programming Language
---


Principal component analysis (PCA) is a commonly used multivariate data analysis to reveal hidden and unknown data structures. It seeks to find the linear combination of the predictors that capture the most possible variance (i.e. the PCs). Thus, the first PC or PC1, lies along the direction of maximal data variance that capture the most variability of all possible linear combinations. It creates components that are uncorrelated and summarize the characteristic of the data that are irrelevant to the underlying structure of the data. The advantages of PCA is that, unlike the data filtering the where only a pair of descriptors of correlated were removed, the pairs of PC are not correlated. Two of the most useful features of PCA include using it to reveal the correlation between all descriptors simultaneously via the loading scores while visualization of similarities and differences within samples are done via the PC scores. In here, we will try to perform PCA using R language. 

# Installing R for Mac 
In the first paragraph, I will briefly tell you how you can install R on Mac OS. It is a very simple process because all it takes is just a few step. So, the first thing you need to do is open your web browser, and go to [CRAN](http://cran.r-project.org). It is a comprehensive R network.  You will see a number of option for you to download for different platform. We are going to download the Mac platform. Once you click R for Mac OS X you will see the latest of the files end with .pkg (latest version) and you will see the download meter will start going. It might takes a few minutes depending on your internet connection. So just be patient. Once its finish downloading, just open it up on your computer. You will see the installer which will guide you the step necessary for you to download all R. It will be on your application folder once you finish the installation process. 

# Installing RStudio for Mac 
Before installing RStudio, you **must** have R installed in your compouter. So, once you installed R, you can go [RStudio](http://www.rstudio.com). There are two version for RStudio for downloads: one is for desktop and one is for server. In here, we are not going to use server version at all. So you will just want to download the desktop the version of RStudio. Download the Mac OS version and you will see the download meter go. Once thats finished downloading, just click on it to install it. Just like any other mac application, all you have to do to install is just drag the RStudio to the application folder. You can go to application folder and double click on it. Then there you go, you are running R studio. 

# Installing R packages
Packages in R are a bunch of commands or libraries you can use to carry out certain analysis. Installing R packages in RStudio is easy. You can go to Console and type install.packages with the parasenthese and quotation mark, type in the name of the package you wish to install. In here we use multiple packages from crane as will as bioconductors. The following list of packages can be installed from crane . **e.g. install.packages("protr")** to reproduce the results of the research. 

```{r eval=FALSE}
install.packages("protr")
```

One can  install packagees from Bioconductor by entering the source before the package can be installed. *When installing R packages from Biconductor, please avoid using proxy internet connection*

```{r eval=FALSE}
source("http://bioconductor.org/biocLite.R")
biocLite("Rcpi")
```


Downloaded packages  will be attached to the environment in order to perform PCA.

```{r eval=FALSE}
set.seed(800)
s = c("protr", "Rcpi")
sapply(s, require,character.only=TRUE)
```


Before diving into the PCA analysis:

How about a yummy crepe?

![Crepe](http://lafenicegelato.com/wp-content/uploads/2014/09/crepes-with-chocolate.jpg)

Here's a code chunk:

~~~
x <- 5 + 10
print(x)
~~~

And here is some code with syntax highlighting

```javascript
var foo = function(x) {
  return(x + 5);
}
foo(3)
```
