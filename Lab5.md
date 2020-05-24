
```{r}
setwd("c:/specdata")
> getwd()
 "c:/specdata"
> file_list <- list.files(path="c:/specdata", pattern=".csv")
> length(file_list)
 332
 ```
 ### Task 1
```{r}
> pmean <- function(directory, pollutant, id=1:332){
+   file_list <- list.files(path="c:/specdata", pattern=".csv", full.names=TRUE)
+   values <- numeric()
+   for (i in id){
+     df <- read.csv(file_list[i])
+     values <- c(values, df[[pollutant]])
+   }
+   mean(values, na.rm=TRUE)
+ }
```

```{r}
> pmean("specdata", "sulfate", 1:10)
 4.064128
> pmean("specdata", "nitrate")
 1.702932
> pmean("specdata", "sulfate", 55)
 3.587319
 ```
 ### Task 2
 
 ```{r}
> complete <- function(directory, id=1:332){
+   file_list <- list.files(path="c:/specdata", pattern=".csv", full.names=TRUE)
+   numobs <- numeric()
+   for (i in id){
+     df <- read.csv(file_list[i])
+     numobs <- c(numobs, sum(complete.cases(df)))
+   }
+   data.frame(id, numobs)
+ }
```

```{r}
complete("cpecdata", 1)
```
id| numobs
--|---
 1  |  117

```{r}
complete("specdata", c(1, 4, 6, 34))
```
obs |  id | numobs
----|-----|------
1 | 1 |   117
2 | 4  |  474
3 | 6  |  228
4 | 34 |   165

```{r}
complete("specdata", 35:45)
```
 obs |  id | numobs
 ----|-----|------
1 | 35 |   509
2 | 36 |   495
3 | 37 |   497
4 | 38 |   491
5 | 39 |   734
6 | 40  |   21
7 | 41   | 227
8 | 42   |  60
9 | 43   |  74
10| 44  |  283
11 | 45  |  424

### Task 3

```{r}
> corr <- function(directory, threshold=0){
+   file_list <- list.files(path="c:/specdata", pattern=".csv", full.names=TRUE)
+   v<-c()
+   for (i in 1:length(file_list)){
+     df <- read.csv(file_list[i])
+     df <- df[complete.cases(df),]
+     if (nrow(df)>threshold){
+       v <- c(v, cor(df$sulfate, df$nitrate))
+     }
+   }
+   return(v)
+ }
```

```{r}
> x <- corr("specdata", 150)
> head(x)
[1] -0.01895754 -0.14051254 -0.04389737 -0.06815956
[5] -0.12350667 -0.07588814
```

```{r}
> summary(x)
    Min.  1st Qu.   Median     Mean  3rd Qu.     Max. 
-0.21057 -0.04999  0.09463  0.12525  0.26844  0.76313 
```
```{r}
> x <- corr("specdata", 400)
> head(x); summary(x)
[1] -0.01895754 -0.04389737 -0.06815956 -0.07588814
[5]  0.76312884 -0.15782860
    Min.  1st Qu.   Median     Mean  3rd Qu.     Max. 
-0.17623 -0.03109  0.10021  0.13969  0.26849  0.76313
```
```{r}
> x <- corr("specdata", 4000)
> head(x); summary(x)
NULL
Length  Class   Mode 
     0   NULL   NULL
 ```









