### Create connection
```{r}

library('DBI')

install.packages("RSQLite")

library('RSQLite')
conn <- dbConnect(RSQLite::SQLite(), "C://Users//HP//Downloads//database.sqlite")
```

### Task 1
```{r}
res <- dbSendQuery(conn, "SELECT Title, EventType FROM Papers WHERE EventType='Spotlight' ORDER BY Title")
df_title <- dbFetch(res, n=10)
df_title

Title EventType
1  A Tractable Approximation to Optimal Point Process Filtering: Application to Neural Encoding Spotlight
2                                    Accelerated Mirror Descent in Continuous and Discrete Time Spotlight
3                        Action-Conditional Video Prediction using Deep Networks in Atari Games Spotlight
4                                                                      Adaptive Online Learning Spotlight
5                          Asynchronous Parallel Stochastic Gradient for Nonconvex Optimization Spotlight
6                                                 Attention-Based Models for Speech Recognition Spotlight
7                                                       Automatic Variational Inference in Stan Spotlight
8                                   Backpropagation for Energy-Efficient Neuromorphic Computing Spotlight
9                       Bandit Smooth Convex Optimization: Improving the Bias-Variance Tradeoff Spotlight
10                         Biologically Inspired Dynamic Textures for Probing Motion Perception Spotlight


dbClearResult(res)

```

### Task2
```{r}
res<- dbSendQuery(conn, "SELECT a.Name, p.Title 
                  FROM Authors a inner join PaperAuthors ap on a.id=ap.AuthorId
                  inner join papers p on p.Id=ap.PaperId 
                  WHERE a.Name='Josh Tenenbaum' 
                  ORDER BY p.Title")
df <- dbFetch(res, n=10)
df

Name                                                                                             Title
1 Josh Tenenbaum                                                       Deep Convolutional Inverse Graphics Network
2 Josh Tenenbaum Galileo: Perceiving Physical Object Properties by Integrating a Physics Engine with Deep Learning
3 Josh Tenenbaum                                                Softstar: Heuristic-Guided Probabilistic Inference
4 Josh Tenenbaum                                                        Unsupervised Learning by Program Synthesis


dbClearResult(res)

```

### Task 3

```{r}
res<- dbSendQuery(conn, "SELECT Title 
                  FROM Papers 
                  WHERE Title LIKE '%statistical%' 
                  ORDER BY Title")
df_title <- dbFetch(res, n=10)
df_title

Title
1 Adaptive Primal-Dual Splitting Methods for Statistical Learning and Image Processing
2                                Evaluating the statistical significance of biclusters
3                  Fast Randomized Kernel Ridge Regression with Statistical Guarantees
4     High Dimensional EM Algorithm: Statistical Optimization and Asymptotic Normality
5                Non-convex Statistical Optimization for Sparse Tensor Graphical Model
6            Regularized EM Algorithms: A Unified Framework and Statistical Guarantees
7                            Statistical Model Criticism using Kernel Two Sample Tests
8                         Statistical Topological Data Analysis - A Kernel Perspective

dbClearResult(res)
```

### Task 4
```{r}
res<- dbSendQuery(conn, "SELECT a.Name, count(p.Title) as NumPapers 
                  FROM Authors a inner join PaperAuthors ap on a.id=ap.AuthorId
                  inner join papers p on p.Id=ap.PaperId 
                  GROUP BY a.Name
                  ORDER BY  NumPapers")
df_count <- dbFetch(res, n=10)
df_count

 Name NumPapers
1       ABHISEK KUNDU         1
2      Aaditya Ramdas         1
3  Aaron C. Courville         1
4         Aaron Klein         1
5          Aaron Roth         1
6         Aarti Singh         1
7   Abbas Abdolmaleki         1
8  Abhradeep Thakurta         1
9          Adam Smith         1
10      Adarsh Prasad         1

dbClearResult(res)

dbDisconnect(conn)
```
