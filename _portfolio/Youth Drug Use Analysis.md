---
title: "Exploring Youth Drug Use: A Decision Tree Analysis of the National Survey on Drug Use and Health"
excerpt: "The goal of this study is to investigate several aspects of youth drug use using data collected by the National Survey on Drug Use and Health. Using ensemble methods and decision trees, the findings are interpreted. 
In this project, alcohol use is predicted using binary classification, frequency of alcohol use in the previous year is predicted using multi-class classification, and estimated age of first alcohol use is predicted using regression. 
It identifies key factors that predict drug use in young people and makes suggestions about how to potentially improve preventive strategies."
---

Link to my GitHub Repository [Github Code](https://github.com/Likhitha-Veganti/data-science-projects/tree/main/Youth%20Drug%20Use%20Analysis).

# Introduction
This report's goal is to apply decision-tree-based analysis to look into the factors that are related to youth drug usage. Building prediction models using decision trees is a common machine learning technique, especially when the data contains both continuous and categorical variables. In this study, we will develop predictive models for youth drug usage using decision trees, including ensemble approaches.

# Dataset Description
The data used in this project is downloaded from National Survey on Drug Use and Health. [DataSet Reference](https://www.datafiles.samhsa.gov/dataset/national-survey-drug-use-and-health-2020-nsduh-2020-ds0001)


The dataset contains complete information on demographics of the respondents, youth experiences, drug use, and more variables. The Substance Abuse and Mental Health Services Administration (SAMHSA) conducts the survey every year to estimate the prevalence, patterns, and impacts of drug use in the country. The dataset contains 2000 variables and 30,000 observations, including data on demographics, youth experience variables and substance variables.

# Problem Types
In this report, we will use decision trees to investigate three different problem types related to youth drug use: binary classification, multi-class classification, and regression. Binary classification involves whether a respondent has ever used alcohol.  Multi-class classification involves predicting the number of days of alcohol use in the past year. Regression involves predicting the age of first use for alcohol. We will demonstrate the use of decision trees, including ensemble methods, for each of these problem types.

# Data Cleaning
Used the code provided in the youthParse.ipynb file to clean up the initial dataset and create a new dataset called 'youth_data' that includes only the substance, demographic, and youth experience columns. 
Saved this new dataset as a CSV file for future use. To further clean the data, removed all rows with black or unknown values in the demographic columns, as these values do not provide any useful information. Additionally, dropped all null values from the youth experience columns, as we need complete data in these columns to analyze youth experiences. However, the null values from the substance columns are not removed as each problem only focuses on one variable from these columns and removing rows with null values from other variables would not be helpful. Health is affected by drinking alcohol from an early age. And also, age of alcohol use slightly increases with increase in Income.

# Methodology
Refer to the youthDrugUseAnalysis.ipynb file for the methodology.

# Results And Discussion

## 1. Binary CXlassification:

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/69caba5d-5995-4437-800c-1d506969714d)

The results show that Boosting has the highest accuracy (82.33%) among the five models for predicting whether an individual has ever used alcohol or not.

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/be60cc1b-05e2-44dd-b40c-8fdbb62ff43c)

This example tree is a pruned decision tree for binary classification of alcohol use (ALCFLAG) based on several predictor variables. The first node splits on the variable YFLMJMO, which measures how the youth feels about their peers using marijuana monthly. If YFLMJMO is 1, the decision tree proceeds to the left branch, otherwise it proceeds to the right branch. Suppose we follow the left branch. The next node splits on STNDALC, which measures the number of students in the youth's grade who drink alcoholic beverages. If STNDALC is 1, the decision tree proceeds to the left branch again, otherwise it proceeds to the right branch. Suppose we follow the left branch again. The next node splits on FRDADLY2, which measures the youth's perception of how their close friends feel about them having 1-2 alcoholic drinks per day. If FRDADLY2 is 1, the decision tree predicts that the youth has never used alcohol (ALCFLAG=0). The interpretation of this path is that if the youth strongly or somewhat disapprove of their peers using marijuana monthly, and if most or all of the students in their grade do not drink alcoholic beverages, and if their close friends strongly or somewhat disapprove of them having 1-2 alcoholic drinks per day, then the youth is predicted to have never used alcohol. When we have a yes/no or true/false analysis, such "Has the youth ever used alcohol?" binary variables, among other types of variables, are helpful. Ordinal or not, categorical variables can have both. Ordinal categorical variables, like "Strongly Disapprove", "Somewhat Disapprove", "Neither Approve nor Disapprove", "Somewhat Approve," and "Strongly Approve," have an intrinsic order. These kinds of variables can be helpful in determining how much the kids agree or disagree with various viewpoints. When we have a continuous measure, like the percentage of pupils in the youth's grade who consume alcoholic beverages, numerical variables are helpful. Generally, each data type should be utilized when appropriate for and relevant to the question being investigated.

### Boosting Results:

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/6f6df293-c219-461a-8ece-cafcb4852bdf)

645 youth are predicted as not drinking alcohol and actually not using alcohol. 63 youth are predicted as drinking alcohol but actually not using alcohol. 105 youth are predicted to be not using alcohol but actually using alcohol. 138 youth are predicted to be using alcohol and actually using alcohol. Accuracy is 82.33% which indicates that the model correctly predicted the alcohol use status of about 4 out of 5 youth.

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/1485dc7c-2fc2-4b10-94e5-0f54be90a28f)

These are the five most important predictors of the alcohol use. YFLMJMO indicated how youth feels about their peers using marijuana monthly. STNDALC measures the number of students in the youth's grade who drink alcoholic beverages. These two are major predictors for almost all the models used in predicting the results. 

