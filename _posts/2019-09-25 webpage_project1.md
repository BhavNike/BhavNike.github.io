---
title: "Comparison of US college admission tests ACT and SAT(2017/2018)"
date: 2019-09-25
tags: [data wrangling, data science, data visualisation]
header:
  image: "/images/project1.jpg"
excerpt: "Data Wrangling, Data Science, Data Visualisation"
mathjax: "true"
---


## Making SAT the preferred choice - for State Education Administrators

### Background for this study:

Participation in the college admission tests has increased, due to various factors, such as, Mandatory requirements for admission to institutes of higher learning Fee waivers offered by states SAT is working to expand its market share in recent years by revising the test and entering into deals with numerous states and school systems to give students the exam.

The increase in the number of students has impacted some state average scores.

This study is also an opportunity to assess the performance of the 2017 and 2018 cohorts in the ACT and SAT tests


### Reference:

https://en.wikipedia.org/wiki/List_of_standardized_tests_in_the_United_States#Admissions_tests

https://www.usnews.com/education/best-colleges/articles/2018-01-23/how-to-take-the-sat-act-for-free

https://www.edweek.org/ew/articles/2017/09/07/us-students-scores-inch-up-on-latest.html

SAT is increasingly the ‘preferred’ test with 100% participation in 5 states currently. However, the SAT board would like to expand and reach out to other states for more participants to adopt SAT as their preferred choice.

### Analysis:
As part of this study State-wise scores for individual components of ACT and SAT (years 2017 and 2018) were studied. Means of analysis used included:

- Calculation of mean and std deviation

- Calculation of quantiles (25, 50 and 75 quantiles)

- Study of skewness and distributions of scores

- Hypothesis testing

### Limitations of the study:

The available data is for only 2 years, hence it is hard to predict trends.

The timing is critical as many states are relooking at the ACT and SAT and policy decisions are being made on whether these should be mandatory or optional. Also, the cost of these decisions is an important factor for the administration. Colleges are questioning the holistic nature of tests and some are considering scrapping them totally. As of January 2018, over 1,000 colleges and universities have stopped requiring SAT or ACT scores for undergraduate applicants.
Strategies to convince state officials that SAT should be their choice:

- Share about past record of 2 years to show how the cohorts have done well

- Average SAT scores have grown along with SAT participation rates

- Provide support to administrative faculty in organising for the test and students taking up the test - for further discussion

- Conduct test on weekday to ensure high participation - for further discussion

- Explore other incentives for administrators - for further discussion

- Feedback from colleges / institutes of higher learning on how SAT can be made more holistic in nature so as to cater to their admission criteria

### Data Dictionary:

'state': Dataset of type string, used in both ACT and SAT lists and is indicative of the name of state in the United States of America

'act2017_participation' / 'act2018_participation': Datatype float, represents the average participation rate (in %) of the cohort of students in ACT exam for the year.

'act2017_eng'/'act2018_eng': Datatype float, represents the average score of student cohort in the state in English in ACT exam for the year.

'act2017_math' /'act2018_math': Datatype float, represents the average score of student cohort in the state in Math in ACT exam for the year.

'act2017_reading' /'act2018_reading': Datatype float, represents the average score of student cohort in the state in Reading in ACT exam for the year.

'act2017_science' /'act2018_science': Datatype float, represents the average score of student cohort in the state in Science in ACT exam for the year.

act2017_composite' /'act2018_composite': Datatype float, represents the average Composite score of student cohort in the state in ACT exam for the year.

'sat2017_participation' /'sat2018_participation': Datatype float, represents the average participation rate (in %) of the cohort of students in SAT exam for the year.

'sat2017_evi_based_read_write' /'sat2018_evi_based_read_write': Datatype float, represents the average score of student cohort in the state in Evidence based Reading and Writing in SAT exam for the year.

'sat2017_math' /'sat2018_math': Datatype float, represents the average score of student cohort in the state in Math in SAT exam for the year.

'sat2017_total' /'sat2018_total': Datatype float, represents the average total score of student cohort in the state in SAT exam for the year.


### To view the code developed in the project, kindly click here


```python

```
