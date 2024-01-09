---
title: "Connect-4 Game Outcome Analysis using Supervised and Unsupervised Machine Learning"
excerpt: "This project applies various supervised and unsupervised machine learning algorithms to analyze legal game positions in Connect-4. It explores the efficacy of different techniques such as Logistic Regression, Decision Trees, SVMs, Neural Networks, and K-means clustering, aiming to predict outcomes and provide insights into the Connect-4 dataset."
---
Link to my GitHub Repository [Github Code](https://github.com/Likhitha-Veganti/data-science-projects/tree/main/Connect-4%20Game%20Analysis).

# Introduction
Connect-4 is a two-player board game with a simple objective: connect four discs of the same color in a row, column, or diagonal. This project investigates the Connect-4 game dataset, comprising legal game positions where victory is not yet achieved, and the next move is not forced.
### Goals
- Examine the effectiveness of various analytical techniques.
- Utilize supervised algorithms for outcome prediction.
- Employ unsupervised learning for pattern discovery.

# Theoretical Background
A detailed discussion of each algorithm's theory and application is provided in the report, encompassing topics like Logistic Regression, Decision Trees, SVMs, Neural Networks, PCA, SVD, and Clustering.

# Methodology
The project includes data visualization, preprocessing with one-hot encoding, training various models, and evaluating them based on accuracy, silhouette score, and completeness score. 

# Results and Discussions
<img width="888" alt="Screenshot 2024-01-09 at 12 06 46 PM" src="https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/8578ecee-014e-44ee-9b34-b4774fe14307">

The table provides insights into the performance of different models and the clustering algorithm on the given dataset. The accuracy metric represents the percentage of correctly classified samples, while the silhouette score and completeness score measures how well the clusters capture the original classes. Based on the results, the random forest model achieved the highest accuracy, indicating its effectiveness in predicting the target variable. The linear SVM and clustering algorithm performed relatively poorly compared to other models, suggesting that the dataset may not exhibit clear linear separability or distinct clustering patterns.

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/32af2eb1-d7f0-4826-8990-ecd27a4625c3)

The given figure illustrates the Outcome Distribution for the connect-4 dataset, revealing an imbalance in the data distribution. However, it is noteworthy that an ample number of data points are available for each outcome category. Consequently, we can confidently proceed with this project.

### Random Forest Results:
Random Forest is the best model according to the accuracy values.

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/1d3a842f-65db-4ba4-b116-ebd99b8c4f5e)

Analyzing feature importances is essential for understanding the underlying factors that drive the model's predictions. It helps identify which features have the most influence on the target variable and can aid in feature selection or feature engineering processes.

![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/300574c4-7d4e-48b5-8bac-04533c719160)

The confusion matrix plot provides an overview of the performance of the random forest model by visually representing the predicted and actual values of the target variable, The diagonal elements of the confusion matrix represent the instances that were correctly classified, while the off-diagonal elements represent the instances that were misclassified.

### Neural Network Performance Visualization:
![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/548e67a9-615b-4fcb-9973-9ed1da35b5ec)

The neural network model that was trained achieved an impressive test accuracy of 79.55%. There is potential for further improvement by either developing a more robust model or making modifications to the existing model. Exploring different neural network architectures in future endeavours could lead to more advanced analyses and insights for the Connect-4 game.

### Singular Value Decomposition:
![image](https://github.com/Likhitha-Veganti/Likhitha-Veganti.github.io/assets/51111766/298f0fa8-a472-4d8d-99f4-1fa26e193c44)

The scree plot is a graphical representation of the eigenvalues of the principal components, showing the amount of variance explained by each component.
If you observe that the scree plot has a clear elbow or cutoff point, where the eigenvalues sharply drop after a certain number of components, it suggests that only a few principal components contribute significantly to the variance explained. In this case, it appears that the first eight principal components contribute to a larger proportion of the total variance, while the remaining components have minimal effect on the variance. This finding can be useful for dimensionality reduction purposes. Instead of using all the components, you may consider retaining only the first eight components that explain the majority of the variance. By doing so, you can reduce the dimensionality of your data while still preserving most of the relevant information.

# Conclusion:

In summary, this project analyzed the Connect4 dataset using machine learning techniques such as logistic regression, decision trees, random forest, boosting, SVMs, neural networks, and K-means clustering. The key findings include:

1. The random forest model was the most accurate, with an 81.94% success rate in predicting game outcomes.
2. The neural network also performed well, achieving 79.55% accuracy.
3. Lower accuracies were observed with linear SVM and the clustering algorithm, highlighting challenges in linear class separation and cluster identification.

Visualizations were used to illustrate data distribution and model performances, particularly identifying crucial game board positions for winning. Despite some limitations, this study provides valuable insights into the predictive capabilities of various machine learning models in classifying outcomes in Connect-4 and similar tasks. Future work could involve refining these models or exploring alternative approaches.






