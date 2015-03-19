---
title       : Decorate your heatmap
subtitle    : https://riverlee2008.shinyapps.io/DecorateHeatmap/
author      : Jiang Li
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Example data set


```r
set.seed(100)
data <- matrix(rnorm(1000), 40, 25)
data[1:15, seq(6, 25, 2)] = data[1:15, seq(6, 25, 2)] + 2
data[16:40, seq(7, 25, 2)] = data[16:40, seq(7, 25, 2)] + 4
colnames(data) <- c(paste("Control", 1:5, sep = ""), paste(c("TrtA", "TrtB"),
                                                           rep(1:10, each = 2), sep = ""))
rownames(data) <- paste("Probe", 1:40, sep = "")
```

---

## Default display

```r
heatmap(data)
```

![plot of chunk defaultHm](assets/fig/defaultHm-1.png) 

---


## Change color to Green-Black-Red


```r
hmcols <- colorRampPalette(c("green", "black", "red"))(256)
heatmap(data,col=hmcols )
```

![plot of chunk hm1](assets/fig/hm1-1.png) 

---

## No dendrogram of rows


```r
heatmap(data,col=hmcols, Rowv = NA )
```

![plot of chunk hm2](assets/fig/hm2-1.png) 





