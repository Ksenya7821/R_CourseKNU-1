### Task 1-3
```{r}
prepare_set <- function(file_name) { 
  df <- read.csv(file_name, skip = 1, 
                 header = TRUE, encoding='UTF-8', 
                 stringsAsFactors = FALSE) 
   df}
 ```

Creat function with attributes
```{r}
answer3 <- function(file_name) { 
  df <- read.csv(file_name, skip = 1, 
                 header = TRUE, encoding='UTF-8', 
                 stringsAsFactors = FALSE) 
        names(df) <- c('Country', 'Summer', 'Gold', 'Silver', 'Bronze', 
                       'Total', 'Winter', 'Gold.1', 'Silver.1', 'Bronze.1', 'Total.1', 
                       'Games', 'Gold.2', 'Silver.2', 'Bronze.2', 'Combined.total')
        df}
 ```
 Creat variable
 ```{r}
olympics <- answer3("C:/mylib/olympics.csv")
olympics

head(olympics)
```
```{r}
                    Country Summer Gold Silver Bronze Total Winter Gold.1 Silver.1 Bronze.1 Total.1 Games Gold.2 Silver.2 Bronze.2 Combined.total
1         Afghanistan (AFG)     13    0      0      2     2      0      0        0        0       0    13      0        0        2              2
2             Algeria (ALG)     12    5      2      8    15      3      0        0        0       0    15      5        2        8             15
3           Argentina (ARG)     23   18     24     28    70     18      0        0        0       0    41     18       24       28             70
4             Armenia (ARM)      5    1      2      9    12      6      0        0        0       0    11      1        2        9             12
5   Australasia (ANZ) [ANZ]      2    3      4      5    12      0      0        0        0       0     2      3        4        5             12
6 Australia (AUS) [AUS] [Z]     25  139    152    177   468     18      5        3        4      12    43    144      155      181            480
```
### Task 4
Split Countries` name
```{r}
answer4 <- function(file_name) {
  df <- read.csv(file_name, skip = 1, header = TRUE,
                 encoding="UTF-8", stringsAsFactors = FALSE)
  names(df) <- c('Country', 'Summer', 'Gold', 'Silver', 'Bronze', 
                 'Total', 'Winter', 'Gold.1', 'Silver.1', 'Bronze.1', 'Total.1', 
                 'Games', 'Gold.2', 'Silver.2', 'Bronze.2', 'Combined.total')
  country_names <- strsplit(df$Country, "(", fixed = TRUE)
    df$Country <- sapply(country_names, "[", 1)
  df}
```
```{r}
olympics <- answer4("C:/mylib/olympics.csv")
olympics$Country 
```
```{r}
[1] "Afghanistan "                      "Algeria "                         
  [3] "Argentina "                        "Armenia "                         
  [5] "Australasia "                      "Australia "                       
  [7] "Austria "                          "Azerbaijan "                      
  [9] "Bahamas "                          "Bahrain "                         
 [11] "Barbados "                         "Belarus "                         
 [13] "Belgium "                          "Bermuda "                         
 [15] "Bohemia "                          "Botswana "                        
 [17] "Brazil "                           "British West Indies "             
 [19] "Bulgaria "                         "Burundi "                         
 [21] "Cameroon "                         "Canada "                          
 [23] "Chile "                            "China "                           
 [25] "Colombia "                         "Costa Rica "                      
 [27] "Ivory Coast "                      "Croatia "                         
 [29] "Cuba "                             "Cyprus "                          
 [31] "Czech Republic "                   "Czechoslovakia "                  
 [33] "Denmark "                          "Djibouti "                        
 [35] "Dominican Republic "               "Ecuador "                         
 [37] "Egypt "                            "Eritrea "                         
 [39] "Estonia "                          "Ethiopia "                        
 [41] "Finland "                          "France "                          
 [43] "Gabon "                            "Georgia "                         
 [45] "Germany "                          "United Team of Germany "          
 [47] "East Germany "                     "West Germany "                    
 [49] "Ghana "                            "Great Britain "                   
 [51] "Greece "                           "Grenada "                         
 [53] "Guatemala "                        "Guyana "                          
 [55] "Haiti "                            "Hong Kong "                       
 [57] "Hungary "                          "Iceland "                         
 [59] "India "                            "Indonesia "                       
 [61] "Iran "                             "Iraq "                            
 [63] "Ireland "                          "Israel "                          
 [65] "Italy "                            "Jamaica "                         
 [67] "Japan "                            "Kazakhstan "                      
 [69] "Kenya "                            "North Korea "                     
 [71] "South Korea "                      "Kuwait "                          
 [73] "Kyrgyzstan "                       "Latvia "                          
 [75] "Lebanon "                          "Liechtenstein "                   
 [77] "Lithuania "                        "Luxembourg "                      
 [79] "Macedonia "                        "Malaysia "                        
 [81] "Mauritius "                        "Mexico "                          
 [83] "Moldova "                          "Mongolia "                        
 [85] "Montenegro "                       "Morocco "                         
 [87] "Mozambique "                       "Namibia "                         
 [89] "Netherlands "                      "Netherlands Antilles "            
 [91] "New Zealand "                      "Niger "                           
 [93] "Nigeria "                          "Norway "                          
 [95] "Pakistan "                         "Panama "                          
 [97] "Paraguay "                         "Peru "                            
 [99] "Philippines "                      "Poland "                          
