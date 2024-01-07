---
title: "Exploring Housing Data: A Support Vector Analysis of the IPUMS Housing Data"
excerpt: "This project investigates the use of Support Vector Machines (SVM) for predicting homeownership based on demographic and economic data. It explores SVM's mathematical formulations, kernel functions, and tuning parameters, demonstrating its potential in predicting homeownership."
---
Link to my GitHub Repository [Github Code](https://github.com/Likhitha-Veganti/data-science-projects/tree/main/Housing%20Data%20Analysis).

## Introduction
The project focuses on SVMs to classify homes as owned or rented based on various individual and housing variables. This novel application of SVM in the real estate domain aims to provide insights into factors influencing homeownership.

## Dataset Description
The data, sourced from the United States Census Bureau, includes variables like number of rooms, income, age, marital status, and homeownership status. With 23 variables and 75,388 observations, it provides a comprehensive view of housing patterns in the U.S.

## Methodology
The dataset, initially comprising 75,388 rows and 23 columns, aimed to predict home ownership through a Support Vector Machine (SVM) model based on demographic and socio-economic factors. The first step involved subsetting the data to include only elder person rows for each household, resulting in a reduced dataset of 30,802 rows and 23 columns. Columns deemed unnecessary for analysis, such as SERIAL, OWNERSHPD, PERNUM, PERWT, BIRTHYR, EDUC, and EDUCD, were identified and dropped, ensuring relevance for the analysis. Subsequently, missing values were checked, and none were found. Categorical variable MARST (marital status) was encoded with its labels.

To prepare the data for modeling, it was split into training and testing sets using the train_test_split() function from the sklearn library. Scaling was applied using the StandardScaler() function to ensure feature consistency. These preprocessing steps yielded a clean and pertinent dataset for SVM model development.

In the SVM model with a linear kernel, feature selection was performed using the SelectKBest algorithm, and the model was trained and evaluated with various values of the regularization parameter C. Accuracy scores for each C value were printed. Feature importances were calculated using permutation importance, and countplots for the top 5 features were created to visualize their relationship with the target variable. A decision boundary graph using only the top 2 predictor variables was also plotted.

Similarly, for the SVM model with a radial kernel and polynomial kernel, feature selection, model training, and evaluation with different parameter values were conducted. Feature importances were calculated, countplots were generated, and decision boundary graphs using the top 2 predictor variables were plotted for each model.

## Results and Discussions

### Linear Kernel SVM:
The results show that Linear SVM with C = 0.01 after the feature selection gives best accuracy of 84.52%.
The project discusses the implications of SVM in real estate, highlighting the potential of machine learning in policy-making. Key predictors of homeownership, such as age, household size, and economic factors, are identified and analyzed for their impact.

### Conclusions
The study concludes with the effectiveness of SVM in predicting homeownership. It underscores the importance of certain demographic and socio-economic factors in homeownership and suggests how these insights can aid policymakers and real estate professionals.

This summary encapsulates the essence of each section while providing a cohesive understanding of the project's scope, methodology, and findings.
