###This is my code from class. The first block of code is for SNPs and their latitudinal variation!

```r
plot(freq$Allele_A, freq$lat, xlab="f(A) rs1426654", ylab="latitude",
     pch=16, cex=0.8, col=myColors[freq$superpop], xlim=c(0,1), main = "Latitudinal Variation in rs1426654 among 26 human populations")

legend("topleft", c("African", "Admixed American", "East Asian", "European", "South Asian"), cex = 0.8, 
       col = c("red", "blue", "darkgreen", "salmon", "black"), pch=16, inset=0.02)
```


###This is my code for the pie charts on the world map!

```r
map("worldHires", xlim = c(-120,142), ylim = c(-12,72), col = "gray", fill = FALSE)

for (m in 1:26){
  add.pie(z=c(freq$Allele_A[m], freq$Allele_G[m]), x= freq$long[m], y= freq$lat[m], radius = freq$N_CHR[m]/100,
          col=c(alpha("orange", 0.6), alpha("purple", 0.6)), labels=" ") 
  m=m+1
}

box()
```