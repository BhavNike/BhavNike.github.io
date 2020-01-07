---
title: "Classification of web posts"
date: 2019-10-31
tags: [data analysis, data science, classification models]
header:
  image: "/images/project3.jpg"
excerpt: "Data Analysis, Data Science, Classification Models"
mathjax: "true"
---


# Classification of web posts

## Introduction

Most of us follow blogs on the internet and read articles online. We even do Google searches for more information on topics we need to learn about. Have you ever clicked on a link and then found the content unrelated along with other material you would like to read? The content could be placed with the intention to capture your attention or plainly in error. Often it could be irritating to say the least and frustrating, at the max, to be unable to access info you need quickly and you may need to scroll down through other content not related to it. This is particularly true is the webpage accepts contributions from members and public. The issue can be resolved easily with the assistance of Machine Learning techniques. Classifiers are algorithms that can study passages and identify if they belong to a certain topic. Supervised training of these Classifiers by providing them with related content, allows them to quickly identify unrelated content and this could then be highlighted for further action.

## Design of Machine Learning model

The design of such Machine Learning models is done through training on a large amount of labelled data – with both positive and negative sentiment to allow the algorithm to learn the patterns /words used in such materials. The internet itself is the source of such large amounts of training materials.

## Development of model

In this project, we have attempted to design and test one such model. The model has been trained on labelled data from 2 sub-Reddits which are similar in some form. However, by providing the algorithm with huge quantity of text materials in the form of web posts, it can be taught to distinguish between two different topics and hence correctly assess (upto 95% of the time) the correct sub-Reddit that the post to be assigned to. The model has been developed after studying various Vectorizer and Classifier modules.

## Conclusion

There are multiple applications to such classification models. There are used in online chatbots to finetune the material forwarded to users upon their request, or redirect them to appropriate services. The are also used as research tools to better understand consumer behaviour.

## Limitations

- The model can only do a binary differentiation after vectorising the words, So it is in an either-or format.
- Model could throw up an error where sentiment is not in line with the content, eg, sarcastic tone of article.


### To view the code developed in the project
- kindly click <a href="https://github.com/BhavNike/dsi10_project3/blob/master/code/project3%20Notebook_1_getting%20data.ipynb"> here </a> for data collection
- kindly click <a href="https://github.com/BhavNike/dsi10_project3/blob/master/code/project3_Notebook2_data_cleaning_n_modelling.ipynb"> here </a> for EDA and modelling details

### To get an overview of the project
kindly click <a href="https://github.com/BhavNike/BhavNike.github.io/blob/master/images/Misclassification%20of%20webposts.pdf"> here </a>

