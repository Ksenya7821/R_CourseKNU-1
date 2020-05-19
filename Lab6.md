
### Task 1
Create matrix

```{r}
> mat <- matrix(rnorm(50), 10, 5)
> mat
```

```{r}
          [,1]        [,2]        [,3]
 [1,] -0.7009123  0.05301138  0.08275954
 [2,] -2.1926907 -2.67574809  1.44615927
 [3,]  1.5169131 -0.51512561  0.20642686
 [4,] -0.5925219 -0.63645202 -2.81100801
 [5,] -2.3343449  1.60603193  1.37237669
 [6,]  1.5072197 -1.00096507 -0.88207774
 [7,] -0.4368354  1.10546686 -0.49858266
 [8,] -2.5162553  0.72417457  0.87019052
 [9,] -0.4075430 -0.12716336 -0.59756258
[10,]  1.4862970 -1.11383631 -1.32674274
             [,4]       [,5]
 [1,] -1.48768211 -0.3741096
 [2,]  0.34806427 -0.3962435
 [3,]  0.64882996 -0.6176965
 [4,] -1.63239923 -0.6987548
 [5,] -0.30681320  1.7755665
 [6,] -0.21034906  0.5818736
 [7,] -1.25586421 -0.2465306
 [8,] -0.22700497  0.8599109
 [9,] -0.05418829  0.9906947
[10,] -0.78267576 -0.2999899
````

### Task 2
Find maximum value in each column

```{r}
# 2 indicates columns
apply(mat, 2, max)
```
 1.516913 1.606032 1.446159 0.648830 1.775566
 
 ### Task 3
 Find mean value in each column
 
```{r}
apply(mat, 2, mean)
```
-0.4670674 -0.2580606 -0.2138061 -0.4960083  0.1574721

### Task 4
Find minimum value in each row
```{r}
apply(mat, 1, min)
```
-1.4876821 -2.6757481 -0.6176965 -2.8110080 -2.3343449 -1.0009651 -1.2558642 -2.5162553
-0.5975626 -1.3267427

### Task 5
Sort columns

```{r}
apply(mat, 2, sort)
```
```{r}
           [,1]        [,2]        [,3]        [,4]       [,5]
 [1,] -2.5162553 -2.67574809 -2.81100801 -1.63239923 -0.6987548
 [2,] -2.3343449 -1.11383631 -1.32674274 -1.48768211 -0.6176965
 [3,] -2.1926907 -1.00096507 -0.88207774 -1.25586421 -0.3962435
 [4,] -0.7009123 -0.63645202 -0.59756258 -0.78267576 -0.3741096
 [5,] -0.5925219 -0.51512561 -0.49858266 -0.30681320 -0.2999899
 [6,] -0.4368354 -0.12716336  0.08275954 -0.22700497 -0.2465306
 [7,] -0.4075430  0.05301138  0.20642686 -0.21034906  0.5818736
 [8,]  1.4862970  0.72417457  0.87019052 -0.05418829  0.8599109
 [9,]  1.5072197  1.10546686  1.37237669  0.34806427  0.9906947
[10,]  1.5169131  1.60603193  1.44615927  0.64882996  1.7755665
```
### Task 6
Find number of values less than 0 in each column
```{r}
apply(mat,2,function(x) sum(x<0))
```
7 6 5 8 6

### Task 7
Create vector where TRUE is when column has values greater than 2 otherwise FALSE

```{r}
apply(mat,2,function(x) sum(x>2)>0)
```
FALSE FALSE FALSE FALSE FALSE


### Task 8
Create list list1 <- list(observationA = c(1:5, 7:3), observationB = matrix(1:6, nrow=2))

```{r}
list1 <- list(observationA = c(1:5, 7:3), observationB = matrix(1:6, nrow=2))
```

```{r}
list1

$observationA
 [1] 1 2 3 4 5 7 6 5 4 3

$observationB
     [,1] [,2] [,3]
[1,]    1    3    5
[2,]    2    4    6

```
Count sum
```{r}
lapply(list1, mean)
```
```{r}
$observationA
[1] 4

$observationB
[1] 3.5
```

### Task 9
For each element in the list find maximum and minimum values (range)

```{r}
# lapply function
lapply(list1, min)
```
```{r}
$observationA
[1] 1

$observationB
[1] 1
```

```{r}
# sapply function
sapply(list1, min)
```
```{r}
observationA observationB 
           1            1 
```

```{r}
lapply(list1, max)
```

```{r}
$observationA
[1] 7

$observationB
[1] 6
```

```{r}
sapply(list1, max)
```

```{r}
observationA observationB 
           7            6 
```
### Task 10
```{r}
v <- split(InsectSprays$count, InsectSprays$spray)
v
```

```{r}
$A
 [1] 10  7 20 14 14 12 10 23 17 20 14 13

$B
 [1] 11 17 21 11 16 14 17 17 19 21  7 13

$C
 [1] 0 1 7 2 3 1 2 1 3 0 1 4

$D
 [1]  3  5 12  6  4  3  5  5  5  5  2  4

$E
 [1] 3 5 3 5 3 6 1 1 3 2 6 4

$F
 [1] 11  9 15 22 15 16 13 10 26 26 24 13
```
```{r}
sapply(v, mean)
```

```{r}
        A         B         C         D         E          F
14.500000 15.333333  2.083333  4.916667  3.500000  16.666667 
```
