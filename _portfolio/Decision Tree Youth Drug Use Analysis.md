---
title: "Exploring Youth Drug Use: A Decision Tree Analysis of the National Survey on Drug Use and Health"
excerpt: "The goal of this study is to investigate several aspects of youth drug use using data collected by the National Survey on Drug Use and Health.This project employs decision-tree-based analysis to explore factors related to youth drug usage, utilizing machine learning techniques. Three problem types are addressed: binary classification (whether a respondent has ever used alcohol), multi-class classification (predicting the number of days of alcohol use in the past year), and regression (predicting the age of first alcohol use).
It identifies key factors that predict drug use in young people and makes suggestions about how to potentially improve preventive strategies."
---

Link to my GitHub Repository [Github Code](https://github.com/Likhitha-Veganti/data-science-projects/tree/main/Youth%20Drug%20Use%20Analysis).

# Introduction
This report's goal is to apply decision-tree-based analysis to look into the factors that are related to youth drug usage. Building prediction models using decision trees is a common machine learning technique, especially when the data contains both continuous and categorical variables. In this study, we will develop predictive models for youth drug usage using decision trees, including ensemble approaches.

# Dataset Description
[DataSet Reference](https://www.datafiles.samhsa.gov/dataset/national-survey-drug-use-and-health-2020-nsduh-2020-ds0001)

The dataset is sourced from the National Survey on Drug Use and Health, containing 2000 variables and 30,000 observations. It encompasses demographics, youth experiences, and substance-related information. The Substance Abuse and Mental Health Services Administration conducts the annual survey to estimate drug use prevalence, patterns, and impacts.

# Problem Types
## Binary Classification:
Predicts whether an individual has ever used alcohol.
Utilizes decision trees, including ensemble methods.
Important predictors include feelings about peers using marijuana monthly and the number of students in the youth's grade who drink alcoholic beverages.

## Multi-Class Classification:
Predicts the number of days of alcohol use in the past year.
Decision tree, pruned decision tree, random forest, bagging, and boosting models are applied.
Top predictors include feelings about peers using marijuana monthly and the students' alcohol consumption in the youth's grade.

## Regression:
Predicts the age of first alcohol use.
Decision tree, pruned decision tree, random forest, bagging, and boosting models are evaluated.
Key predictors include the grade in school and overall health record.

# Data Cleaning
Used the code provided in the youthParse.ipynb file to clean up the initial dataset and create a new dataset called 'youth_data' that includes only the substance, demographic, and youth experience columns. 
Saved this new dataset as a CSV file youth_data.csv for future use. To further clean the data, removed all rows with black or unknown values in the demographic columns, as these values do not provide any useful information. Additionally, dropped all null values from the youth experience columns, as we need complete data in these columns to analyze youth experiences. However, the null values from the substance columns are not removed as each problem only focuses on one variable from these columns and removing rows with null values from other variables would not be helpful. Health is affected by drinking alcohol from an early age. And also, age of alcohol use slightly increases with increase in Income.

# Methodology
Refer to the 'youthDrugUseAnalysis.ipynb' file for detailed information on the methodology used for each problem type.

# Results And Discussion
## 1. Binary Classification:
![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/be60cc1b-05e2-44dd-b40c-8fdbb62ff43c)

This example tree is a pruned decision tree for binary classification of alcohol use (ALCFLAG) based on several predictor variables. The first node splits on the variable YFLMJMO, which measures how the youth feels about their peers using marijuana monthly. If YFLMJMO is 1, the decision tree proceeds to the left branch, otherwise it proceeds to the right branch. Suppose we follow the left branch. The next node splits on STNDALC, which measures the number of students in the youth's grade who drink alcoholic beverages. If STNDALC is 1, the decision tree proceeds to the left branch again, otherwise it proceeds to the right branch. Suppose we follow the left branch again. The next node splits on FRDADLY2, which measures the youth's perception of how their close friends feel about them having 1-2 alcoholic drinks per day. If FRDADLY2 is 1, the decision tree predicts that the youth has never used alcohol (ALCFLAG=0). The interpretation of this path is that if the youth strongly or somewhat disapprove of their peers using marijuana monthly, and if most or all of the students in their grade do not drink alcoholic beverages, and if their close friends strongly or somewhat disapprove of them having 1-2 alcoholic drinks per day, then the youth is predicted to have never used alcohol. When we have a yes/no or true/false analysis, such "Has the youth ever used alcohol?" binary variables, among other types of variables, are helpful. Ordinal or not, categorical variables can have both. Ordinal categorical variables, like "Strongly Disapprove", "Somewhat Disapprove", "Neither Approve nor Disapprove", "Somewhat Approve," and "Strongly Approve," have an intrinsic order. These kinds of variables can be helpful in determining how much the kids agree or disagree with various viewpoints. When we have a continuous measure, like the percentage of pupils in the youth's grade who consume alcoholic beverages, numerical variables are helpful. Generally, each data type should be utilized when appropriate for and relevant to the question being investigated.

*Boosting* has the highest accuracy (82.33%) among the five models for predicting whether an individual has ever used alcohol or not.
### Boosting Results:
![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/6f6df293-c219-461a-8ece-cafcb4852bdf)

645 youth are predicted as not drinking alcohol and actually not using alcohol. 63 youth are predicted as drinking alcohol but actually not using alcohol. 105 youth are predicted to be not using alcohol but actually using alcohol. 138 youth are predicted to be using alcohol and actually using alcohol. Accuracy is 82.33% which indicates that the model correctly predicted the alcohol use status of about 4 out of 5 youth.

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/1485dc7c-2fc2-4b10-94e5-0f54be90a28f)

These are the five most important predictors of the alcohol use. YFLMJMO indicated how youth feels about their peers using marijuana monthly. STNDALC measures the number of students in the youth's grade who drink alcoholic beverages. These two are major predictors for almost all the models used in predicting the results. 

## 2. Multi-Class Classification:
Pruned decision tree and random forest models perform the best with an accuracy of 79.39% and 79.18%, respectively.

### Pruning Results:

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/62c8761a-4390-433a-a323-8d6f28fe81e9)

