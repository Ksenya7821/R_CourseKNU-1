### Prepare set
```{r}
df <- read.csv("C:/mylib/olympics.csv", skip = 1, 
               header = TRUE, encoding='UTF-8', 
               stringsAsFactors = FALSE) 
df
```

```{r}
                                    X X..Summer X01.. X02.. X03.. Total X..Winter X01...1 X02...1 X03...1 Total.1 X..Games X01...2 X02...2 X03...2 Combined.total
1                   Afghanistan (AFG)        13     0     0     2     2         0       0       0       0       0       13       0       0       2              2
2                       Algeria (ALG)        12     5     2     8    15         3       0       0       0       0       15       5       2       8             15
3                     Argentina (ARG)        23    18    24    28    70        18       0       0       0       0       41      18      24      28             70
4                       Armenia (ARM)         5     1     2     9    12         6       0       0       0       0       11       1       2       9             12
5             Australasia (ANZ) [ANZ]         2     3     4     5    12         0       0       0       0       0        2       3       4       5             12
6           Australia (AUS) [AUS] [Z]        25   139   152   177   468        18       5       3       4      12       43     144     155     181            480
7                       Austria (AUT)        26    18    33    35    86        22      59      78      81     218       48      77     111     116            304
8                    Azerbaijan (AZE)         5     6     5    15    26         5       0       0       0       0       10       6       5      15             26
9                       Bahamas (BAH)        15     5     2     5    12         0       0       0       0       0       15       5       2       5             12
10                      Bahrain (BRN)         8     0     0     1     1         0       0       0       0       0        8       0       0       1              1
11               Barbados (BAR) [BAR]        11     0     0     1     1         0       0       0       0       0       11       0       0       1              1
12                      Belarus (BLR)         5    12    24    39    75         6       6       4       5      15       11      18      28      44             90
13                      Belgium (BEL)        25    37    52    53   142        20       1       1       3       5       45      38      53      56            147
14                      Bermuda (BER)        17     0     0     1     1         7       0       0       0       0       24       0       0       1              1
15            Bohemia (BOH) [BOH] [Z]         3     0     1     3     4         0       0       0       0       0        3       0       1       3              4
16                     Botswana (BOT)         9     0     1     0     1         0       0       0       0       0        9       0       1       0              1
17                       Brazil (BRA)        21    23    30    55   108         7       0       0       0       0       28      23      30      55            108
18    British West Indies (BWI) [BWI]         1     0     0     2     2         0       0       0       0       0        1       0       0       2              2
19                 Bulgaria (BUL) [H]        19    51    85    78   214        19       1       2       3       6       38      52      87      81            220
20                      Burundi (BDI)         5     1     0     0     1         0       0       0       0       0        5       1       0       0              1
21                     Cameroon (CMR)        13     3     1     1     5         1       0       0       0       0       14       3       1       1              5
22                       Canada (CAN)        25    59    99   121   279        22      62      56      52     170       47     121     155     173            449
23                    Chile (CHI) [I]        22     2     7     4    13        16       0       0       0       0       38       2       7       4             13
24                  China (CHN) [CHN]         9   201   146   126   473        10      12      22      19      53       19     213     168     145            526
25                     Colombia (COL)        18     2     6    11    19         1       0       0       0       0       19       2       6      11             19
26                   Costa Rica (CRC)        14     1     1     2     4         6       0       0       0       0       20       1       1       2              4
27            Ivory Coast (CIV) [CIV]        12     0     1     0     1         0       0       0       0       0       12       0       1       0              1
28                      Croatia (CRO)         6     6     7    10    23         7       4       6       1      11       13      10      13      11             34
29                     Cuba (CUB) [Z]        19    72    67    70   209         0       0       0       0       0       19      72      67      70            209
30                       Cyprus (CYP)         9     0     1     0     1        10       0       0       0       0       19       0       1       0              1
31         Czech Republic (CZE) [CZE]         5    14    15    15    44         6       7       9       8      24       11      21      24      23             68
32         Czechoslovakia (TCH) [TCH]        16    49    49    45   143        16       2       8      15      25       32      51      57      60            168
33                  Denmark (DEN) [Z]        26    43    68    68   179        13       0       1       0       1       39      43      69      68            180
34                 Djibouti (DJI) [B]         7     0     0     1     1         0       0       0       0       0        7       0       0       1              1
35           Dominican Republic (DOM)        13     3     2     1     6         0       0       0       0       0       13       3       2       1              6
36                      Ecuador (ECU)        13     1     1     0     2         0       0       0       0       0       13       1       1       0              2
37              Egypt (EGY) [EGY] [Z]        21     7     9    10    26         1       0       0       0       0       22       7       9      10             26
38                      Eritrea (ERI)         4     0     0     1     1         0       0       0       0       0        4       0       0       1              1
39                      Estonia (EST)        11     9     9    15    33         9       4       2       1       7       20      13      11      16             40
40                     Ethiopia (ETH)        12    21     7    17    45         2       0       0       0       0       14      21       7      17             45
41                      Finland (FIN)        24   101    84   117   302        22      42      62      57     161       46     143     146     174            463
42           France (FRA) [O] [P] [Z]        27   202   223   246   671        22      31      31      47     109       49     233     254     293            780
43                        Gabon (GAB)         9     0     1     0     1         0       0       0       0       0        9       0       1       0              1
44                      Georgia (GEO)         5     6     5    14    25         6       0       0       0       0       11       6       5      14             25
45            Germany (GER) [GER] [Z]        15   174   182   217   573        11      78      78      53     209       26     252     260     270            782
46 United Team of Germany (EUA) [EUA]         3    28    54    36   118         3       8       6       5      19        6      36      60      41            137
47           East Germany (GDR) [GDR]         5   153   129   127   409         6      39      36      35     110       11     192     165     162            519
48           West Germany (FRG) [FRG]         5    56    67    81   204         6      11      15      13      39       11      67      82      94            243
49                  Ghana (GHA) [GHA]        13     0     1     3     4         1       0       0       0       0       14       0       1       3              4
50      Great Britain (GBR) [GBR] [Z]        27   236   272   272   780        22      10       4      12      26       49     246     276     284            806
51                   Greece (GRE) [Z]        27    30    42    39   111        18       0       0       0       0       45      30      42      39            111
52                      Grenada (GRN)         8     1     0     0     1         0       0       0       0       0        8       1       0       0              1
53                    Guatemala (GUA)        13     0     1     0     1         1       0       0       0       0       14       0       1       0              1
54                 Guyana (GUY) [GUY]        16     0     0     1     1         0       0       0       0       0       16       0       0       1              1
55                    Haiti (HAI) [J]        14     0     1     1     2         0       0       0       0       0       14       0       1       1              2
56              Hong Kong (HKG) [HKG]        15     1     1     1     3         4       0       0       0       0       19       1       1       1              3
57                      Hungary (HUN)        25   167   144   165   476        22       0       2       4       6       47     167     146     169            482
58                      Iceland (ISL)        19     0     2     2     4        17       0       0       0       0       36       0       2       2              4
59                    India (IND) [F]        23     9     6    11    26         9       0       0       0       0       32       9       6      11             26
60                    Indonesia (INA)        14     6    10    11    27         0       0       0       0       0       14       6      10      11             27
61                     Iran (IRI) [K]        15    15    20    25    60        10       0       0       0       0       25      15      20      25             60
62                         Iraq (IRQ)        13     0     0     1     1         0       0       0       0       0       13       0       0       1              1
 [ reached 'max' / getOption("max.print") -- omitted 85 rows ]
 ```
 

