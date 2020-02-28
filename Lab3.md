#### Task 1

```{r}
# creating vectors x and y
x <- seq(5, 10, length=10)
x
```

5.000000  5.555556  6.111111  6.666667  7.222222  7.777778
8.333333  8.888889  9.444444 10.000000
```{r}
y <- seq(0, 12, length=10)
y
```
0.000000  1.333333  2.666667  4.000000  5.333333  6.666667
8.000000  9.333333 10.666667 12.000000

```{r}
# creating function
add2 <- function(x, y) { 
  x + y
}

add2(x, y)
```
5.000000  6.888889  8.777778 10.666667 12.555556 14.444444
16.333333 18.222222 20.111111 22.000000
> 

#### Task 2

```{r}
# creating vector
z <- seq(8, 15, length=10)
z

# initiating function
above <- function(x, n) {
x[x>n]
}

above(z, 10)
```
10.33333 11.11111 11.88889 12.66667 13.44444 14.22222 15.00000

#### Task 3

```{r}
# initiating function
my_ifelse <- function(x, exp, n){
 if  (exp == ">"x) {
   [x>n]
 } else if (exp == "<"){
  x[x<n]
 } else if (exp == ">="){
  x[x>=n]
 } else if (exp == "<="){
  x[x<=n]
 } else if (exp == "=="){
  x[x==n]
 } else {
    x
 }
}

my_ifelse(z, ">=", 10)
10.33333 11.11111 11.88889 12.66667 13.44444 14.22222 15.00000

my_ifelse(z, "<=", 10)
8.000000 8.777778 9.555556

my_ifelse(z, ">", 12)
12.66667 13.44444 14.22222 15.00000

 my_ifelse(z, "<", 13)
8.000000  8.777778  9.555556 10.333333 11.111111 11.888889 12.666667

my_ifelse(z, "*", 10)
8.000000  8.777778  9.555556 10.333333 11.111111 11.888889 12.666667 13.444444 14.222222 15.000000
```

#### Task 3

```{r}
# creating matrix
m <- matrix(c(4, 5, NA, 7, 8, NA, 9, 10, NA, 13, 16, 15), nrow=4, ncol=3)
m
```
4  |  8 |  NA
---|-----|------
5 |  NA  | 13
NA  |  9  | 16
7 |  10  | 15

```{r}
# initiating function
columnmean <- function(x, removeNA = TRUE) {
  colMeans(x, na.rm = removeNA)
  }
```
```{r}
columnmean(m, FALSE)
```
NA NA NA

```{r}
columnmean(m, TRUE)
```
5.333333  9.000000 14.666667






