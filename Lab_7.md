### Data preperation
Load the NEI and SCC data frames
```{r}
NEI <- readRDS("summarySCC_PM25.rds")
SCC <- readRDS("Source_Classification_Code.rds")
```
Reading names of the columns
```{r}
names(NEI)
```
"fips"      "SCC"       "Pollutant" "Emissions" "type"      "year" 

```{r}
names(SCC)
```
[1] "SCC"                 "Data.Category"       "Short.Name"         
 [4] "EI.Sector"           "Option.Group"        "Option.Set"         
 [7] "SCC.Level.One"       "SCC.Level.Two"       "SCC.Level.Three"    
[10] "SCC.Level.Four"      "Map.To"              "Last.Inventory.Year"
[13] "Created_Date"        "Revised_Date"        "Usage.Notes"  

Data about emissins is in NEI data set

## Question 1
### Find total amount of PM2.5 emissions by year
```{r}
library("dplyr")
df1 <- NEI %>% group_by(year)%>%summarise(Total=sum(Emissions))
par(mar = rep(2, 4))
barplot((df1$Total/10^6), names.arg=df1$year, xlab = "Year", ylab = "PM2.5 Emissions (million Tons)",
        main="Total PM2.5 Emissions From All US Sources")
```
![Plot]( https://github.com/Mariia97/R_CourseKNU/blob/master/Rplot1.png)

Total emissions from PM2.5 have decreased in the US, from 1999 to 2008.

## Question 2
```{r}
df2 <- NEI %>% group_by(year)%>%filter(fips=="24510")%>%summarise(Total=sum(Emissions))
par(mar = rep(2, 4))
barplot(df2$Total, names.arg=df2$year, xlab = "Year", ylab = "PM2.5 Emissions (Tons)",
        main="Total PM2.5 Emissions From All Baltimore City Sources")
```
![Plot]( https://github.com/Mariia97/R_CourseKNU/blob/master/Rplot2.png)

Overall, total emissions from PM2.5 have decreased in Baltimore City, Maryland, from 1999 to 2008.

## Question 3

```{r}
library('ggplot2')

df3 <- NEI%>%select(year, Emissions, type, fips)%>%filter(fips=="24510")%>% group_by(year, type)%>%summarise(Total=sum(Emissions))

ggplot(df3, aes(factor(year), Total, fill=factor(type))) +
  geom_bar(stat="identity")  +  facet_grid(~type) + guides(fill=FALSE)+ 
  labs(x="year", y=expression("Total PM2.5 Emission (Tons)")) + 
  labs(title=expression("PM2.5 Emissions in Baltimore City 1999-2008 by Source Type"))
```
![Plot]( https://github.com/Mariia97/R_CourseKNU/blob/master/Rplot3.png)

Non-road, nonpoint, on-road source types have decreased emissions overall from 1999-2008 in Baltimore City.

## Question 4

```{r}
combustion <- grepl("comb", SCC$SCC.Level.One, ignore.case=TRUE)
coal<- grepl("coal", SCC$SCC.Level.Four, ignore.case=TRUE) 
coalCombustion <- (combustion & coal)
combustionSCC <- SCC[coalCombustion,]$SCC
df4 <- NEI[NEI$SCC %in% combustionSCC,]

ggplot(df4, aes(factor(year), (Emissions/10^6))) +
  geom_bar(stat="identity") +
  labs(x="year", y=expression("Total PM2.5 Emission (million Tons)")) + 
  labs(title=expression("PM2.5 Coal Combustion Source Emissions Across US from 1999-2008"))
```
![Plot]( https://github.com/Mariia97/R_CourseKNU/blob/master/Rplot4.png)

Emissions from coal combustion related sources have decreased.

## Question 5
```{r}
vehicles <- grepl("vehicle", SCC$SCC.Level.Two, ignore.case=TRUE)
vehiclesSCC <- SCC[vehicles,]$SCC
vehiclesNEI <- NEI[NEI$SCC %in% vehiclesSCC,]
df5 <- vehiclesNEI[vehiclesNEI$fips=="24510",]

ggplot(df5, aes(factor(year), Emissions)) +
  geom_bar(stat="identity") +
  labs(x="year", y=expression("Total PM2.5 Emission (Tons)")) + 
  labs(title=expression("PM2.5 Vehicle Source Emissions in Baltimore City from 1999-2008"))
 ```
 ![Plot]( https://github.com/Mariia97/R_CourseKNU/blob/master/Rplot5.png)

Emissions from vehicle related sources have decreased in Baltimore from 1999-2008.

## Question 6
```{r}
df5$city <- "Baltimore City"
df6 <- vehiclesNEI[vehiclesNEI$fips=="06037",]
df6$city <- "Los Angeles"
df7 <- rbind(df5,df6)


ggplot(df7, aes(factor(year), Emissions, fill=factor(city))) +
  geom_bar(stat="identity")  +  facet_grid(~city) + guides(fill=FALSE)+ 
  labs(x="year", y=expression("Total PM2.5 Emission (Tons)")) + 
  labs(title=expression("Vehicle Source Emissions in Baltimore and LA, 1999-2008"))
 ```
![Plot]( https://github.com/Mariia97/R_CourseKNU/blob/master/Rplot6.png)
