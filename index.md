---
title       : A Capability Modeler App
subtitle    : Developing Data Products Project
author      : Douglas Gorman
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Capability Metrics Modeler

My Application demonstrates the relationship between the distribution of a process output and its specifications

Along with this graphical depiction the Capability Statistics Cp and Cpk are calculated

Cp and Cpk are commonly used metrics in Six Sigma to measure the 
capability of process to meet customer requirements

https://dougiegee.shinyapps.io/project/

--- .class #id  

## Capability Metrics Cp

Cp measures the potential Capability of a process  
Cp compares the width of a distribution(as measured by 6 Standard Deviations) to the width of the specification limits 
(USL - LSL) as a ratio
   
   Cp = (USL-LSL)/(6*S)

---

## Cp Example

In this example the width of the distribution equals the width of the specs, so the Cp metric is unity.


```r
USL<-23
LSL<-17
S<-1
(USL-LSL)/(6*S)
```

```
## [1] 1
```

---

## Capability Metrics Cpk

The metric Cp doesn't account for the location (mean) of the distribution  

Cpk on the other hand has a penalty when the mean is not mid-way between 
  the lower and upper spec limits.  
  
  Cpk = Min[ (Mean-LSL)/(3\*S),  (USL-Mean)/(3*S) ]
  
Cpk compares the distance from the mean to the nearest spec to half of the distribution spread (3 Standard Deviations).

---

## Cpk Example

Take the same example as above where the mean is exactly midway between the specs (20), Cpk matches Cp and is again unity.


```r
USL<-23
LSL<-17
S<-1
Mu<-20
(Mu-LSL)/(3*S)
```

```
## [1] 1
```

Now consider the mean shifted down one unit to (19), note that the Cpk is reduced.

```r
Mu<-19
(Mu-LSL)/(3*S)
```

```
## [1] 0.6666667
```



