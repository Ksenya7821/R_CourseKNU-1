
```{r}
setwd("c:/specdata")
> getwd()
 "c:/specdata"
> file_list <- list.files()
> length(file_list)
 332
 ```
 ### Task 1
```{r}
> pmean <- function(directory, pollutant, id=1:332){
+   file_list <- list.files()
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
+   file_list <- list.files()
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
|id| numobs
---|---|---
1 | 1  |  117

```{r}
complete("specdata", c(1, 4, 6, 34))
```