## 2. Multi-Class Classification:

<img width="615" alt="image" src="https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/33f2ae1b-084e-4a00-9c4e-bca1d9edbeca">

The accuracy achieved by the models ranges from 68.35% for the decision tree model to 79.39% for the pruned decision tree model. It seems that the pruned decision tree and the random forest models are performing the best, achieving an accuracy of 79.39% and 79.18% respectively. Bagging and boosting models also perform relatively well with accuracy scores of 77.92% and 78.55% respectively.

### Pruning Results:

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/62c8761a-4390-433a-a323-8d6f28fe81e9)

This confusion matrix indicates that the prune_tree decision tree classifier is having difficultyin correctly predicting the class labels of the test data. The classifier is not making any correct predictions for classes 2, 3, and 4, as the counts in those rows are all 0. Instead, the classifier is only predicting the majority class (class 6) for all the test samples, as indicated by the large count in the last row of the matrix.
This suggests that the classifier is not learning the patterns in the data and is instead making biased predictions towards the majority class. This can happen when there is a class imbalance in the data, where one or more classes have significantly fewer samples than others. In such cases, the classifier may tend to overfit to the majority class and ignore the minority classes. To improve the performance of the classifier, it may be necessary to re-balance the class distribution in the data or try other algorithms or parameter settings that can better handle class imbalance.

### Random Forest Results:

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/13c95b76-25b3-4165-ae87-e44e797efbe0)

The confusion matrix shows the predicted and actual class labels of a classifier on test data. In this case, the classifier is making some correct predictions for classes 1, 2, and 6, but is not making any correct predictions for classes 3 and 4. The matrix also shows that the classifier is sometimes confusing classes 1 and 6, and to a lesser extent, classes 2 and 4. The diagonal counts represent the number of correct predictions, while off-diagonal counts represent misclassifications. Improvements could be made by exploring different algorithms, feature selection techniques, or parameter settings.

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/8293bad7-b13c-492f-b188-83284a3860f1)

We can see YFLMJMO and STNDALC are important predictors in both the models. 

YFLMJMO - How youth feel using marijuana monthly. (1 = Strongly/Somewhat Disapprove, 2 = Neither Approve nor Disapprove)
![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/3f0c861a-ce70-4a7e-b2d8-6931f9a5c3ff)

STNDALC – Students in yth grade drink alcoholic beverages. (1 = Most/All, 2 = None/Few)
![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/61552de3-d684-4bf8-a22c-50a92acd7c0c)

We can see that the youth who strongly/ somewhat disapprove of using marijuana monthly are more likely to not taking alcohol in the past year. Similarly, the students of the class with very few or no students that drink alcohol in the yth grade are more likely to not having alcohol in the past year.

## 3. Regression
<img width="610" alt="image" src="https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/3cf74421-1e0c-4e90-964b-a9d7c398f74a">

According to the table provided, the decision tree model has the highest MSE of 7.865, indicating poor performance. The pruning model has a lower MSE of 3.075, which is an improvement from the decision tree model. Overall, based on the MSE values, the random forest model appears to perform the best among the models evaluated for predicting the age of first alcohol use.

#### Random Forest Results:
<img width="360" alt="image" src="https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/3a540b37-8463-4bbc-98f7-2f12aa1f21f5">
<img width="467" alt="image" src="https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/aa6bf9ab-bf61-498a-884d-c34f17cd3356">
<img width="428" alt="image" src="https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/2af81726-286e-448d-a183-e5245403c86c">

This suggests that the grade or year of school that a respondent is currently attending or will attend after vacation is the most important predictor of the age of first alcohol use. We can see age of first alcohol use increases with increase in EDUSCHGRD2. The other top features include "HEALTH2" with an importance score of 0.029098 which describes the overall health record. We can see if the HEALTH2 is poor, the age of alcohol use is very less. Maybe the  health is affected by drinking alcohol from an early age. And also, age of alcohol use slightly increases with increase in Income.

# CONCLUSIONS
The findings of the study suggest that boosting is the most accurate model for predicting whether an individual has ever used alcohol or not, with an accuracy of 82.33%. The important predictors for this model were YFLMJMO (how youth feel about their peers using marijuana monthly) and STNDALC (the number of students in the youth's grade who drink alcoholic beverages).

For the multi-class classification task, the pruned decision tree and random forest models performed the best with an accuracy of 79.39% and 79.18% respectively. However, the confusion matrix obtained by pruning showed that the classifier is having difficulty in correctly predicting the class labels of the test data, and the classifier is only predicting the majority class for all the test samples. This suggests that the classifier is not learning the patterns in the data and is instead making biased predictions towards the majority class. Therefore, re-balancing the class distribution in the data or trying other algorithms or parameter settings that can better handle class imbalance could be helpful.

The regression model for predicting the age of first alcohol use showed that the random forest model performed the best among the models evaluated, with an MSE of 3.02. The most important predictors for this model were EDUSCHGRD2(what grade in now/will the person be in) and HEALTH2 (overall health recode) and INCOME(total family income record). We can see age of first alcohol use increases with increase in EDUSCHGRD2. We can also see health is deteriorating if the person is using alcohol from an early age and also age of alcohol use slightly increases with INCOME.

Overall, the study suggests that the important predictors for alcohol use and age of first alcohol use are related to peer influence and social norms, such as how youth feel about their peers using marijuana monthly and the number of students in the youth's grade who drink alcoholic beverages. The findings of the study have broader implications for designing interventions and prevention strategies to reduce underage alcohol use by targeting these important predictors.
