---
title: "Exploring Youth Drug Use: A Decision Tree Analysis of the National Survey on Drug Use and Health"
excerpt: "The goal of this study is to investigate several aspects of youth drug use using data collected by the National Survey on Drug Use and Health. Using ensemble methods and decision trees, the findings are interpreted. 
In this project, alcohol use is predicted using binary classification, frequency of alcohol use in the previous year is predicted using multi-class classification, and estimated age of first alcohol use is predicted using regression. 
It identifies key factors that predict drug use in young people and makes suggestions about how to potentially improve preventive strategies."
---

Link to my GitHub Repository [Github Code](https://github.com/Likhitha-Veganti/data-science-projects/tree/main/Youth%20Drug%20Use%20Analysis).

## Introduction
This report's goal is to apply decision-tree-based analysis to look into the factors that are related to youth drug usage. 
Building prediction models using decision trees is a common machine learning technique, especially when the data contains both continuous and categorical variables. 
In this study, we will develop predictive models for youth drug usage using decision trees, including ensemble approaches.

## Dataset Description
The data used in this project is downloaded from National Survey on Drug Use and Health. https://www.datafiles.samhsa.gov/dataset/national-survey-drug-use-and-health-2020-nsduh-2020-ds0001
The dataset contains complete information on demographics of the respondents, youth experiences, drug use, and more variables. 
The Substance Abuse and Mental Health Services Administration (SAMHSA) conducts the survey every year to estimate the prevalence, patterns, and impacts of drug use in the country. 
The dataset contains 2000 variables and 30,000 observations, including data on demographics, youth experience variables and substance variables.

## Problem Types
In this report, we will use decision trees to investigate three different problem types related to youth drug use: binary classification, multi-class classification, and regression. 
Binary classification involves whether a respondent has ever used alcohol. 
Multi-class classification involves predicting the number of days of alcohol use in the past year. 
Regression involves predicting the age of first use for alcohol. 
We will demonstrate the use of decision trees, including ensemble methods, for each of these problem types.

## Data Cleaning
Used the code provided in the youthParse.ipynb file to clean up the initial dataset and create a new dataset called 'youth_data' that includes only the substance, demographic, and youth experience columns. 
Saved this new dataset as a CSV file for future use.
To further clean the data, removed all rows with black or unknown values in the demographic columns, as these values do not provide any useful information. 
Additionally, dropped all null values from the youth experience columns, as we need complete data in these columns to analyze youth experiences.
However, the null values from the substance columns are not removed as each problem only focuses on one variable from these columns and removing rows with null values from other variables would not be helpful.
health is affected by drinking alcohol from an early age. And also, age of alcohol use slightly
increases with increase in Income.

# Methodology
Refer to the youthDrugUseAnalysis.ipynb file for the methodology and results.

# CONCLUSIONS
The findings of the study suggest that boosting is the most accurate model for predicting whether an individual has ever used alcohol or not, with an accuracy of 82.33%. The important predictors for this model were YFLMJMO (how youth feel about their peers using marijuana
monthly) and STNDALC (the number of students in the youth's grade who drink alcoholic beverages).

For the multi-class classification task, the pruned decision tree and random forest models performed the best with an accuracy of 79.39% and 79.18% respectively. However, the confusion matrix obtained by pruning showed that the classifier is having difficulty in correctly
predicting the class labels of the test data, and the classifier is only predicting the majority class for all the test samples. 
This suggests that the classifier is not learning the patterns in the data and is instead making biased predictions towards the majority class. 
Therefore, re-balancing the class distribution in the data or trying other algorithms or parameter settings that can better handle class imbalance could be helpful.

The regression model for predicting the age of first alcohol use showed that the random forest model performed the best among the models evaluated, with an MSE of 3.02. 
The most important predictors for this model were EDUSCHGRD2(what grade in now/will the person be in) and HEALTH2 (overall health recode) and INCOME(total family income record). 
We can see age of first alcohol use increases with increase in EDUSCHGRD2. 
We can also see health is deteriorating if the person is using alcohol from an early age and also age of alcohol use slightly increases with INCOME.

Overall, the study suggests that the important predictors for alcohol use and age of first alcohol use are related to peer influence and social norms, such as how youth feel about their peers using marijuana monthly and the number of students in the youth's grade who drink alcoholic
beverages. The findings of the study have broader implications for designing interventions and prevention strategies to reduce underage alcohol use by targeting these important predictors.
