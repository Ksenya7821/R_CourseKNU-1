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

```
![Plot]( https://github.com/Mariia97/R_CourseKNU/blob/master/Rplot3.png)


