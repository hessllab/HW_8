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

    __There are 3 variables and 84 observations.__

2.  What type of data (according to R) are in each of the vectors?

    __Height is a double, age is a double, and seed is an integer.__  
    
3.  What command could you use to force the Seed data to be an integer?

    `seed_int <- as.integer(Loblolly$Seed)`
    
4.  Write command(s) that record the date according to your computer and
    adds it to Loblolly as a column (repeating the same value for all
    observations) called ‘date’. In snippet, report the head of your
    revised data.frame.
    
    `Loblolly$date <- Sys.Date()`
    ```
    Loblolly
    
        height age Seed       date
    1    4.51   3  301 2019-10-18
    15  10.89   5  301 2019-10-18
    29  28.72  10  301 2019-10-18
    43  41.74  15  301 2019-10-18
    57  52.70  20  301 2019-10-18
    71  60.92  25  301 2019-10-18
    2    4.55   3  303 2019-10-18
    ```

5.  Add a new vector of data called ‘mature’ to the Loblolly data.frame
    that is a sequence of logical values such that any tree equal to or
    over the age of 10 is ‘TRUE’ and younger than 10 is ‘FALSE’

------------------------------------------------------------------------
#### For the following questions, create your own objects in R.

1.  Make a list that contains the abbreviated days of the week (‘Mon’,
    ‘Tue’, etc), months of the year, the numbers 1 through 31.
    
    ```
    months <- month.abb
    weekdays <- c("Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun")
    days <- (1:31)
    my_list <- list(weekdays, months, days) ```
    
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
    
    ```
    matrix(0, ncol=5, nrow=4, data=seq(1:5))
    colnames(my_matrix) <- c("Dory", "Edna", "Eva", "Boo", "Violet")
    rownames(my_matrix) <- c("FindingNemo", "Incredibles", "Wall-E", "MonstersInc")
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

<!-- -->

    ##               Dory    Edna   
    ## FindingNemo "TRUE"  "FALSE"
    ## Incredibles "FALSE" "TRUE"
    
***
#### Final Question to Be Completed with Your Partner
4. Import a text dataset of your choice into R using `read.csv` (or `read.table` or any of the other `read.` options). Use type coercion to adjust any variables that are read in incorrectly.  Report a snippet of the data and define the type of each vector in the data.frame.

