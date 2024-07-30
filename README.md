Building a Data Mining System, From Data Cleaning to Model Evaluation

Introduction

In this code sample, we're using a Decision Tree Classifier to make a prediction about whether someone has diabetes based on several medical characteristics like age, blood pressure, BMI, and so on. Our model's effectiveness is being assessed utilizing the Stratified K-Fold Cross Validation method. We can make sure that our model works effectively over a variety of data subsets using this strategy.

Dataset

The dataset used in this code snippet contains 100,000 records with 9 attributes. The dataset attributes are:

Gender: A categorical attribute that specifies the gender of the person. This attribute has values like Male, Female, and Other.
Age: A Ratio type attribute that specifies the person's age.
Hypertension: A categorical attribute that has binary values of either 0 or 1. This attribute specifies whether the person has blood pressure or not.
Heart Disease: A categorical attribute that has binary values of either 0 or 1. This attribute specifies whether the person has a history of heart disease or not.
Smoking History: An Ordinal type attribute that has values of ‘No Info’, ‘Never’, ‘Former’, ‘Not Current’, ‘Current’, and ‘Ever’. This attribute specifies the smoking history of the person.
BMI: A Ratio type attribute that specifies the Body Mass Index of a person. In this dataset, the BMI value ranges from 10 to 95.7.
HbA1c Level: A Ratio type attribute that specifies the Hemoglobin level or blood sugar level observed in a person’s blood in the past 2-3 months. In this dataset, the HbA1c level value ranges from 3.5 to 9.
Blood Glucose Level: A Ratio type attribute that specifies the amount of glucose observed in a person’s bloodstream at a given point in time. In this dataset, the glucose level value ranges from 80 to 300.
Diabetes: This is the output attribute that takes either 0 or 1. If a datapoint has a value of 1, then diabetes is present in the person, else diabetes is not present.
Preprocessing

Before the decision tree classifier receives the dataset, it is first processed through the following steps:

One hot encoding is used to convert the categorical feature “Gender” into a binary vector.
The nominal feature "Smoking History" is mapped to integers ranging from 0 to 4 based on the level of smoking history the person had.
The original columns of “Gender” and “Smoking History” are dropped from the dataset as they are no longer required.
All columns are normalized using StandardScaler before training.
Decision Tree Classifier

In combination with the pipeline object and the common scaler object, the decision tree classifier is defined and employed. An attribute grid contains the hyperparameter definitions for the decision tree classifier. The classifier is evaluated after being trained on the training data based on the accuracy score and F1 Score on testing data.

Stratified K-Fold Cross-Validation

Using the Stratified K-Fold Cross-Validation approach, the dataset is divided into five folds. The training and evaluation data for each fold are used to train and assess the decision tree classifier. Each fold's accuracy is recorded, and at the conclusion, a printout of the average accuracy across all folds is displayed.
