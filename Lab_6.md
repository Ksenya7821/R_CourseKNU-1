Loading data

```{r}
Url <- "https://archive.ics.uci.edu/ml/machine-learning-databases/00235/household_power_consumption.zip"

download.file(Url, destfile=paste0(getwd(), "/power_consumption.zip"), method = "curl")

```

Reading NA values and keep rows rows that contain information on 2007-02-01 and 2007-02-02
```{r}
dt <- read.table( "household_power_consumption.txt", header=TRUE, sep=";", na.strings = "?")

subdt <- subset(dt, Date=="1/2/2007" | Date =="2/2/2007")
```
Converting Date and Time variables to Date/Time format
```{r}
subdt <- subset(dt, Date=="1/2/2007" | Date =="2/2/2007")
subdt$Date<-as.Date(subdt$Date, format = "%d/%m/%Y")
subdt$DateTime<-strptime(paste(subdt$Date,subdt$Time),"%F %T")
```

### Task 1
Histogram of Global active pover consumption

png("plot1.png", width=480, height=480)
hist(subdt$Global_active_power, col="red", main="Global Active Power", 
     xlab="Global Active Power (kilowatts)")
dev.off()

### Task 2
Global active pover consumption over time
