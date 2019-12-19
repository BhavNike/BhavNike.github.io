---
title: "AMES Housing data - modelling exercise"
date: 2019-09-25
tags: [data analysis, data science, modelling]
header:
  image: "../images/project2.jpg"
excerpt: "Data Analysis, Data Science, Modelling"
mathjax: "true"
---

## Background:
The Ames Housing Dataset is an exceptionally detailed and robust dataset with over 70 columns of different features relating to houses in the town of Ames, Iowa state USA.

## Objective:
To develop a Linear Regression model for the Prediction of saleprice of property using data available from Ames Iowa

## Data Dictionary: http://jse.amstat.org/v19n3/decock/DataDocumentation.txt
Details of the competition/dataset: DSI-US-6 Regression Challenge

## Process:
1. Download data in dataframe format
2. EDA of data
3. Checking for null values and replacement with valid values if needed
4. Coverting all catergorical (ordinal and nominal) data to integers and floats
5. Identifying features that have considerable correlation to the target variable (namely 'SalePrice')
6. Preparing and testing models to identify best fit for prediction of target variable
7. Compiling of predictions of models and uploading same to Kaggle to identify suitable model
8. Comments and observations during the process

## Details:
4 models were tried during the design process, with 17, 16 and 14 features. Variations, such as, lasso, ridge, polynomial model and inclusion of engineered feature were explored, along with the baseline model of linear regression.



## Outcome:
Although the scores of some of the models were in the same range, the final model was decided based on the lowest Kaggle score.
This was the Linear Regression model with 17 features.


## Limitations:
While it is not possible to design the perfect model, it may be possible to better fit the model by further exploring on the features as well as increasing the degree of the polynomial model.

The model may be further refined by:
    - Consider other features
    - Feature Engineering
    - Polynomial with degree of 3
    - Try other known models of regression

### To view the code developed in the project
- kindly click <a href="https://github.com/BhavNike/dsi10_project2/blob/master/code/Ames%20Housing_part%201%20Data%20Cleaning.ipynb"> here </a> for EDA details
- kindly click <a href="https://github.com/BhavNike/dsi10_project2/blob/master/code/Ames%20Housing_part%202%20Modelling.ipynb"> here </a> for modelling details
