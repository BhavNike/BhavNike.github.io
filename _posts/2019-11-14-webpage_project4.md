---
title: "Predictive model for WNV"
date: 2019-11-14
tags: [data analysis, data science, predictive models, geodata]
header:
  image: "/images/project4.jpg"
excerpt: "Data Analysis, Data Science, Predictive Models, Geodata"
mathjax: "true"
---

## Where next WNV?  (Kaggle dataset)

## Background
In 2007-08, when the city of Chicago faced an epidemic of West Nile Virus, the Department of Public Health set up a surveillance and control system. The local public officials put together a team to study the spread of the epidemic and predict the occurence of mosquitoes carrying the virus and hence assist to halt the spread of the WNV.


## Dataset
The dataset, along with description, can be found here: [https://www.kaggle.com/c/predict-west-nile-virus/](https://www.kaggle.com/c/predict-west-nile-virus/).


## Problem statement
To develop a predictive model that will forecast the probability of WNV presence in 138 mosquito traps around Chicago over the course of a season. WNV is a communicable disease that is spread through its most common vector, mosquitoes.

## Analysis and modelling
- Data cleaning and EDA done on the train/test, weather and spray datasets
    - Train.csv was split into a training set and testing set. EDA was done on the training set.
- General observed trends:
    - WNV incidences spiked in July and August, the summer months in Chicago.
    - The spikes corresponds with increase in temp. and also humidity.
    - During the summer months, the number of days between rain days generally increases as well.
- Visualization of spatial data was done to observe the trap locations, concentration of WNV incidences, and spray locations.
    - It was found that O'Hare Airport was a major hotspot, with the other hotspot being in the River Grove/Belmont Terrace area. These areas either have multiple bodies of water, or are areas with a lot of greenery.
- Cost-benefit analysis done for spraying pesticide. It was concluded that usage of pesticide was not worth the amount of money for the effect it created.
- Modelling was done with various classification models, with the best being an XGBoost model.

## Recommendations
We would recommend against spraying on a large scale as it has been found to be not very effective. Targetted spraying in areas with very high density of mosquitoes would be preferred.

Other measures would be to educate the general population on steps to take to prevent mosquito breeding.

O’Hare Airport and River Grove areas should be the focus of mosquito eradication as they have the highest concentration of WNV.

Regular monitoring of weather forecasts would be useful to monitor the mosquito growth cycle.

## Limitations
There was no bird data (birds are WNV carriers as well).

Further study with more data can be done using neural network (possible to improve performance of the model)

### To view the code developed in the project
- kindly click <a href="https://github.com/BhavNike/BhavNike.github.io/blob/master/code/Project4Part1.ipynb"> here </a> for data cleaning and feature engineering details
- kindly click <a href="https://github.com/BhavNike/BhavNike.github.io/blob/master/code/Project4Part2.ipynb"> here </a> for modelling details
