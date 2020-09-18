
##### Task 1

Downlod xls file

```r
url<-"https://data.gov.ua/dataset/175386f8-fbce-4352-8ec9-44fc8c436aa9/resource/e58e005a-c448-4d97-9d45-813f05b1d737/download/nabir-2020-2022-roki.xls"
download.file(url, destfile="./forecast.xlsx", mode='wb')
```

Read file

```r
install.packages("readxl")
library(readxl)
df<-read_excel("C:/Users/HP/Documents/forecast.xls", sheet=1)
df
```

```r
df<-read_excel("C:/Users/HP/Documents/forecast.xls", sheet=1)
> df
# A tibble: 17 x 8
   `№ з/п` Показник `Прогноз 2020 с~ `Прогноз 2020 с~ `Прогноз 2021 с~ `Прогноз 2021 с~
     <dbl> <chr>    <chr>            <chr>            <chr>            <chr>           
 1       1 Валовий~ 4510.8000000000~ 4 598,8          5 041,6          5 206,9         
 2       2 Валовий~ 103.7            104.8            103.8            105.5           
 3       3 Індекс ~ 106.40000000000~ 106.59999999999~ 105.59999999999~ 105.5           
 4       4 Індекс ~ 105.5            105.8            105.3            105             
 5       5 Індекс ~ 108.2            109              108              108             
 6       6 Прибуто~ 937.60000000000~ 942.39999999999~ 1 050,9          1080.5          
 7       7 Фонд оп~ 1352.2           1 374,8          1 528,9          1 600,6         
 8       8 Середнь~ 12497            12552            14187            14692           
 9       9 Середнь~ 110.09999999999~ 110.40000000000~ 107.5            110.90000000000~
10      10 Кількіс~ 16.510000000000~ 16.780000000000~ 16.609999999999~ 16.920000000000~
11      11 Рівень ~ 8.0999999999999~ 7.2999999999999~ 7.9000000000000~ 6.7000000000000~
12      12 Продукт~ 103.2            102.59999999999~ 103.2            104.59999999999~
13      13 Сальдо ~ –14 882          –16 743          –16 561          –21 597         
14      14 Експорт~ 68642            69270            73530            75692           
15      15 Експорт~ 107.8            108.8            107.09999999999~ 109.3           
16      16 Імпорт ~ 83524            86013            90091            97289           
17      17 Імпорт ~ 109.59999999999~ 112.90000000000~ 107.90000000000~ 113.09999999999~
```

##### Task 2
Download  csv file
```r
fileurl<-("https://d396qusza40orc.cloudfront.net/getdata%2Fdata%2Fss06hid.csv")
download.file(fileurl, destfile="./getdata.csv", mode='wb')
```

read csv file
```r
fileUrl <- "https://d396qusza40orc.cloudfront.net/getdata%2Fdata%2Fss06hid.csv"
df <- read.csv(fileUrl)
df
```
count properties with value more then 1000000

```r
> subset_1<-subset(df, VAL==24)
> nrow(subset_1)
 ```
53

```r
sum(df$VAL==24 & !is.na(df$VAL))
```
53

##### Task 3
Download xml file

```r
library(xml2)

pg <- read_xml("http://d396qusza40orc.cloudfront.net/getdata%2Fdata%2Frestaurants.xml")
```
Convert xml to dataframe

```r
doc <- as_list(pg)
str(doc$response, 1)

library(tidyr)
dat<- tibble::as_tibble(doc) %>%
  # new tidyr function
  unnest_wider(response) %>%
  # unnest same length list cols
  unnest(cols = names(.)) %>%
  unnest(cols = names(.)) %>%
  # convert using readr parser
 readr::type_convert()
```
Transpose dataframe
```r
dat_transpose <- as.data.frame(t(as.matrix(dat)))
```
```r
sum(dat_transpose$V2==21231 & !is.na(dat_transpose$V2))
```
127














