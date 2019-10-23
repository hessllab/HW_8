---
title: "HW 8"
author: "Shaun Donmoyer"
date: "10/23/2019"
output: html_document
---
# HW_8
## R Practice with Data Structures

Work independently to solve each questions 1-8. Using GitHub, merge your answers with your partner's - selecting the best solution to each question or combine solutions to create a better answer.  Consider performance, elegance and readability in deciding on the best solution.

Work together on question 9.

Submit your answer as an .Rmd file using the following steps in GitHub:  

    + Fork-clone-branch 
    + Work independently on 1-8  
    + One partner invites other as collaborator  
    + Collaborator makes pull request to partner 1's repo  
    + Merge (it's gonna be messy!)  
    + Address question 8 
    + Partner 1 makes pull request to instructor's HW_8 repo  

***
For the following questions, use the Loblolly dataset that comes with Base R. Loblolly contains some data about a common garden experiment involving loblolly pine trees. Load the Loblolly dataset and answer the following questions (1-5).

1.  How many variables and how many observations are there?
``` {r}
str(loblolly)
```


#we can see that there are 3 variables and 84 observations in the dataset.

2.  What type of data (according to R) are in each of the vectors?

``` {r}
typeof(Loblolly$height) #yields double
```

``` {r}
typeof(Loblolly$seed) #yields integer
```

```{r}
typeof(Loblolly$age) #yields double
```

3.  What command could you use to force the Seed data to be an integer?
``` {r}
Loblolly$Seed <- as.integer(Loblolly$Seed)
```

4.  Write command(s) that record the date according to your computer and
    adds it to Loblolly as a column (repeating the same value for all
    observations) called ‘date’. In snippet, report the head of your
    revised data.frame.
``` {r}    
Loblolly$date <- date()
```

```
 height age Seed                     date 
1    4.51   3   10 Sun Oct 20 17:41:55 2019  
15  10.89   5   10 Sun Oct 20 17:41:55 2019  
29  28.72  10   10 Sun Oct 20 17:41:55 2019   
43  41.74  15   10 Sun Oct 20 17:41:55 2019   
57  52.70  20   10 Sun Oct 20 17:41:55 2019   
```


5.  Add a new vector of data called ‘mature’ to the Loblolly data.frame
    that is a sequence of logical values such that any tree equal to or
    over the age of 10 is ‘TRUE’ and younger than 10 is ‘FALSE’
```{r}    
Loblolly$mature <- ifelse(Loblolly$age >= 10, "True", "False")
```

```
height age Seed                     date mature
1    4.51   3   10 Sun Oct 20 17:41:55 2019  False
15  10.89   5   10 Sun Oct 20 17:41:55 2019  False
29  28.72  10   10 Sun Oct 20 17:41:55 2019   True
43  41.74  15   10 Sun Oct 20 17:41:55 2019   True
57  52.70  20   10 Sun Oct 20 17:41:55 2019   True
71  60.92  25   10 Sun Oct 20 17:41:55 2019   True
2    4.55   3   13 Sun Oct 20 17:41:55 2019  False
16  10.92   5   13 Sun Oct 20 17:41:55 2019  False
```

------------------------------------------------------------------------
#### For the following questions, create your own objects in R.

1.  Make a list that contains the abbreviated days of the week (‘Mon’,
    ‘Tue’, etc), months of the year, the numbers 1 through 31.

```{r}    
days <- c('Mon','Tue','Wed','Thu','Fri','Sat','Sun')



months <- c('Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec')


numbers <- 1:31


mylist <- list(days,months,numbers)


mylist
```    

For example:

    my_list

    ## [[1]]
    ## [1] "Mon" "Tue" "Wed" "Thu" "Fri" "Sat" "Sun"
    ## 
    ## [[2]]
    ##  [1] "Jan" "Feb" "Mar" "Apr" "May" "Jun" "Jul" "Aug" "Sep" "Oct" "Nov"
    ## [12] "Dec"
    ## 
    ## [[3]]
    ##  [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23
    ## [24] 24 25 26 27 28 29 30 31

2.  Write a command that will create a matrix with 4 rows and 5 columns
    and fill it as follows:
```{r}    
mymatrix <- matrix(c(1,2,3,4,5), nrow=4, ncol=5, byrow=FALSE) 


colnames(mymatrix)<-c("Dory","Edna","Eva","Boo","Violet")



rownames(mymatrix)<-c("FindingNemo","Incredibles","Wall-E","MonstersInc")

mymatrix
```


<!-- -->

    my_matrix

    ##             Dory Edna Eva Boo Violet
    ## FindingNemo    1    5   4   3      2
    ## Incredibles    2    1   5   4      3
    ## Wall-E         3    2   1   5      4
    ## MonstersInc    4    3   2   1      5

3. Remove the Violet vector from the matrix and fill it with logical values that tell us which movies the characters were actually in.

For example:
```{r}
mymatrix <- matrix(FALSE, nrow=4, ncol=4, byrow=FALSE)

diag(mymatrix)<- TRUE

colnames(mymatrix)<-c("Dory","Edna","Eva","Boo")

rownames(mymatrix)<-c("FindingNemo","Incredibles","Wall-E","MonstersInc")

mymatrix
```

<!-- -->

    ##               Dory    Edna   
    ## FindingNemo "TRUE"  "FALSE"
    ## Incredibles "FALSE" "TRUE"
    
***
#### Final Question to Be Completed with Your Partner
4. Import a text dataset of your choice into R using `read.csv` (or `read.table` or any of the other `read.` options). Use type coercion to adjust any variables that are read in incorrectly.  Report a snippet of the data and define the type of each vector in the data.frame.
```{r}
Bio <- read.csv("Biostats.csv")
Bio
```
```
Name      Sex Age Height..in. Weight..lbs.
1  Alex        M  41          74          170
2  Bert        M  42          68          166
3  Carl        M  32          70          155
4  Dave        M  39          72          167
5  Elly        F  30          66          124
6  Fran        F  33          66          115
7  Gwen        F  26          64          121
8  Hank        M  30          71          158
9  Ivan        M  53          72          175
10 Jake        M  32          69          143
```


```{r}
typeof(Bio$Name) #integer
```

```{r}
typeof(Bio$Sex) #integer
```

```{r}
typeof(Bio$Age) #integer
```

```{r}
typeof(Bio$Height..in.) #integer
```

```{r}
typeof(Bio$Weight..lbs.) #integer
```






