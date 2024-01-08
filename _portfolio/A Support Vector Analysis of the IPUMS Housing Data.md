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
Best Accuracy: 84.52%
Optimal Parameter: C = 0.01
Feature Importance: AGE, number of BEDROOMS, COST OF WATER, number of ROOMS, and marital status were identified as the most important features.

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/66b9deaf-6a09-43a2-8116-21d532a9b8bd)

Total 5,207 people, 4099 owners and 1108 renters are correctly classified as the owners and renters respectively. 672 renters are misclassified as owners and 282 owners are misclassified as renters.

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/063e2e4d-be04-4e32-ac50-887ffc87c126)

We can see that the most of the owners are increasing with AGE and then decreasing after a certain point of AGE say 75. It does make sense as the people tend to buy house after they settle in their life or to settle in their lives. After a certain age, they may give their ownership to their children.

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/01b3add8-cef2-4fb3-a558-30b88f0123de)

The households with 4 and 5 BEDROOMS have more positive ownership values. So, we can house with moderate number of BEDROOMS are most sold as people are willing to buy them more. 

See the report for the plots of remaining variables. Coming to the cost of water, if the cost of water is extreme high, there are more renters. So, we can conclude people are not willing to buy those houses. ROOMS is similar to BEDROOMS scenario. The household with moderate ROOMS have more owners. People whose marital status is Married and Spouse is present are more owners. It makes sense that they are buying houses because they may want to settle at a place with the family.

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/59b3aa3c-587d-4a1b-8cf3-77f72c62f23a)

We can see a linear boundary as it is a linear kernel SVM. The lower region of feature space is assigned to OWNERS and upper region is assigned to RENTERS. We can see a lot of RENTERS are misclassified as OWNERS which is true even from the confusion matrix and few of the OWNERS are misclassified as RENTERS.
We cannot see many of the OWNER’S points as they may be in other view and may be the RENTERS values are overlapping with OWNERS in our view as there are many other variables that impact the OWNERSHIP.

### Radial Basis Kernal SVM:
Best Accuracy: 84.79%
Optimal Parameters: Gamma = 0.1, C = 1
Feature Importance: Similar to the linear kernel, with the addition of HHINCOME.

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/c46efce6-3dea-4970-8173-1038a18b60f9)

This is the confusion matrix for the Radial Kernal SVM. 694 values of RENTERS are misclassified as OWNERS and 243 values of OWNERS are misclassified as RENTERS.
Most of the RENTERS are from lowincome households and most of the OWNERS are from high income households from the analysis.

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/d31e7a1e-32a5-4464-a88b-f3a7e015ca68)

We can see the decision boundary is non-linear as we used radial kernel SVM. The blue region is the OWNERS region and ORANGE region is the RENTERS region. We can see few overlaps as there are still some misclassifications. The view of values may be better in other views as there are many variables. But we can see a clear hyperplane that is dividing the values in this view.

### Polynomial Kernal SVM:
Best Accuracy: 85.03%
Optimal Parameters: Degree = 4, C = 0.1
Feature Importance: Similar to linear and radial kernels.

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/d295daa2-afe4-40f6-8e62-dff717e6c2cf)

This is the confusion matrix of polynomial kernel SVM. 693 of RENTERS are misclassified as OWNERS and 229 OWNERS are misclassified as RENTERS.

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/7a9aa13f-c06e-4797-8395-4c6c4a94bb12)

This is the decision boundary of a 4th degree polynomial. The blue region is OWNERS region and ORANGE belongs to RENTERS. We can still see a lot of misclassifications. Based on all the results, I might consider using Radial as it has better results than linear and also less complex and less time taking compared to polynomial.

### Conclusions
In this project, we aimed to predict home ownership based on demographic and socio-economic factors using Support Vector Machine (SVM) models. Our analysis revealed several important features that were strongly associated with home ownership.

Firstly, the age of the person was found to be the most important predictor of home ownership. This suggests that as people grow older, they are more likely to own their own homes. Additionally, the number of bedrooms and rooms in a household were also found to be important features for predicting home ownership. Households with four to five bedrooms and moderate numbers of rooms were more likely to have positive ownership values.

The cost of water was also found to be an important predictor of home ownership. Households with extreme high costs of water were more likely to have negative ownership values, indicating that people are less willing to buy houses with high water costs. Even marital status was found to be an important predictor of home ownership. Specifically, people who were married and had a spouse were more likely to own their own homes.
Even household income is an important predictor of home ownership. People with low household income were more likely to have negative ownership values. and people with high income tend to own more houses.

Overall, these findings have important implications for policymakers, real estate agents, and homeownership advocacy groups. By understanding the key factors associated with home ownership, these groups can develop targeted interventions to help more people become homeowners, which can have positive impacts on social and economic outcomes.
