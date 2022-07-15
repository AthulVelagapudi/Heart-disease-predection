# Heart-disease-predection
## Problem statement
From the given data, predict whether the patient has 10-year risk of future coronary heart disease (CHD)
## EDA(exploratory data analysis)
1. Removing or filling the null values(by using the appropriate value of each column)
2. Plotting graphs such as Bar plot, Count plot, Pair plot, Scattar plot, Violin plot, Distribution plot and catplot for univariant, bivaraint and multivarint analysis
### Conclusions of EDA
1. Even though it seems heart disease is more frequent in people with lower level of education, it is not the complete fact. Number of sample in other levels is smaller. So, we need to another way to compare the relation. As a matter of fact it has not much to do with CHD.
2. Women are slightly more proned to have heart dieseases with other health conditions than men although women are less in count have not having CHD then men as well. This slight indifference can be ignored.
3. Even though we think smokers are in big risk of CHD, data analysis says the difference is not that big. By looking at rate, we can see that percantage difference is only around 1%. Hence, smoking is not a very helpful attribute to detect CHD but cigsPerDay can be helpful attribute to detect CHD.
4. People on BP medicine are more likely to have CHD in future than people who are not on medication of BP
5. Diabetic patients are more in risk than non-diabetic patients.
6. The data shows that people without CHD and with CHD are closer to being overweight in average. But without CHD people are close to normal BMI rate, which indicates BMI is a good indicator of health and CHD.
7. People with higher sysBP level are more likely to develop 10year CHD.
8. People with higher diaBP level are more likely to develop 10year CHD.
9. People with higher Cholesterol level are more likely to develop 10year CHD.
10.The final conclusion is that male or female, better in education or not better in education, who comsume more cigsPerday , who are on BP medicine,have high cholestrol,high sysBP and diaBP, and higher BMI have higher risk of CHD within the 10 yrs
## Feature selection
Selecting the best 10 attribute based on the chi-square test

![](https://github.com/AthulVelagapudi/Heart-disease-predection/blob/main/images/Feature%20selection.png)
## Removing outliers and resmapling 
1. Removing the outliers by plotting the box plot
2. We can see that the proportion is 5.97:1 which is not well balanced. One of the major issues when dealing with unbalanced datasets relates to the metrics used to evaluate a model. Using simpler metrics like accuracy_score can be misleading. In a dataset with highly unbalanced classes, if the classifier always "predicts" the most common class without performing any analysis of the features, it will still have a high accuracy rate, obviously illusory.
3. Oversampling aims to increase the number of instances from the underrepresented class in the data set. In our case, these techniques will increase the number of correct transactions in our data . If we do not balance the number of instances, most classification algorithms will heavily focus on the majority class. As a result, it might seem like your algorithm is achieving superb results when, in reality, it is simply always predicting the majority class.The easiest way to do so is to randomly select observations from the minority class and include them from the data set until we achieve a balance between the majority and minority class.
## Modeling and Evaluation
The machine learning models which were trained and evaluated are:
1. Logistic Regression
2. K-Nearest Neighbour
3. Decission Tree
4. Support Vector Machine
5. Naive Bayesian Classification
6. Random Forest
### Scores and Conclusion after evaluation

![](https://github.com/AthulVelagapudi/Heart-disease-predection/blob/main/images/Scores.png)

From result and the F1 score and accuracy of the models we conclude that Random Forest model is better because:
- It runs efficiently on large databases.
- It can handle thousands of input variables without variable deletion.
- It gives estimates of what variables are important in the classification
Also

- If the number of observations is lesser than the number of features, Logistic Regression should not be used, otherwise, it may lead to overfitting which doesnot occur in Random Forest

- Random forests are a strong modeling technique and much more robust than a single decision tree. They aggregate many decision trees to limit overfitting as well as error due to bias and therefore yield useful results.

- Random Forest is intrinsically suited for multiclass problems, while SVM is intrinsically two-class. For multiclass problem you will need to reduce it into multiple binary classification problems.

- We have to determine the value of parameter K (number of nearest neighbors) in KNN and the type of distance to be used. The computation time is also very much as we need to compute distance of each query instance to all training samples which is not required in Random forest