```{r}
prepare_set <- function(file_name) { 
  df <- read.csv(file_name, skip = 1, 
                 header = TRUE, encoding='UTF-8', 
                 stringsAsFactors = FALSE) 
  names(df) <- 'Country'
               t<- length(colnames(df[1]))
               for (i in 1:t) {
                 colnames(df)=sub("X..", "", colnames(df), fixed=TRUE)
                 colnames(df)=sub("X01..", "Gold", colnames(df))
                 colnames(df)=sub("X02..", "Silver", colnames(df))
                 colnames(df)=sub("X03..", "Bronze", colnames(df))
               }
  country_names <- strsplit(df$Country, "(", fixed = TRUE)
  df$Country <- sapply(country_names, "[", 1)
  df$ID <- substr(sapply(country_names, '[', 2), 1,3)
  df <- df[-which(df$Country == 'Totals'), ]
  df}
  ```
 ### Question 1
What country has the greates number of gold medals in summer games? 
```{r}
answer1<-function() {
olympics[which.max(olympics$Gold), "Country"]
}
answer1()
```
Answer:
"United States"
  
### Question 2
What country has the maximum difference between number of medals in Summer and Winter games?

```{r}
answer2<-function() {
  olympics[which.max(olympics$Total-olympics$Total.1), "Country"]
}
answer2()
```