[101] "Portugal "                         "Puerto Rico "                     
[103] "Qatar "                            "Romania "                         
[105] "Russia "                           "Russian Empire "                  
[107] "Soviet Union "                     "Unified Team "                    
[109] "Saudi Arabia "                     "Senegal "                         
[111] "Serbia "                           "Serbia and Montenegro "           
[113] "Singapore "                        "Slovakia "                        
[115] "Slovenia "                         "South Africa "                    
[117] "Spain "                            "Sri Lanka "                       
[119] "Sudan "                            "Suriname "                        
[121] "Sweden "                           "Switzerland "                     
[123] "Syria "                            "Chinese Taipei "                  
[125] "Tajikistan "                       "Tanzania "                        
[127] "Thailand "                         "Togo "                            
[129] "Tonga "                            "Trinidad and Tobago "             
[131] "Tunisia "                          "Turkey "                          
[133] "Uganda "                           "Ukraine "                         
[135] "United Arab Emirates "             "United States "                   
[137] "Uruguay "                          "Uzbekistan "                      
[139] "Venezuela "                        "Vietnam "                         
[141] "Virgin Islands "                   "Yugoslavia "                      
[143] "Independent Olympic Participants " "Zambia "                          
[145] "Zimbabwe "                         "Mixed team "                      
[147] "Totals"                           

```
### Task 5
```{r}
answer5 <- function(file_name) {
  df <- read.csv(file_name, skip = 1, header = TRUE,
                 encoding="UTF-8", stringsAsFactors = FALSE)
  names(df) <- c('Country', 'Summer', 'Gold', 'Silver', 'Bronze', 
                 'Total', 'Winter', 'Gold.1', 'Silver.1', 'Bronze.1', 'Total.1', 
                 'Games', 'Gold.2', 'Silver.2', 'Bronze.2', 'Combined.total')
  country_names <- strsplit(df$Country, "(", fixed = TRUE)
  df$Country <- sapply(country_names, "[", 1)
  df$ID <- substr(sapply(country_names, '[', 2), 1,3)
 df}
```

```{r}
olympics <- answer5("C:/mylib/olympics.csv")
head(olympics)
```
```{r}
      Country Summer Gold Silver Bronze Total Winter Gold.1 Silver.1 Bronze.1 Total.1 Games Gold.2 Silver.2 Bronze.2 Combined.total  ID
1 Afghanistan      13    0      0      2     2      0      0        0        0       0    13      0        0        2              2 AFG
2     Algeria      12    5      2      8    15      3      0        0        0       0    15      5        2        8             15 ALG
3   Argentina      23   18     24     28    70     18      0        0        0       0    41     18       24       28             70 ARG
4     Armenia       5    1      2      9    12      6      0        0        0       0    11      1        2        9             12 ARM
5 Australasia       2    3      4      5    12      0      0        0        0       0     2      3        4        5             12 ANZ
6   Australia      25  139    152    177   468     18      5        3        4      12    43    144      155      181            480 AUS
```

### Task 6
```{r}
answer6 <- function(file_name) {
  df <- read.csv(file_name, skip = 1, header = TRUE,
                 encoding="UTF-8", stringsAsFactors = FALSE)
  names(df) <- c('Country', 'Summer', 'Gold', 'Silver', 'Bronze', 
                 'Total', 'Winter', 'Gold.1', 'Silver.1', 'Bronze.1', 'Total.1', 
                 'Games', 'Gold.2', 'Silver.2', 'Bronze.2', 'Combined.total')
  country_names <- strsplit(df$Country, "(", fixed = TRUE)
  df$Country <- sapply(country_names, "[", 1)
  df$ID <- substr(sapply(country_names, '[', 2), 1,3)
  df <- df[-which(df$Country == 'Totals'), ]
  df}
```
```{r}
olympics <- answer6("C:/mylib/olympics.csv")
head(olympics)
```
  
  


