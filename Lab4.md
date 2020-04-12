#### Task 1
Read csv file
```{r}
data_set <- read.csv(file="C:/mylib/hw1_data.csv", header=TRUE, sep=",")
```

#### Task 2
Show first six rows

```{r}
head(data_set, 6)
```
Output:
```{r}
  Ozone Solar.R Wind Temp Month Day
1    41     190  7.4   67     5   1
2    36     118  8.0   72     5   2
3    12     149 12.6   74     5   3
4    18     313 11.5   62     5   4
5    NA      NA 14.3   56     5   5
6    28      NA 14.9   66     5   6
```

#### Task 3
Count number of observations
```{r}
nrow(data_set)
```
153

#### Task 4
Show last 10 rows
```{r}
tail(data_set, 10)
```
Output:
```{r}
    Ozone Solar.R Wind Temp Month Day
144    13     238 12.6   64     9  21
145    23      14  9.2   71     9  22
146    36     139 10.3   81     9  23
147     7      49 10.3   69     9  24
148    14      20 16.6   63     9  25
149    30     193  6.9   70     9  26
150    NA     145 13.2   77     9  27
151    14     191 14.3   75     9  28
152    18     131  8.0   76     9  29
153    20     223 11.5   68     9  30
```

#### Task 5
Count NA values across variable Ozone
```{r}
length(which(is.na(data_set$Ozone)))
```
37

#### Task 6
Count mean(Ozone) excluding NA values

```{r}
mean(data_set$Ozone[!is.na(data_set$Ozone)])
```
42.12931

#### Task 7
Create subset
```{r}
sub_set <- subset(data_set, data_set$'Ozone'>31 & data_set$'Temp' > 90)
```

#### Task 8
Mean(temp) if mounth is June
```{r}
mean(data_set$'Temp'[data_set$'Month' == 6])
```
79.1

#### Task 9
Max(Ozone) for May
```{r}
 max(data_set$Ozone[data_set$Month==5], na.rm=TRUE)
 ```
 115





