---
title       : Data products
subtitle    : Exploring CO2 dataset 
author      : Andrew Sila, Data Science course learner
job         : Nairobi, Kenya
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Exploring CO2 dataset

1. View the data 
2. Using a boxplot
3. Anova

--- .class #id 

====
## View data
1. Start by reading in the CO2 dataset
2. Give the number of observation to be viewed in th header.
3. We set six as the default number to view in the app.

```r
data(CO2)
head(CO2)
```

```
##   Plant   Type  Treatment conc uptake
## 1   Qn1 Quebec nonchilled   95   16.0
## 2   Qn1 Quebec nonchilled  175   30.4
## 3   Qn1 Quebec nonchilled  250   34.8
## 4   Qn1 Quebec nonchilled  350   37.2
## 5   Qn1 Quebec nonchilled  500   35.3
## 6   Qn1 Quebec nonchilled  675   39.2
```

--- .class #id 

===

## Boxplot
1. Visualize the CO2 dataset with a boxplot
2. Plant co2 uptake can be viewed versus: Type, Treatment and conc 


```r
data(CO2)
with(CO2, boxplot(uptake~conc,col="blue",ylab="Co2 uptake",xlab="conc"))
```

![plot of chunk unnamed-chunk-2](assets/fig/unnamed-chunk-2-1.png) 

--- .class #id 

===

## Anova

Test for significance of each of the three experiment factors:
    1. Type
    2. Treatment
    3. conc

### Testing for conc illustrated.

```r
data(CO2)
with(CO2, aov(uptake~conc))
```

```
## Call:
##    aov(formula = uptake ~ conc)
## 
## Terms:
##                     conc Residuals
## Sum of Squares  2284.994  7421.982
## Deg. of Freedom        1        82
## 
## Residual standard error: 9.513778
## Estimated effects may be unbalanced
```




