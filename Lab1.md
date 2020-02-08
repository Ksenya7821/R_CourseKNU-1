#### Task 1.  Create five basic or “atomic” classes of objects


``` {r}
int <- 10L
print(int)
```
[1] 10

```{r}
num <- 3.1415
print(num)
```

[1] 3.1415

```{r}
st <- "hello world"
print(st)
```

```{r}
lg <- TRUE
lg
```

TRUE

```{r}
cpl <- 1+0i
cpl
```
1+0i

#### Task 2. Create vestors

```{r}
v_1 <- c(5:75)
v_1
```

[1]  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40
[37] 41 42 43 44 45 46 47 48 49 50 51 52 53 54 55 56 57 58 59 60 61 62 63 64 65 66 67 68 69 70 71 72 73 74 75

```{r}
v_2 <- c(3.14, 2.71, 0, 13)
v_2
```

[1]  3.14  2.71  0.00 13.00

```{r}
v_3 <- c(1:100)
as.logical(v_3)
```

```{r}
vec <- rep (TRUE, 100)
vec
```

[1] TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE
[22] TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE
[43] TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE
[64] TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE
[85] TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE



#### Task 3. Create  matrix
```{r}
x <- c(0.5, 1.3, 3.5)
y <- c(3.9, 131, 2.8)
a <- c(0, 2.2, 4.6)
b <- c(2, 7, 5.1)
m <- rbind(x, y, a, b)
m
```

```{r}
mat <- matrix(c(0.5, 3.9, 0, 2, 1.3, 131, 2.2, 7, 3.5, 2.8, 4.6, 5.1), nrow = 4, ncol = 3)
mat
```

0.5 |  1.3 | 3.5
----|------|------
3.9 | 131.0 | 2.8
0.0  | 2.2 | 4.6
2.0  | 7.0 | 5.1

#### Task 4. Create the list
```{r}
lst <- list(59L, 378.42, "programming", FALSE, 1 + 4i)
lst
```

[[1]]
[1] 59

[[2]]
[1] 378.42

[[3]]
[1] "programming"

[[4]]
[1] FALSE

[[5]]
[1] 1+4i

#### Task 5. Create factor with three level "baby", "child", "adult".
```{r}
ftr <- factor( c("baby", "child", "adult", "baby", "child", "adult", "baby", "child", "child"))
ftr
```


#### Task 6.  Find the index of the first element NA in vector
```{r}
v <- c(1, 2, 3, 4, NA, 6, 7, NA, 9, NA, 11)
l <- is.na(v) # output a true/false vector
l
```

```{r}
first_NA <- min(which(l)) # find index of first NA element
first_NA
```
[1] 5

```{r}
count_NA <- length(which(l)) # find index of first NA element
count_NA
```
[1] 3

#### Task 7. Create dataframe
```{r}
df <- data.frame(a = 1:4, b = c("M", "M", "F", "F"), c = c(3.67, 6.78, 4.89, 9.01))
df
```
  a |b | c
----|---|------
1 | M | 3.67
2 | M | 6.78
3 | F | 4.89
4 | F | 9.01

#### Task 8. Rename columns
```{r}
names(df) <- c("Rank", "Gender", "Score")
df
```
Rank | Gender | Score
------|--------|---------
1 | M | 3.67
2 | M | 6.78
3 | F | 4.89
4 | F | 9.01
