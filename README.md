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
    
    3 variables and 84 observations

2.  What type of data (according to R) are in each of the vectors?
    
    Height is a double, age is a double and seed is an integer

3.  What command could you use to force the Seed data to be an integer?
    
    `Loblolly$Seed <- as.integer(Loblolly$Seed)`

4.  Write command(s) that record the date according to your computer and
    adds it to Loblolly as a column (repeating the same value for all
    observations) called ‘date’. In snippet, report the head of your
    revised data.frame.
    
    `Loblolly$date <- Sys.Date()`
    ```
       height age Seed       date
    1    4.51   3  301 2019-10-22
    15  10.89   5  301 2019-10-22
    29  28.72  10  301 2019-10-22
    43  41.74  15  301 2019-10-22
    57  52.70  20  301 2019-10-22
    71  60.92  25  301 2019-10-22
    ```

5.  Add a new vector of data called ‘mature’ to the Loblolly data.frame
    that is a sequence of logical values such that any tree equal to or
    over the age of 10 is ‘TRUE’ and younger than 10 is ‘FALSE’
    
    `Loblolly$mature <- as.logical(Loblolly$age>=10)`

------------------------------------------------------------------------
#### For the following questions, create your own objects in R.

1.  Make a list that contains the abbreviated days of the week (‘Mon’,
    ‘Tue’, etc), months of the year, the numbers 1 through 31.
    ```
    days_of_week <- weekdays(x=as.Date(seq(7), origin="2019-10-20"),abbreviate = TRUE)
    months <- month.abb
    date <- seq(1,31)
    my_list <- list(days_of_week, months, date)
    ```

2.  Write a command that will create a matrix with 4 rows and 5 columns
    and fill it as follows:
    ```
    rows <- c("FindingNemo", "Incredibles", "Wall-E", "MonstersInc")
    columns <- c("Dory", "Edna", "Eva", "Boo", "Violet")
    my_matrix <- matrix(ncol=5, nrow=4, data=(1:5), dimnames = list(rows, columns))
    ```

3. Remove the Violet vector from the matrix and fill it with logical values that tell us which movies the characters were actually in.
    ```
    my_matrix <- my_matrix[,-5]
    my_matrix <- (my_matrix==1)
    ```
    
***
#### Final Question to Be Completed with Your Partner
4. Import a text dataset of your choice into R using `read.csv` (or `read.table` or any of the other `read.` options). Use type coercion to adjust any variables that are read in incorrectly.  Report a snippet of the data and define the type of each vector in the data.frame.

```
    airQualityData <- read.csv(file = "pa_wv_annual.csv", header = TRUE, sep = ",")
    
    #   SITE_ID YEAR   DATEON  DATEOFF SO2_CONC SO4_CONC NO3_CONC
    # 1   CDR119 2018 01/02/18 01/01/19    0.401    1.099    0.298
    # 2   PAR107 2018 01/02/18 01/01/19    0.489    1.124    0.459
    # 3   CDR119 2017 01/03/17 01/02/18    0.586    1.212    0.321
    # 4   CDR119 2016 12/29/15 01/03/17    0.599    1.325    0.264
    # 5   PSU106 2018 01/02/18 01/01/19    0.644    1.231    1.076
    
    > typeof(airQualityData$DateOn)
    [1] "NULL"
    > typeof(airQualityData$DateOff)
    [1] "NULL"
    > airQualityData$DATEON <- as.character.Date(airQualityData$DATEON)
    > airQualityData$DATEOFF <- as.character.Date(airQualityData$DATEOFF)
```
