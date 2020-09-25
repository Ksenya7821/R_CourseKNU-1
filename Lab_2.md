### Task 1
Download file


### Task 2
Install R package
```{r}
install.packages("BiocManager")
BiocManager::install("rhdf5")
library("rhdf5")
```

### Task 3
View file
```{r}
setwd("c:/RLab")

h5ls("H-H1_LOSC_C00_4_V1-1187006834-4096.hdf5")
```

### Task 4
Measures

```{r}
strain <- h5read("H-H1_LOSC_C00_4_V1-1187006834-4096.hdf5", "strain/Strain")
H5close()
```
### Task 5
```{r}
st <- h5readAttributes(file="H-H1_LOSC_C00_4_V1-1187006834-4096.hdf5", name="strain/Strain")$Xspacing
st
```
 0.0002441406

### Task 6
```{r}
gpsStart <- h5read("H-H1_LOSC_C00_4_V1-1187006834-4096.hdf5", "meta/GPSstart")
gpsStart
```
1187006834

```{r}
duration <- h5read("H-H1_LOSC_C00_4_V1-1187006834-4096.hdf5", "meta/Duration")
duration
```
 4096

### Task 7
```{r}
gpsEnd <- gpsStart + duration
gpsEnd
```
1187010930

### Task 8
```{r}
myTime <- seq(gpsStart, gpsEnd, st)
myTime
```
```{r}
[1] 1187006834 1187006834 1187006834 1187006834 1187006834 1187006834 1187006834
   [8] 1187006834 1187006834 1187006834 1187006834 1187006834 1187006834 1187006834
  [15] 1187006834 1187006834 1187006834 1187006834 1187006834 1187006834 1187006834
  [22] 1187006834 1187006834 1187006834 1187006834 1187006834 1187006834 1187006834
  [29] 1187006834 1187006834 1187006834 1187006834 1187006834 1187006834 1187006834
  [36] 1187006834 1187006834 1187006834 1187006834 1187006834 1187006834 1187006834
  [43] 1187006834 1187006834 1187006834 1187006834 1187006834 1187006834 1187006834
  .................................................................................
 [995] 1187006834 1187006834 1187006834 1187006834 1187006834 1187006834
 ```

### Task 9
```{r}
numSamples <- 1000000
```


### Task 10
```{r}
plot(myTime[0:numSamples], strain[0:numSamples], type = "l", xlab = "GPS Time (s)", ylab = "H1 Strain")
```
