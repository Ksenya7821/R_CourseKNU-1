
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
read_excel("C:/Users/HP/Documents/forecast.xls", sheet=1)
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
library(XML)

dat <-  xmlTreeParse("http://d396qusza40orc.cloudfront.net/getdata%2Fdata%2Frestaurants.xml",useInternal = TRUE)
x <- xmlRoot(dat)

```
```r
sum(xpathSApply(x,"//zipcode",xmlValue) == 21231)
```
127