Answer:
"United States"

### Question 3
Which country has the maximum value of (Summer Gold - Winter Gold) / Total Gold?

```{r}

answer3<-function() {
  my_subset<-subset(olympics, Gold>=1 & Gold.1>=1)
  my_subset[which.max((my_subset$Gold-my_subset$Gold.1)/my_subset$Gold.2), "Country"]
}
answer3()
```

Answer:
"Bulgaria "

### Question 4
Count number of points for each country

```{r}
answer4<-function() {
  olympics$Points<-(olympics$Gold.2*3 + olympics$Silver.2*2 + olympics$Bronze.2*1)
  olympics[, c("Country", "Points")]
  }

head(answer4())
```

Answer:
```{r}
       Country Points
1 Afghanistan       2
2     Algeria      27
3   Argentina     130
4     Armenia      16
5 Australasia      22
6   Australia     923
```

### Part 2
```{r}
census <- read.csv("C:/mylib/census.csv", stringsAsFactors = FALSE)
census
```

```{r}
SUMLEV REGION DIVISION STATE COUNTY  STNAME         CTYNAME CENSUS2010POP ESTIMATESBASE2010 POPESTIMATE2010 POPESTIMATE2011 POPESTIMATE2012 POPESTIMATE2013
1      40      3        6     1      0 Alabama         Alabama       4779736           4780127         4785161         4801108         4816089         4830533
2      50      3        6     1      1 Alabama  Autauga County         54571             54571           54660           55253           55175           55038
3      50      3        6     1      3 Alabama  Baldwin County        182265            182265          183193          186659          190396          195126
4      50      3        6     1      5 Alabama  Barbour County         27457             27457           27341           27226           27159           26973
5      50      3        6     1      7 Alabama     Bibb County         22915             22919           22861           22733           22642           22512
6      50      3        6     1      9 Alabama   Blount County         57322             57322           57373           57711           57776           57734
7      50      3        6     1     11 Alabama  Bullock County         10914             10915           10887           10629           10606           10628
8      50      3        6     1     13 Alabama   Butler County         20947             20946           20944           20673           20408           20261
9      50      3        6     1     15 Alabama  Calhoun County        118572            118586          118437          117768          117286          116575
10     50      3        6     1     17 Alabama Chambers County         34215             34170           34098           33993           34075           34153
   POPESTIMATE2014 POPESTIMATE2015 NPOPCHG_2010 NPOPCHG_2011 NPOPCHG_2012 NPOPCHG_2013 NPOPCHG_2014 NPOPCHG_2015 BIRTHS2010 BIRTHS2011 BIRTHS2012 BIRTHS2013
1          4846411         4858979         5034        15947        14981        14444        15878        12568      14226      59689      59062      57938
2            55290           55347           89          593          -78         -137          252           57        151        636        615        574
3           199713          203709          928         3466         3737         4730         4587         3996        517       2187       2092       2160
4            26815           26489         -116         -115          -67         -186         -158         -326         70        335        300        283
5            22549           22583          -58         -128          -91         -130           37           34         44        266        245        259
6            57658           57673           51          338           65          -42          -76           15        183        744        710        646
7            10829           10696          -28         -258          -23           22          201         -133         39        169        122        132
8            20276           20154           -2         -271         -265         -147           15         -122         65        276        241        240
9           115993          115620         -149         -669         -482         -711         -582         -373        317       1382       1357       1309
10           34052           34123          -72         -105           82           78         -101           71         81        401        393        404
   BIRTHS2014 BIRTHS2015 DEATHS2010 DEATHS2011 DEATHS2012 DEATHS2013 DEATHS2014 DEATHS2015 NATURALINC2010 NATURALINC2011 NATURALINC2012 NATURALINC2013 NATURALINC2014
1       58334      58305      11089      48811      48357      50843      50228      50330           3137          10878          10705           7095           8106
2         623        600        152        507        558        583        504        467             -1            129             57             -9            119
3        2186       2240        532       1825       1879       1902       2044       1992            -15            362            213            258            142
4         260        269        128        319        291        294        310        309            -58             16              9            -11            -50
5         247        253         34        278        237        281        211        223             10            -12              8            -22             36
6         618        603        133        570        592        585        589        590             50            174            118             61             29
7         118        123         52        132        116        120         99        109            -13             37              6             12             19
8         267        257         60        261        271        261        265        236              5             15            -30            -21              2
9        1355       1335        312       1326       1357       1412       1407       1395              5             56              0           -103            -52
10        421        429         80        441        475        452        491        457              1            -40            -82            -48            -70
   NATURALINC2015 INTERNATIONALMIG2010 INTERNATIONALMIG2011 INTERNATIONALMIG2012 INTERNATIONALMIG2013 INTERNATIONALMIG2014 INTERNATIONALMIG2015 DOMESTICMIG2010
1            7975                 1357                 4926                 4904                 4834                 5529                 5726             537
2             133                   33                   20                   16                   16                   18                   19              49
3             248                   69                  187                  172                  170                  212                  221             856
4             -40                    2                   -4                   -7                   -3                   -2                    0             -62
5              30                    2                   10                   16                   18                   21                   21             -69
6              13                    5                    3                   19                   20                   28                   28              -3
7              14                    7                   21                   25                   28                   31                   32             -23
8              21                    0                    2                    2                    2                    2                    2              -5
9             -60                    6                   43                   61                   54                   64                   66            -155
10            -28                    7                   31                   29                   31                   34                   34             -74
   DOMESTICMIG2011 DOMESTICMIG2012 DOMESTICMIG2013 DOMESTICMIG2014 DOMESTICMIG2015 NETMIG2010 NETMIG2011 NETMIG2012 NETMIG2013 NETMIG2014 NETMIG2015 RESIDUAL2010
1               11            -929            1838            2816           -2268       1894       4937       3975       6672       8345       3458            3
2              398            -161            -166             125            -140         82        418       -145       -150        143       -121            8
3             2743            3327            4211            3799            3469        925       2930       3499       4381       4011       3690           18
4             -129             -68            -191            -105            -281        -60       -133        -75       -194       -107       -281            2
5             -126            -115            -140              -4               4        -67       -116        -99       -122         17         25           -1
6              104             -68            -101            -119             -79          2        107        -49        -81        -91        -51           -1
7             -333             -55             -12             154            -174        -16       -312        -30         16        185       -142            1
8             -292            -240            -115              22            -132         -5       -290       -238       -113         24       -130           -2
9             -727            -542            -646            -519            -391       -149       -684       -481       -592       -455       -325           -5
10             -93             131              98             -78              46        -67        -62        160        129        -44         80           -6
   RESIDUAL2011 RESIDUAL2012 RESIDUAL2013 RESIDUAL2014 RESIDUAL2015 GQESTIMATESBASE2010 GQESTIMATES2010 GQESTIMATES2011 GQESTIMATES2012 GQESTIMATES2013
1           132          301          677         -573         1135              116185          116212          115560          115666          116963
2            46           10           22          -10           45                 455             455             455             455             455
3           174           25           91          434           58                2307            2307            2307            2249            2304
4             2           -1           19           -1           -5                3193            3193            3382            3388            3389
5             0            0           14          -16          -21                2224            2224            2224            2224            2224
6            57           -4          -22          -14           53                 489             489             489             489             489
7            17            1           -6           -3           -5                1690            1690            1690            1777            1715
8             4            3          -13          -11          -13                 333             333             333             333             333
9           -41           -1          -16          -75           12                2933            2934            2882            2958            2812
10           -3            4           -3           13           19                 458             458             458             458             458
   GQESTIMATES2014 GQESTIMATES2015 RBIRTH2011 RBIRTH2012 RBIRTH2013 RBIRTH2014 RBIRTH2015 RDEATH2011 RDEATH2012 RDEATH2013 RDEATH2014 RDEATH2015 RNATURALINC2011
1           119088          119599   12.45302   12.28258   12.01208  12.056286   12.01497  10.183524  10.056360  10.541099  10.380963  10.371556       2.2694961
2              455             455   11.57279   11.13848   10.41619  11.293597   10.84628   9.225478  10.106133  10.579514   9.136393   8.442022       2.3473111
3             2308            2309   11.82635   11.09652   11.20559  11.072868   11.10500   9.868812   9.966716   9.867141  10.353587   9.875515       1.9575398
4             3353            3352   12.27848   11.03245   10.45592   9.667584   10.09305  11.692048  10.701480  10.862337  11.526735  11.593877       0.5864350
5             2233            2236   11.66820   10.79890   11.47185  10.962917   11.21156  12.194587  10.446281  12.446295   9.365083   9.882124      -0.5263851
6              489             489   12.92969   12.29576   11.18518  10.711314   10.45686   9.905808  10.252236  10.128993  10.208680  10.231421       3.0238782
7             1757            1757   15.70924   11.49046   12.43289  10.998742   11.42857  12.269939  10.925359  11.302628   9.227758  10.127758       3.4393010
8              333             333   13.26381   11.73292   11.80260  13.173150   12.71333  12.542951  13.193447  12.835329  13.074475  11.674499       0.7208593
9             2797            2804   11.70170   11.54628   11.19468  11.652506   11.52785  11.227535  11.546283  12.075549  12.099687  12.045956       0.4741644
10             458             458   11.77836   11.54728   11.84265  12.345136   12.58526  12.953254  13.956632  13.249692  14.397771  13.406674      -1.1748983
   RNATURALINC2012 RNATURALINC2013 RNATURALINC2014 RNATURALINC2015 RINTERNATIONALMIG2011 RINTERNATIONALMIG2012 RINTERNATIONALMIG2013 RINTERNATIONALMIG2014
1        2.2262204       1.4709812      1.67532229       1.6434167            1.02771996            1.01983977            1.00221611            1.14271613
2        1.0323469      -0.1633201      2.15720397       2.4042590            0.36392419            0.28978158            0.29034687            0.32629976
3        1.1298086       1.3384450      0.71928052       1.2294818            1.01121530            0.91233374            0.88192114            1.07385542
4        0.3309736      -0.4064140     -1.85915074      -1.5008255           -0.14660876           -0.25742392           -0.11084017           -0.07436603
5        0.3526171      -0.9744430      1.59783405       1.3294337            0.43865421            0.70523416            0.79727156            0.93206986
6        2.0435200       1.0561856      0.50263450       0.2254381            0.05213583            0.32904136            0.34629036            0.48530227
7        0.5651048       1.1302628      1.77098383       1.3008130            1.95203569            2.35460325            2.63727983            2.88949993
8       -1.4605292      -1.0327276      0.09867528       1.0388326            0.09611457            0.09736861            0.09835501            0.09867528
9        0.0000000      -0.8808651     -0.44718104      -0.5181056            0.36409051            0.51902967            0.46181279            0.55037666
10      -2.4093554      -1.4070470     -2.05263544      -0.8214155            0.91054618            0.85208909            0.90871783            0.99699436
   RINTERNATIONALMIG2015 RDOMESTICMIG2011 RDOMESTICMIG2012 RDOMESTICMIG2013 RDOMESTICMIG2014 RDOMESTICMIG2015 RNETMIG2011 RNETMIG2012 RNETMIG2013 RNETMIG2014
1             1.17996289      0.002294949       -0.1931956         0.381066        0.5820019       -0.4673692    1.030015   0.8266442    1.383282   1.7247181
2             0.34346557      7.242091472       -2.9159271        -3.012349        2.2659706       -2.5307989    7.606016  -2.6261455   -2.722002   2.5922703
3             1.09562691     14.832960211       17.6472928        21.845705       19.2432865       17.1978722   15.844176  18.5596266   22.727626  20.3171419
4             0.00000000     -4.728132388       -2.5006895        -7.056824       -3.9042166      -10.5432988   -4.874741  -2.7581135   -7.167664  -3.9785826
5             0.93060356     -5.527043032       -5.0688705        -6.201001       -0.1775371        0.1772578   -5.088389  -4.3636364   -5.403729   0.7545327
6             0.48555896      1.807375482       -1.1776217        -1.748766       -2.0625347       -1.3699699    1.859511  -0.8485804   -1.402476  -1.5772324
7             2.97328688    -30.953708870       -5.1801271        -1.130263       14.3542900      -16.1672474  -29.001673  -2.8255239    1.507017  17.2437899
8             0.09893643    -14.032727010      -11.6842336        -5.655413        1.0854281       -6.5298046  -13.936612 -11.5868650   -5.557058   1.1841034
9             0.56991620     -6.155669863       -4.6117062        -5.524649       -4.4632108       -3.3763217   -5.791579  -4.0926766   -5.062836  -3.9128341
10            0.99743308     -2.731638543        3.8490921         2.872721       -2.2872223        1.3494683   -1.821092   4.7011812    3.781439  -1.2902280
   RNETMIG2015
1    0.7125937
2   -2.1873334
3   18.2934991
4  -10.5432988
5    1.1078614
6   -0.8844110
7  -13.1939605
8   -6.4308682
9   -2.8064055
10   2.3469014
 [ reached 'max' / getOption("max.print") -- omitted 3183 rows ]
```

