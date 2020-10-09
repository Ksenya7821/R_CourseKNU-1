### Install packages
```{r}
install.packages('rvest')
library('rvest')
```
### Create variable url
```{r}
Url <-("https://www.imdb.com/search/title/?count=100&release_date=2017,2017&title_ty")
```
### read the HTML code from the website
```{r}
webmovie <- read_html(Url)
webmovie

{html_document}
<html xmlns:og="http://ogp.me/ns#" xmlns:fb="http://www.facebook.com/2008/fbml">
[1] <head>\n<meta http-equiv="Content-Type"  ...
[2] <body id="styleguide-v2" class="fixed">\

```

### using CSS selectors for films ranking
```{r}
rank_html <- html_nodes(webmovie, '.text-primary')
rank_html

{xml_nodeset (100)}
 [1] <span class="lister-item-index unbol ...
 [2] <span class="lister-item-index unbol ...
 [3] <span class="lister-item-index unbol ...
 [4] <span class="lister-item-index unbol ...
 ...
```


### convert to text
```{r}
rank_data <- html_text(rank_html)
rank_data

[1] "1."   "2."   "3."   "4."   "5."  
  [6] "6."   "7."   "8."   "9."   "10." 
 [11] "11."  "12."  "13."  "14."  "15." 
 [16] "16."  "17."  "18."  "19."  "20." 
 [21] "21."  "22."  "23."  "24."  "25." 
 [26] "26."  "27."  "28."  "29."  "30." 
 [31] "31."  "32."  "33."  "34."  "35." 
 
 ```
 ### conver ranking to numerical format
 
 ```{r}
rank_data <- as.numeric(rank_data)
head(rank_data)

1 2 3 4 5 6
```

### using CSS selector fot titles
```
title_html <-html_nodes(webmovie, ".lister-item-header a")
```

### convert to the text
```{r}
title_data <-html_text(title_html)
head(title_data)

[1] "Пітьма"                 
[2] "Озарк"                  
[3] "Оповідь служниці"       
[4] "Паперовий будинок"      
[5] "Зоряний шлях: Дискавері"
[6] "Britannia"
```

### using CSS selector for runtime
```{r}
runtime_html <- html_nodes(webmovie, ".text-muted .runtime")
```

### convert to the text

```{r}
runtime_data <- html_text(runtime_html)
head(runtime_data)

[1] "60 min" "60 min" "60 min" "70 min"
[5] "60 min" "60 min"
```
### convert runtime to numeric
```{r}
runtime_data <- substr(runtime_data, 1, 3)
runtime_data <- as.numeric(runtime_data)
head(runtime_data)

60 60 60 70 60 60
```
### create dataframe
```{r}
movies<-data.frame(Rank = rank_data, Title = title_data, Runtime = runtime_data)
```

### Task 1 - show first 6 movies
```{r}
head(movies, n=6)

Rank                   Title Runtime
1    1                  Пітьма      60
2    2                   Озарк      60
3    3        Оповідь служниці      60
4    4       Паперовий будинок      70
5    5 Зоряний шлях: Дискавері      60
6    6               Britannia      60
```

### Task 2 - films with runtime more than 120 mins
```{r}
morethan120 <-subset(movies, Runtime > 120)
morethan120

Rank                                    Title Runtime
9     9             Той, хто біжить по лезу 2049     164
10   10                            Тор: Раґнарок     130
11   11                                     Воно     135
14   14                     Красуня і Чудовисько     129
28   28                   Назви мене своїм ім'ям     132
35   35 Пірати Карибського моря: Помста Салазара     129
36   36                      Вартові Галактики 2     136
38   38          Людина-павук: Повернення додому     133
39   39                  Kingsman: Золоте кільце     141
48   48                          Логан: Росомаха     137
49   49                               Диво-жінка     141
53   53                               Форма води     123
54   54                           Чужий: Заповіт     122
57   57  Зоряні війни: Епізод 8 - Останні Джедаї     152
59   59                               Джон Вік 2     122
60   60                                Гра Моллі     140
63   63                           Примарна нитка     130
68   68                Вбивство священного оленя     121
72   72               Король Артур: Легенда меча     126
82   82           Валеріан і місто тисячі планет     136
83   83             Трансформери: Останній лицар     154
84   84                                    Мати!     121
```

```{r}

library("dplyr")

mt120 <- movies %>% filter(Runtime > 120)
mt120
```

### Task 3 - count number of films with runtime less than 100 mins
```{r}
nrow(subset(movies, Runtime <100))

52
```
```{r}
count100 <-movies %>% filter(Runtime < 100) %>% count
count100

   n
1 52
```

 
