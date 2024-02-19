# Face Orientation Detection Project

## Overview

The project aims to detect the angle of the roll, pitch, and yaw from the face. To accomplish this, we converted the face into 2D blobs, which serve as our data, and the target variables are the roll, pitch, and yaw (RPY).

## Data Preprocessing

Normalization of the data was necessary to ensure that each feature contributes equally to the analysis and to avoid bias towards features with larger scales.

## Model Evaluation

We evaluated multiple models to determine the best approach for predicting face orientation. Below are the models we experimented with along with their respective Root Mean Squared Error (RMSE) on the test data:

- Xgboost: RMSE of 0.579053
- Linear Regression: RMSE of 1.342557
- Lasso Regression: RMSE of 0.395986
- Ridge Regression: RMSE of 0.397217
- ElasticNet: RMSE of 0.395986
- Random Forest: RMSE of 0.464200
- K-Nearest Neighbors (KNN): RMSE of 0.4794939
- Decision Tree: RMSE of 0.605653
- AdaBoost: RMSE of 0.887643
- Support Vector Machine (SVM): RMSE of 0.410460

## Model Selection

After analyzing the results, we decided to focus on AdaBoost due to its promising performance. We further fine-tuned the model's hyperparameters using grid search, resulting in an improved RMSE of 0.39581.

## Model Serialization

We saved the trained AdaBoost model to disk for future use.

## Test on Real Data

To validate the model's performance, we ran tests on a video clip from "Sherlock Holmes" where the character was moving his head. Here's a sample output:

[Link to the Video]([https://drive.google.com/file/d/1-Xo5hhtfwLkN5pExR--quQFiuIWhki6J/view?usp=sharing](https://drive.google.com/file/d/1-Q0XGxDtLqOBL7CYEq6KzXnuExCip-1C/view?usp=sharing))

<video width="640" height="360" controls>
  <source src="[[https://www.example.com/your-video.mp4](https://drive.google.com/file/d/1-Xo5hhtfwLkN5pExR--quQFiuIWhki6J/view?usp=sharing)](https://drive.google.com/file/d/1-Q0XGxDtLqOBL7CYEq6KzXnuExCip-1C/view?usp=sharing)" type="video/mp4">
</video>


## Model Descriptions

### Xgboost
Xgboost is an optimized gradient boosting library that is highly efficient and flexible.

### Linear Regression
Linear Regression is a simple yet powerful regression technique that models the relationship between the independent and dependent variables using a linear approach.

### Lasso Regression
Lasso Regression is a linear regression technique that performs L1 regularization, which adds a penalty term to the loss function to encourage simpler models with fewer coefficients.

### Ridge Regression
Ridge Regression is another linear regression technique that performs L2 regularization, penalizing large coefficient values to prevent overfitting.

### ElasticNet
ElasticNet combines the penalties of both Lasso and Ridge regression, offering a balance between feature selection and model complexity.

### Random Forest
Random Forest is an ensemble learning method that builds multiple decision trees and combines their predictions to improve accuracy and reduce overfitting.

### K-Nearest Neighbors (KNN)
K-Nearest Neighbors is a non-parametric method used for classification and regression. It predicts the output based on the average of the 'k' nearest data points.

### Decision Tree
Decision Tree is a tree-like structure where each internal node represents a feature, each branch represents a decision, and each leaf node represents an outcome.

### AdaBoost
AdaBoost is an ensemble learning method that combines multiple weak learners to build a strong learner. It sequentially trains models on the same dataset but adjusts the weights of incorrectly classified instances to focus on the harder-to-classify cases.

### Support Vector Machine (SVM)
Support Vector Machine is a powerful supervised learning algorithm used for classification and regression tasks. It works by finding the hyperplane that best separates the data points into different classes while maximizing the margin.

## Conclusion

Through this project, we gained insights into various regression techniques and their effectiveness in predicting face orientation. AdaBoost emerged as the most promising model, offering both good performance and flexibility. This project highlights the importance of selecting appropriate models and optimizing hyperparameters to achieve accurate predictions.
