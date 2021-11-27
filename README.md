# ATUS: Select-Non-work-Activities-and-Weekly-Earnings
 
The American Time Use Survey is an annual survey conducted on a sample of individuals across the United States studying how individuals spent their time over the course of a day. Individual respondents were interviewed about what activities they did, during what times (rounded to 15 minute increments), at what locations, and in the presence of which individuals. The activities are subsequently encoded based on 3 separate tier codes for classification. The ATUS package provides three datasets for analysis: ATUSACT (Tabulates the duration spent on different activities by respondent ID), ATUSCPS (Provides demographic information like marital status, ethnicity, sex, state of origin, and level of education about each respondent by respondent ID), and ATUSRESP (Provides primarily economic information for each respondent like earnings, type of work, industry of work, hours worked per week, and labor status by respondent ID). 

This project involves exploring the ATUS Data and predicting income based on how people spend non-work time. Non-work time was defined as "socializing, relaxing, and leisure" or as "sleeping" as reported in the ATUS dataset. This excludes things like exercise, household chores, and religious activities. The initial hypothesis was that there may be a connection between how someone spends this non-work time and their level of income. For example, perhaps if an individual spends a disproportionate amount of time watching TV during their non-work hours, they make less weekly earnings because they’re not building skills or maintaining their health. The results showed that only one variable was determined to have a significant effect on weekly earnings: time spent using tobacco and drugs. For this variable, our regression analysis determined that increasing time spent using tobacco and other drugs by 1% is associated with a 0.026% decrease in weekly earnings. For the remainder of our variables, there was no significant relationship.

Packages such as tidyverse and atus for exploring the ATUS data, data wrangling, data merging, regression modeling and analysis, exploratory data analysis, and summary tables. 

The steps that were taken in this analysis involved:

1. Data Wrangling:
- To do this analysis, we first have to construct a new data table that contains observations of a specific survey respondent ID, their weekly earnings, and all of the activity codes related to our definition of non-work activity. This required the use of the dplyr package to merge and filter the “atusact” and “atusresp” datasets. In this step, we also simplified our data to only include those who are in the workforce (not a student or unemployed), are full-time workers, and only have one job.

2. Exploratory
- In this step, we took our usable dataset and use ggplot2 to create “quick-and-dirty” visualizations to explore which variables may be the most pertinent to our analysis, how these variables are distributed and if we need to make adjustments, and other possible learnings.

3. Regression Analysis
- Once we had a usable dataset containing our variables of interest, we performed a number of regression analyses to explore the relationships between the time spent doing different types of non-work activities and weekly earnings for our survey respondents. For example, reprising the “watching TV” example from before, a regression line may look like the one below:
weeklyearningsi = β0 + β1(watchingTVi) + βk(controlvariablesi) + εi
- There are a number of variables that needed to be included in our controls including marital status, work-class (public sector, private sector, or self-employed), race, and education level in order to ensure that our regressions are valid.

#### The full analysis can be found in _ATUS Script.pdf_ and its respective R code in _ATUS Script.Rmd_
