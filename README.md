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

2.  What type of data (according to R) are in each of the vectors?

3.  What command could you use to force the Seed data to be an integer?

4.  Write command(s) that record the date according to your computer and
    adds it to Loblolly as a column (repeating the same value for all
    observations) called ‘date’. In snippet, report the head of your
    revised data.frame.

5.  Add a new vector of data called ‘mature’ to the Loblolly data.frame
    that is a sequence of logical values such that any tree equal to or
    over the age of 10 is ‘TRUE’ and younger than 10 is ‘FALSE’

------------------------------------------------------------------------
#### For the following questions, create your own objects in R.

1.  Make a list that contains the abbreviated days of the week (‘Mon’,
    ‘Tue’, etc), months of the year, the numbers 1 through 31.

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

