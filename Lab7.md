
```{r}
prepare_set <- function(file_name) { 
  df <- read.csv(file_name, skip = 1, 
                 header = TRUE, encoding='UTF-8', 
                 stringsAsFactors = FALSE) 
        names(df) <- c('Country', 'Summer', 'Gold', 'Silver', 'Bronze', 
                       'Total', 'Winter', 'Gold.1', 'Silver.1', 'Bronze.1', 'Total.1', 
                       'Games', 'Gold.2', 'Silver.2', 'Bronze.2', 'Combined.total')
        df}
 ```
 
 
