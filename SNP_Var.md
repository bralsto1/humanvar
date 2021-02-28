---

title: " SNP Variation in Human Population Class Work"
author: "Brett Ralston"
date: "February 28th, 2021"

---



#This is my code from class. The first block of code is for SNPs and their latitudinal variation!

```r
plot(freq$Allele_A, freq$lat, xlab="f(A) rs1426654", ylab="latitude",
     pch=16, cex=0.8, col=myColors[freq$superpop], xlim=c(0,1), main = "Latitudinal Variation in rs1426654 among 26 human populations")

legend("topleft", c("African", "Admixed American", "East Asian", "European", "South Asian"), cex = 0.8, 
       col = c("red", "blue", "darkgreen", "salmon", "black"), pch=16, inset=0.02)
```


#This is my code for the pie charts on the world map!

```r
map("worldHires", xlim = c(-120,142), ylim = c(-12,72), col = "gray", fill = FALSE)

for (m in 1:26){
  add.pie(z=c(freq$Allele_A[m], freq$Allele_G[m]), x= freq$long[m], y= freq$lat[m], radius = freq$N_CHR[m]/100,
          col=c(alpha("orange", 0.6), alpha("purple", 0.6)), labels=" ") 
  m=m+1
}

box()
```

#Here is the session info so you can make sure you are using the same packages.

```r print(sessionInfo())```r

R version 3.6.1 (2019-07-05)
Platform: x86_64-w64-mingw32/x64 (64-bit)
Running under: Windows >= 8 x64 (build 9200)

Matrix products: default

locale:
[1] LC_COLLATE=English_United States.1252  LC_CTYPE=English_United States.1252    LC_MONETARY=English_United States.1252
[4] LC_NUMERIC=C                           LC_TIME=English_United States.1252    

attached base packages:
[1] stats     graphics  grDevices utils     datasets  methods   base     

other attached packages:
[1] rmarkdown_1.12 markdown_0.9   ggplot2_3.3.3  mapplots_1.5.1 mapdata_2.3.0  maps_3.3.0    

loaded via a namespace (and not attached):
 [1] Rcpp_1.0.1       rstudioapi_0.10  knitr_1.22       magrittr_1.5     tidyselect_0.2.5 munsell_0.5.0   
 [7] colorspace_2.0-0 R6_2.4.0         rlang_0.4.10     dplyr_0.8.0.1    tools_3.6.1      grid_3.6.1      
[13] gtable_0.3.0     xfun_0.6         withr_2.4.1      htmltools_0.3.6  digest_0.6.18    yaml_2.2.0      
[19] assertthat_0.2.1 tibble_2.1.1     lifecycle_1.0.0  crayon_1.3.4     purrr_0.3.2      farver_2.0.3    
[25] evaluate_0.13    glue_1.3.1       compiler_3.6.1   pillar_1.3.1     scales_1.1.1     pkgconfig_2.0.2 