### Question 5
What state has the greates number of countrie?
```{r}
answer5<-function() {
  census_gr<-split(census[ , "CTYNAME"], census[ , "STNAME"])
  ncounty<-sapply(census_gr, length)
  which.max(ncounty)
}

answer5()
```

Answer:
Texas 
   44
   
 ### Question 6
 Three the most populated states
 
 
 ```{r}
 answer6<-function() {
  order_df<-census[order(census$STNAME, -census$CENSUS2010POP), ]
  df_split<-split(order_df, order_df$STNAME)
  df_split<-lapply(df_split, function (x) sum (x[2:4, "CENSUS2010POP"]))
  df_split<-df_split[order(unlist(df_split), decreasing = TRUE, na.last = TRUE)]
  names(df_split) [1:3]
}
answer6() 
 ```
 
Answer:
 "California" "Texas"      "Illinois"  
 
 ### Question 7
 
 ```{r}
 answer7<-function() {
  population<-census[, 10:15]
  popul_max<-apply(population, 1, max)
  popul_min<-apply(population, 1, min)
  popul_chg<-(popul_max-popul_min)
  population<-cbind(CTYNAME = census$CTYNAME, popul_chg)
  population[which.max(popul_chg)]
}
answer7()
 ```
 
Answer:
 "Texas"
 ### Question 8
  Create function that finds countries from regions 1 and 2, for which name starts with "Washington" and POPESTIMATE2015 greater than  POPESTIMATE2014.
  
  ```{r}
  answer8 <- function() {
  subset_1<-subset(census, (REGION==1 | REGION==2))
  subset_2<-subset_1[grep("Washington", subset_1$CTYNAME),]
  subset_3<-subset(subset_2, POPESTIMATE2015>POPESTIMATE2014)
  subset_3[ , c("STNAME", "CTYNAME")]
}
answer8() 
```

Answer:
```{r}
          STNAME           CTYNAME
897          Iowa Washington County
1420    Minnesota Washington County
2346 Pennsylvania Washington County
2356 Rhode Island Washington County
3164    Wisconsin Washington County
```
  
 
  
