# Predicting-income-using-1994-US-Census

## Abstract

A Gradient Boosting Classification model was run to classify individuals in the 1994 US Census as >$50k median household income vs those with <=$50k. Feature importance revealed that marital status, education, age, and capital gains were the top 5 predictive features.

To dig deeper into this project, please see the final jupyter notebooks and presentation slides within this repository.

### Design
The local state government wants to see how well a model from 30 years ago would correctly classify against today’s median household income. The first step is to build a model using the 1994 US Census data to predict whether an individual’s income will be greater than or less than or equal to $50,000 based on several features. Classifying individuals as greater than or less than or equal to a $50k salary will assist the local government to understand which features were important in the 1994 model. The metric of interest will be accuracy.

### Data  
The data for this project was downloaded from Kaggle, which was taken from the UCI Machine Learning Repository. The unaltered data contains 32,561 rows, where each row represents an individual who completed the census that year. In total, there are 14 features (8 categorical). The target variable is salary, which was coded as 1 for “>$50k” and 0 for “<=$50k”.

### Algorithms  
**Feature Engineering:** Exploratory analyses were run to remove any data points that seemed illogical (e.g., 90 year olds working >50hours a week) and assess the distribution and segmentation of variables by class. Total education in years, as a continuous variable, was retained for modeling vice education expressed as categories. The response values for native country was engineered as “USA” and “Other”. Dummy coding was applied to all categorical features prior to modeling. 

**Exploratory Analysis:** A 60% train, 20% validation, and 20% test split was performed on the data. The training data was then oversampled to provide proper balance to our classification labels since 76% were classified as <=$50k and 24% as >$50k. The following models were tested on the training dataset and then on the validation dataset: Logistic Regression, KNN, Random Forest, Gradient Boosting Classifier, Extra Trees Classifier, AdaBoost Classifier. The Gradient Boost Classifier had the best metrics and was ultimately chosen as the prominent model for the testing dataset. The hyperparameters, max features, max depth, and n estimators were tuned.

**Metrics:** Final model contained 44 features (6 continuous) with a max depth 8, max features 6, and n estimators 150. All other hyperparameters were set to their default.
Validation - Accuracy .85, Precision .71, Recall .68, F1 Score .69, AUC, .91.
Testing - Accuracy .86, Precision .71, Recall .7, F1 Score .7, AUC .92

### Tools  
Numpy and Pandas for data manipulation, Scikit-learn for modeling, Matplotlib and Seaborn for plotting.

### Communication  
I completed a 5-minute presentation of my findings; slides and visuals for this project are included in this repository. Future work may include comparison of a prior season of the show, topic modeling across episodes, and re-segmenting the time interval.

<img width="531" alt="Screen Shot 2022-11-02 at 20 18 05" src="https://user-images.githubusercontent.com/80511410/199476537-ebccdf9d-e957-4e2c-9ea5-8b09e194a4e2.png">