This confusion matrix indicates that the prune_tree decision tree classifier is having difficultyin correctly predicting the class labels of the test data. The classifier is not making any correct predictions for classes 2, 3, and 4, as the counts in those rows are all 0. Instead, the classifier is only predicting the majority class (class 6) for all the test samples, as indicated by the large count in the last row of the matrix.
This suggests that the classifier is not learning the patterns in the data and is instead making biased predictions towards the majority class. This can happen when there is a class imbalance in the data, where one or more classes have significantly fewer samples than others. In such cases, the classifier may tend to overfit to the majority class and ignore the minority classes. To improve the performance of the classifier, it may be necessary to re-balance the class distribution in the data or try other algorithms or parameter settings that can better handle class imbalance.

### Random Forest Results:

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/13c95b76-25b3-4165-ae87-e44e797efbe0)

The confusion matrix shows the predicted and actual class labels of a classifier on test data. In this case, the classifier is making some correct predictions for classes 1, 2, and 6, but is not making any correct predictions for classes 3 and 4. The matrix also shows that the classifier is sometimes confusing classes 1 and 6, and to a lesser extent, classes 2 and 4. The diagonal counts represent the number of correct predictions, while off-diagonal counts represent misclassifications. Improvements could be made by exploring different algorithms, feature selection techniques, or parameter settings.

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/8293bad7-b13c-492f-b188-83284a3860f1)

We can see YFLMJMO and STNDALC are important predictors in both the models. 
Youth who strongly/ somewhat disapprove of using marijuana monthly are more likely to not taking alcohol in the past year. Similarly, the students of the class with very few or no students that drink alcohol in the yth grade are more likely to not having alcohol in the past year.

## 3. Regression
Random forest model outperforms others with an MSE of 3.02 in predicting the age of first alcohol use.

#### Random Forest Results:
<img width="467" alt="image" src="https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/aa6bf9ab-bf61-498a-884d-c34f17cd3356">
<img width="428" alt="image" src="https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/2af81726-286e-448d-a183-e5245403c86c">

Key predictors: grade in school, overall health record, and family income.
This suggests that the grade or year of school that a respondent is currently attending or will attend after vacation is the most important predictor of the age of first alcohol use. We can see age of first alcohol use increases with increase in EDUSCHGRD2. The other top features include "HEALTH2" with an importance score of 0.029098 which describes the overall health record. We can see if the HEALTH2 is poor, the age of alcohol use is very less. Maybe the  health is affected by drinking alcohol from an early age. And also, age of alcohol use slightly increases with increase in Income.

# CONCLUSIONS
The study's findings highlight effective predictive models for understanding youth drug usage patterns. In the realm of binary classification to determine whether an individual has used alcohol, boosting emerged as the most accurate model with an impressive 82.33% accuracy. Noteworthy predictors included how youth perceive their peers' marijuana use (YFLMJMO) and the prevalence of alcohol consumption among peers in the same grade (STNDALC). These insights illuminate the significance of social influences in shaping individual choices regarding alcohol use.

In the multi-class classification task, where the goal was to predict the number of days of alcohol use, pruned decision tree and random forest models showcased strong performance with 79.39% and 79.18% accuracy, respectively. However, challenges surfaced in the pruned decision tree's tendency to predict the majority class, indicating potential issues with data imbalance. For predicting the age of first alcohol use, the random forest model stood out with an MSE of 3.02. Critical predictors included the individual's grade in school (EDUSCHGRD2), overall health status (HEALTH2), and family income (INCOME). These findings emphasize the interplay of social dynamics, educational environment, and personal well-being in shaping youth behaviors related to alcohol use.
