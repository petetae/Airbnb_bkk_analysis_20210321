# Airbnb_bkk_analysis_20210321
Analysing data from AirBnB in Bangkok area for 3 Mar 21 dataset

### Table of Contents

1. [Introduction](#Introduction)
2. [Installation](#installation)
3. [Project Motivation](#motivation)
4. [Process breakdown](#process)
5. [File Descriptions](#files)
6. [Results](#results)
7. [Licensing, Authors, and Acknowledgements](#licensing)

## Introduction <a name="Introduction"></a>

AirBnB has been everywhere around the world. This analysis is to identify the current state of its value in Bangkok and to identify potential interesting insights.
AirBnB has a lot of open data available to analyse and this project references the free data to identify insights around the host count, listing, and value predictions.

## Installation <a name="installation"></a>

There should be no necessary libraries to run the code here beyond the Anaconda distribution of Python.  The code should run with no issues using Python versions 3.
The Jupyter Notebook file can be downloaded and run without issues.

## Project Motivation<a name="motivation"></a>

Interestingly, there is a lot of free open data relating to AirBnB. So this small side project looks to try and answer the following business questions:


Business question 1: What are the top 10 most common amenities for AirBnB listings in Bangkok?

Business question 2: What are the top 10 ares in Bangkok with the most listing value? How many listings are there?

Business question 3: What are the growth trend in number of AirBnB hosts overtime in Bangkok?

Business question 4: What is the latest total value of AirBnB listings in Bangkok? 

Business question 5: Given an estimated number of listing at the end of the year 2021, what would be our total listing value predictions?

## Process <a name="process"></a>

Workings of this project follows the CRISP-DM process (https://www.sv-europe.com/crisp-dm-methodology/). Our work and analysis are as follows:

# 1. Business Understanding
There has been an increase number of AirBnB users around the world. Take Bangkok for example, the land of Smiles, how do we know the extent of AirBnB business and penetration to the renting industry in Thailand? We can do this by analysing the available data from AirBnB in the scope of hosts and listings value (http://insideairbnb.com/get-the-data.html).

Currently, we are assuming that there is a continual increase in host listings and growth trend overtime and an evenly distributed listings in different areas in Bangkok. We look to see whether our hypotheses still holds true or not.

Overall, the main objective for this project is to further understand the insights regarding the AirBnB landscape in Bangkok based on the overview host listings and insights. This project will work with basic analysis methods using Python, and our main success criteria is the ability to see the value of AirBnB listings, the growth trend, and the estimated value at the end of year 2022.

# 2. Data Understanding
Data used for this project is based on the open data provided by AirBnB itself (http://insideairbnb.com/get-the-data.html). The data available here includes the listings, reviews, neighborhood, and many more. However, for the scope of this project, we are only focusing on the data on listings only (as also included in this project). For further details and descriptions on the data dictionary, this can be found at (https://docs.google.com/spreadsheets/d/1iWCNJcSutYqpULSQHlNyGInUvHg2BoUGoNRIGa6Szc4/edit#gid=982310896).

Although the data is readily available, looking through it will show that there are missing information and null values. This moves onto our next part to clean the data before we can conduct a thorough analysis.

# 3. Prepare Data
In terms of the preparation of data, as readily mentioned, we are referring to the data from AirBnB (http://insideairbnb.com/get-the-data.html) for Bangkok area. In this project, we have scope the location and picked Bangkok but the code can be adapted to take in data from any location and still output the same analysis structure.

Now, as there are a number of null and missing data, this may prove issues in our analysis or our modelling. Cleaning of our data here includes two main methods that have been used.
1. Dropping null and missing values
2. Converting categorical data into dummy values for analysis

With regards to dropping missing values, more information can be found from the notebook. We first check whether there are any blank columns (columns with no data at all) and drop these first. We then check any information that is going to be used for plotting and remove missing rows from those data (for example, host_since column has dropped some missing row data before proceeding to analyse and plot).

The second part regarding converting data to categorical data into dummy values was done in order to be able to sum the information easily and count them. For example in the "amenities" column, you may see data such as ["aaa","bbb","ccc"] as one data point. This means that it is hard to count each data individually so we have to break them down to individual columns and then set a 1 or 0 value to it for that specific category. As you can see in the notebook, this breakdowns to many columns but is worthwhile to be able to conduct our analysis as we breakdown the column data and merge it back to the original dataframe.

# 4. Data Modeling
Based on the requirements of this project from the business questions that we are trying to answer, there are two main parts to the modelling for analysis.
1. Statistical analysis
2. Linear regression model

With regards to statistical analysis, these are basic use case such as the sum, count, mean, max value of the data itself. There is not much requirement for usage here.
In terms of the linear regression model, this is chosen to answer our last business question for predicting the value of the listing at the end of the year. Linear regression was chosen due to the fact that we were able to see a linear trend from other analysis (such as host count overtime, and the total listing value and count) so it would be appropriate. The main parameters used for this is that we split the data in 30-70 ratio to use for test and training. Due to the limited data available, the prediction may not be as accurate as it can be but serves as a starting point of our modelling.

# 5. Evaluate the Results
Finally, the last process step that we have undertaken is the review of the results. These are mainly assessed based on the accuracy of code and verifying that the data is correct. For the modelling, we can use the r2_score to analyse how close is the final result to the linear regression line trend. 

Overall, we then will cross check that we have successfully answered all business questions for this project.
Note, with regards to deployment, as this project does not require any web services setup, it is only deployed and saved as a project on Git repository.

## File Descriptions <a name="files"></a>

There is everything in one notebook for analysis and the attached csv files for the AirBnB listing data used for analysis.

## Results<a name="results"></a>

Main findings and analysis can also be found at https://pete-taecha.medium.com/is-airbnb-secretly-dominating-bangkok-419b676a23e9 link.
Overall, there is a strong growth trend in AirBnB domination in Bangkok and let's see whether they are going to further penetrate the market or not.

## Licensing, Authors, Acknowledgements<a name="licensing"></a>

Credits to AirBnB open data which can be found at http://insideairbnb.com/get-the-data.html

