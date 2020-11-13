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
subdt$Date<-as.Date(subdt$Date, format = "%d/%m/%Y")
subdt$DateTime<-strptime(paste(subdt$Date,subdt$Time),"%F %T")
```

### Task 1
Histogram of Global active pover consumption

```{r}
png("plot1.png", width=480, height=480)
hist(subdt$Global_active_power, col="red", main="Global Active Power", 
     xlab="Global Active Power (kilowatts)")
dev.off()
```
![Plot]( https://github.com/Mariia97/R_CourseKNU/blob/master/plot1.png)

### Task 2
Global active pover consumption over time

```{r}
png("plot2.png", width=480, height=480)
plot(subdt$DateTime,subdt$Global_active_power, ylab="Global Active Power (kilowatts)", 
     xlab="", type="l")
dev.off()
```
![Plot]( https://github.com/Mariia97/R_CourseKNU/blob/master/plot2.png)

### Task 3
Energy sub meterings
```{r}
png("plot3.png", width=480, height=480)

plot(subdt$DateTime,subdt$Sub_metering_1,ylab="Energy sub metering", xlab="", type="l", col="black")
points(subdt$DateTime,subdt$Sub_metering_2, col="red", type="l")
points(subdt$DateTime,subdt$Sub_metering_3, col="blue", type="l")
legend("topright", lwd=1, col=c("black", "red", "blue"), legend=names(subdt[,7:9]))
dev.off()
```
![Plot]( https://github.com/Mariia97/R_CourseKNU/blob/master/plot3.png)


### Task 4
Combination of 4 plots: global active power, energy sub meterings, voltage over time, global reactive power over time
```{r}
png("plot4.png", width=480, height=480)
par(mfcol=c(2,2))
# Plot 4.1
plot(subdt$DateTime, subdt$Global_active_power, ylab="Global Active Power (kilowatts)", 
     xlab="", pch =".", type="l")
# Plot 4.2
plot(subdt$DateTime, subdt$Sub_metering_1,ylab="Energy sub metering", xlab="", type="l", col="black")
points(subdt$DateTime, subdt$Sub_metering_2, col="red", type="l")
points(subdt$DateTime, subdt$Sub_metering_3, col="blue", type="l")
legend("topright", lwd=1, col=c("black", "red", "blue"), legend=names(subdt[,7:9]), bty="n")
# Plot 4.3
plot(subdt$DateTime, subdt$Voltage, ylab="Voltage", xlab="datetime", type="l")
# Plot 4.4
plot(subdt$DateTime, subdt$Global_reactive_power, ylab="Global_reactive_power", xlab="datetime", type="l")
dev.off()

```

![Plot]( https://github.com/Mariia97/R_CourseKNU/blob/master/plot4.png)
