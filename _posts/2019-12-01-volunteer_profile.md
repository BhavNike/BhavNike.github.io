---
title: "Engaging Senior Volunteers Volunteer profile"
date: 2019-12-01
tags: [seniors, volunteers, datascience, dataanalysis]
header:
  image: "/images/SeniorVol.jpg"
excerpt: "Senior Volunteers, Data Analytics"
mathjax: "true"
---

<h1>Table of Contents<span class="tocSkip"></span></h1>
<div class="toc"><ul class="toc-item"><li><span><a href="#Seniors-volunteering---a-deeper-look" data-toc-modified-id="Seniors-volunteering---a-deeper-look-1"><span class="toc-item-num">1&nbsp;&nbsp;</span>Seniors volunteering - a deeper look</a></span><ul class="toc-item"><li><span><a href="#Background" data-toc-modified-id="Background-1.1"><span class="toc-item-num">1.1&nbsp;&nbsp;</span>Background</a></span><ul class="toc-item"><li><span><a href="#RSVP" data-toc-modified-id="RSVP-1.1.1"><span class="toc-item-num">1.1.1&nbsp;&nbsp;</span>RSVP</a></span></li></ul></li><li><span><a href="#Importing-relevant-libraries" data-toc-modified-id="Importing-relevant-libraries-1.2"><span class="toc-item-num">1.2&nbsp;&nbsp;</span>Importing relevant libraries</a></span></li><li><span><a href="#Problem-statement" data-toc-modified-id="Problem-statement-1.3"><span class="toc-item-num">1.3&nbsp;&nbsp;</span>Problem statement</a></span></li><li><span><a href="#Creating-Volunteer-Id-(vol_id)-that-can-be-used-to-link-volunteer-database-to-activity-databases" data-toc-modified-id="Creating-Volunteer-Id-(vol_id)-that-can-be-used-to-link-volunteer-database-to-activity-databases-1.4"><span class="toc-item-num">1.4&nbsp;&nbsp;</span>Creating Volunteer Id (vol_id) that can be used to link volunteer database to activity databases</a></span></li><li><span><a href="#Basic-profile-of-volunteer" data-toc-modified-id="Basic-profile-of-volunteer-1.5"><span class="toc-item-num">1.5&nbsp;&nbsp;</span>Basic profile of volunteer</a></span><ul class="toc-item"><li><span><a href="#Interest-of-volunteers-as-stated-during-registration" data-toc-modified-id="Interest-of-volunteers-as-stated-during-registration-1.5.1"><span class="toc-item-num">1.5.1&nbsp;&nbsp;</span>Interest of volunteers as stated during registration</a></span></li></ul></li><li><span><a href="#Creating-a-basic-model-to-predict-if-member-will-be-'active'" data-toc-modified-id="Creating-a-basic-model-to-predict-if-member-will-be-'active'-1.6"><span class="toc-item-num">1.6&nbsp;&nbsp;</span>Creating a basic model to predict if member will be 'active'</a></span><ul class="toc-item"><li><span><a href="#Applying-Standard-Scaler" data-toc-modified-id="Applying-Standard-Scaler-1.6.1"><span class="toc-item-num">1.6.1&nbsp;&nbsp;</span>Applying Standard Scaler</a></span></li><li><span><a href="#Model-1-:Logistic-regression---training-and-validation" data-toc-modified-id="Model-1-:Logistic-regression---training-and-validation-1.6.2"><span class="toc-item-num">1.6.2&nbsp;&nbsp;</span>Model 1 :Logistic regression - training and validation</a></span></li><li><span><a href="#Model-2-:Lasso-model---training-and-validation" data-toc-modified-id="Model-2-:Lasso-model---training-and-validation-1.6.3"><span class="toc-item-num">1.6.3&nbsp;&nbsp;</span>Model 2 :Lasso model - training and validation</a></span></li><li><span><a href="#Model-3:-Decision-Tree-Classifier---training-and-validation" data-toc-modified-id="Model-3:-Decision-Tree-Classifier---training-and-validation-1.6.4"><span class="toc-item-num">1.6.4&nbsp;&nbsp;</span>Model 3: Decision Tree Classifier - training and validation</a></span></li></ul></li><li><span><a href="#Testing-of-model" data-toc-modified-id="Testing-of-model-1.7"><span class="toc-item-num">1.7&nbsp;&nbsp;</span>Testing of model</a></span><ul class="toc-item"><li><span><a href="#Model-1:-Logistic-Regression---testing" data-toc-modified-id="Model-1:-Logistic-Regression---testing-1.7.1"><span class="toc-item-num">1.7.1&nbsp;&nbsp;</span>Model 1: Logistic Regression - testing</a></span></li><li><span><a href="#Model-2:-Lasso---testing" data-toc-modified-id="Model-2:-Lasso---testing-1.7.2"><span class="toc-item-num">1.7.2&nbsp;&nbsp;</span>Model 2: Lasso - testing</a></span></li><li><span><a href="#Model-3:-Decision-Tree-Classifier---testing" data-toc-modified-id="Model-3:-Decision-Tree-Classifier---testing-1.7.3"><span class="toc-item-num">1.7.3&nbsp;&nbsp;</span>Model 3: Decision Tree Classifier - testing</a></span></li></ul></li><li><span><a href="#Volunteer-profile-and-recommendations" data-toc-modified-id="Volunteer-profile-and-recommendations-1.8"><span class="toc-item-num">1.8&nbsp;&nbsp;</span>Volunteer profile and recommendations</a></span></li></ul></li></ul></div>

# Seniors volunteering - a deeper look

## Background

### RSVP

- RSVP Singapore The Organisation of Senior Volunteers is an Institution of Public Character and the National Centre of Excellence for Senior Volunteerism under the patronage of Mdm Halimah Yacob, President of the Republic of Singapore. The organisation started in 1998 and was launched by then-Prime Minister Mr Goh Chok Tong. RSVP Singapore is a registered society under the Societies Act and a member of the National Council of Social Service (NCSS).

- Since its inception, RSVP Singapore has been actively engaging seniors in purpose-driven volunteerism. With over 1,000 members and 1,500 ad-hoc volunteers, RSVP Singapore serves more than 200,000 beneficiaries each year including the mentally disadvantaged, at-risk children from low income families, and socially isolated seniors through its community service programmes.
(ref: https://rsvp.org.sg/vision-mission/)

- The project was scoped to look at the past four years of activities and profile of volunteers - 2015 to 2018 (full years) and till Oct 2019.

## Importing relevant libraries


```python
# importing libraries

import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import time
import random
from datetime import datetime
from datetime import timedelta
from sklearn import metrics
import math


from sklearn.model_selection import train_test_split, cross_val_score
from sklearn.preprocessing import StandardScaler
from sklearn.linear_model import LogisticRegression, LassoCV, Lasso
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import accuracy_score, confusion_matrix, mean_squared_error

import graphviz
from sklearn.externals.six import StringIO
from IPython.display import Image
from sklearn.tree import export_graphviz
import pydotplus


import requests

%matplotlib inline
```


```python
# setting options to view entire dataset

pd.set_option('display.max_columns', None)
pd.set_option('display.max_rows', None)
```

## Problem statement

-- To look at the volunteer database and activities conducted over 4 years (2015-2018) and study patterns:
- Profile of volunteers
- What activities are these volunteers most involved in? (Comparison of numbers)
- Clustering of volunteers based on activities they are invovled in / hours they volunteer
- Engagement of volunteers and suggestions for continuing their involvement

While this notebook will cover the basic profile and interests of the volunteers, the second book will focus on the various types of volunteers and the activities used by RSVP to engage them.


```python
# reading excel file containing volunteer details

df_volunteer= pd.read_excel('.\datasets\Vol Basic run on 29Oct Sample.xlsx')
df_volunteer.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date_Joined</th>
      <th>Gender</th>
      <th>Nationality</th>
      <th>Last 4 digits IC</th>
      <th>Date_of_Birth</th>
      <th>Age</th>
      <th>Postal_Code</th>
      <th>Race</th>
      <th>Spoken_languages</th>
      <th>Interests</th>
      <th>Skills</th>
      <th>Hear_about_us</th>
      <th>Education_Qualification</th>
      <th>Current_Employment_Status</th>
      <th>Employer_Name</th>
      <th>Designation</th>
      <th>Status</th>
      <th>Status_Remarks</th>
      <th>Registration_Date</th>
      <th>Membership_Type</th>
      <th>Membership_Start_Date</th>
      <th>Membership_Expiry_Date</th>
      <th>Membership_Payment</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>11-01-2016</td>
      <td>Male</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>05-08-1938</td>
      <td>81.0</td>
      <td>788214.0</td>
      <td>Others</td>
      <td>Hokkien,English</td>
      <td>Infocomm Related,</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Retired</td>
      <td>ForumEnergy Technologies Pte Ltd</td>
      <td>Regional Manager</td>
      <td>Inactive</td>
      <td>Inactive since June 2017.</td>
      <td>22-05-2016</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>16-05-2002</td>
      <td>Female</td>
      <td>NaN</td>
      <td>0001H</td>
      <td>30-07-1941</td>
      <td>78.0</td>
      <td>572152.0</td>
      <td>Chinese</td>
      <td>Cantonese,Hokkien,Teochew,English,Mandarin</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Secondary</td>
      <td>Homemaker</td>
      <td>K K Hospital</td>
      <td>Midwife</td>
      <td>Inactive</td>
      <td>Status data correction from (Ordinary Member) ...</td>
      <td>22-05-2016</td>
      <td>Ordinary Member</td>
      <td>NaN</td>
      <td>30-06-2015</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>02-02-2016</td>
      <td>Male</td>
      <td>NaN</td>
      <td>0024H</td>
      <td>17-06-1963</td>
      <td>56.0</td>
      <td>161057.0</td>
      <td>Chinese</td>
      <td>Cantonese,Hokkien,Teochew,English,Mandarin</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Others, pls</td>
      <td>NTUC Fairprice</td>
      <td>Retail Assistant</td>
      <td>Inactive</td>
      <td>Status data correction from (Ordinary Member) ...</td>
      <td>22-05-2016</td>
      <td>Ordinary Member</td>
      <td>NaN</td>
      <td>30-06-2016</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>12-10-2010</td>
      <td>Male</td>
      <td>Singapore Permanent Resident</td>
      <td>0037I</td>
      <td>07-12-1935</td>
      <td>84.0</td>
      <td>570269.0</td>
      <td>Chinese</td>
      <td>Cantonese,English,Mandarin</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Retired</td>
      <td>Retired</td>
      <td>Bank Central Asia, Indonesia</td>
      <td>Clerk</td>
      <td>Active</td>
      <td>NaN</td>
      <td>22-05-2016</td>
      <td>Ordinary Member</td>
      <td>25-09-2018</td>
      <td>30-06-2019</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>12-04-2013</td>
      <td>Female</td>
      <td>Singapore Citizen</td>
      <td>0066e</td>
      <td>29-07-1952</td>
      <td>67.0</td>
      <td>100050.0</td>
      <td>Chinese</td>
      <td>,English</td>
      <td>Office Admin.,Snr Guiding,Active Ageing Seniors</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Retired</td>
      <td>Retired</td>
      <td>Singapore Post Pte Ltd</td>
      <td>Part time CSO</td>
      <td>Active</td>
      <td>NaN</td>
      <td>22-05-2016</td>
      <td>Ordinary</td>
      <td>05-07-2019</td>
      <td>30-06-2019</td>
      <td>paid</td>
    </tr>
  </tbody>
</table>
</div>




```python
df_volunteer.shape
```




    (8285, 23)




```python
df_volunteer.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 8285 entries, 0 to 8284
    Data columns (total 23 columns):
    Date_Joined                  3151 non-null object
    Gender                       7955 non-null object
    Nationality                  6437 non-null object
    Last 4 digits IC             8080 non-null object
    Date_of_Birth                8211 non-null object
    Age                          8211 non-null float64
    Postal_Code                  4950 non-null float64
    Race                         4999 non-null object
    Spoken_languages             4917 non-null object
    Interests                    1342 non-null object
    Skills                       722 non-null object
    Hear_about_us                351 non-null object
    Education_Qualification      4396 non-null object
    Current_Employment_Status    2726 non-null object
    Employer_Name                1108 non-null object
    Designation                  1256 non-null object
    Status                       8227 non-null object
    Status_Remarks               5940 non-null object
    Registration_Date            8227 non-null object
    Membership_Type              2568 non-null object
    Membership_Start_Date        1092 non-null object
    Membership_Expiry_Date       2597 non-null object
    Membership_Payment           799 non-null object
    dtypes: float64(2), object(21)
    memory usage: 1.5+ MB


- Observations:
- The data has 8285 rows of info, However there are many null values and it needs to be cleaned for duplicates and missing values
- Relevant columns for analysis, such as date of birth, date of joining, status, details to link to other data sheets, will be retained
- Duplicates checked and rows with null values in identifying variables ('vol_id' and 'Date_of_Birth') dropped as ther is no other way toidentify such persons


```python
# dropping columns not relevant to study - eg. membership expiry and payment details

df_volunteer.drop(columns=['Status_Remarks','Membership_Start_Date',
                            'Membership_Expiry_Date','Membership_Payment'], inplace=True)
df_volunteer.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date_Joined</th>
      <th>Gender</th>
      <th>Nationality</th>
      <th>Last 4 digits IC</th>
      <th>Date_of_Birth</th>
      <th>Age</th>
      <th>Postal_Code</th>
      <th>Race</th>
      <th>Spoken_languages</th>
      <th>Interests</th>
      <th>Skills</th>
      <th>Hear_about_us</th>
      <th>Education_Qualification</th>
      <th>Current_Employment_Status</th>
      <th>Employer_Name</th>
      <th>Designation</th>
      <th>Status</th>
      <th>Registration_Date</th>
      <th>Membership_Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>11-01-2016</td>
      <td>Male</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>05-08-1938</td>
      <td>81.0</td>
      <td>788214.0</td>
      <td>Others</td>
      <td>Hokkien,English</td>
      <td>Infocomm Related,</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Retired</td>
      <td>ForumEnergy Technologies Pte Ltd</td>
      <td>Regional Manager</td>
      <td>Inactive</td>
      <td>22-05-2016</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>16-05-2002</td>
      <td>Female</td>
      <td>NaN</td>
      <td>0001H</td>
      <td>30-07-1941</td>
      <td>78.0</td>
      <td>572152.0</td>
      <td>Chinese</td>
      <td>Cantonese,Hokkien,Teochew,English,Mandarin</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Secondary</td>
      <td>Homemaker</td>
      <td>K K Hospital</td>
      <td>Midwife</td>
      <td>Inactive</td>
      <td>22-05-2016</td>
      <td>Ordinary Member</td>
    </tr>
    <tr>
      <th>2</th>
      <td>02-02-2016</td>
      <td>Male</td>
      <td>NaN</td>
      <td>0024H</td>
      <td>17-06-1963</td>
      <td>56.0</td>
      <td>161057.0</td>
      <td>Chinese</td>
      <td>Cantonese,Hokkien,Teochew,English,Mandarin</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Others, pls</td>
      <td>NTUC Fairprice</td>
      <td>Retail Assistant</td>
      <td>Inactive</td>
      <td>22-05-2016</td>
      <td>Ordinary Member</td>
    </tr>
    <tr>
      <th>3</th>
      <td>12-10-2010</td>
      <td>Male</td>
      <td>Singapore Permanent Resident</td>
      <td>0037I</td>
      <td>07-12-1935</td>
      <td>84.0</td>
      <td>570269.0</td>
      <td>Chinese</td>
      <td>Cantonese,English,Mandarin</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Retired</td>
      <td>Retired</td>
      <td>Bank Central Asia, Indonesia</td>
      <td>Clerk</td>
      <td>Active</td>
      <td>22-05-2016</td>
      <td>Ordinary Member</td>
    </tr>
    <tr>
      <th>4</th>
      <td>12-04-2013</td>
      <td>Female</td>
      <td>Singapore Citizen</td>
      <td>0066e</td>
      <td>29-07-1952</td>
      <td>67.0</td>
      <td>100050.0</td>
      <td>Chinese</td>
      <td>,English</td>
      <td>Office Admin.,Snr Guiding,Active Ageing Seniors</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Retired</td>
      <td>Retired</td>
      <td>Singapore Post Pte Ltd</td>
      <td>Part time CSO</td>
      <td>Active</td>
      <td>22-05-2016</td>
      <td>Ordinary</td>
    </tr>
  </tbody>
</table>
</div>



## Creating Volunteer Id (vol_id) that can be used to link volunteer database to activity databases

- With an effort to protect privacy and confidentiality, only the last 4 numbers of the IC and the alphabet are retained as linking details to connect the volunteer datatbase and other sheets showing the activities they have participated in.
- This detail will be called 'vol_id'.


```python
# 'last 4 digits IC' is one of the identifying factors for volunteers.

df_volunteer.rename(columns={'Last 4 digits IC': 'vol_id'}, inplace=True)
df_volunteer.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date_Joined</th>
      <th>Gender</th>
      <th>Nationality</th>
      <th>vol_id</th>
      <th>Date_of_Birth</th>
      <th>Age</th>
      <th>Postal_Code</th>
      <th>Race</th>
      <th>Spoken_languages</th>
      <th>Interests</th>
      <th>Skills</th>
      <th>Hear_about_us</th>
      <th>Education_Qualification</th>
      <th>Current_Employment_Status</th>
      <th>Employer_Name</th>
      <th>Designation</th>
      <th>Status</th>
      <th>Registration_Date</th>
      <th>Membership_Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>11-01-2016</td>
      <td>Male</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>05-08-1938</td>
      <td>81.0</td>
      <td>788214.0</td>
      <td>Others</td>
      <td>Hokkien,English</td>
      <td>Infocomm Related,</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Retired</td>
      <td>ForumEnergy Technologies Pte Ltd</td>
      <td>Regional Manager</td>
      <td>Inactive</td>
      <td>22-05-2016</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>16-05-2002</td>
      <td>Female</td>
      <td>NaN</td>
      <td>0001H</td>
      <td>30-07-1941</td>
      <td>78.0</td>
      <td>572152.0</td>
      <td>Chinese</td>
      <td>Cantonese,Hokkien,Teochew,English,Mandarin</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Secondary</td>
      <td>Homemaker</td>
      <td>K K Hospital</td>
      <td>Midwife</td>
      <td>Inactive</td>
      <td>22-05-2016</td>
      <td>Ordinary Member</td>
    </tr>
    <tr>
      <th>2</th>
      <td>02-02-2016</td>
      <td>Male</td>
      <td>NaN</td>
      <td>0024H</td>
      <td>17-06-1963</td>
      <td>56.0</td>
      <td>161057.0</td>
      <td>Chinese</td>
      <td>Cantonese,Hokkien,Teochew,English,Mandarin</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Others, pls</td>
      <td>NTUC Fairprice</td>
      <td>Retail Assistant</td>
      <td>Inactive</td>
      <td>22-05-2016</td>
      <td>Ordinary Member</td>
    </tr>
    <tr>
      <th>3</th>
      <td>12-10-2010</td>
      <td>Male</td>
      <td>Singapore Permanent Resident</td>
      <td>0037I</td>
      <td>07-12-1935</td>
      <td>84.0</td>
      <td>570269.0</td>
      <td>Chinese</td>
      <td>Cantonese,English,Mandarin</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Retired</td>
      <td>Retired</td>
      <td>Bank Central Asia, Indonesia</td>
      <td>Clerk</td>
      <td>Active</td>
      <td>22-05-2016</td>
      <td>Ordinary Member</td>
    </tr>
    <tr>
      <th>4</th>
      <td>12-04-2013</td>
      <td>Female</td>
      <td>Singapore Citizen</td>
      <td>0066e</td>
      <td>29-07-1952</td>
      <td>67.0</td>
      <td>100050.0</td>
      <td>Chinese</td>
      <td>,English</td>
      <td>Office Admin.,Snr Guiding,Active Ageing Seniors</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Retired</td>
      <td>Retired</td>
      <td>Singapore Post Pte Ltd</td>
      <td>Part time CSO</td>
      <td>Active</td>
      <td>22-05-2016</td>
      <td>Ordinary</td>
    </tr>
  </tbody>
</table>
</div>




```python
df_volunteer['Date_of_Birth'].isnull().value_counts()
```




    False    8211
    True       74
    Name: Date_of_Birth, dtype: int64



- For 74 volunteers Date of Birth is not available.
- Also checking the vol_id to see if the individual can be identified
- For volunteers where both Date of Birth and vol_id is not available - 59 nos - these are dropped as there is no way to identify them.
- In addition, most other fields also do not have info, allowing for dropping of the same.
- The resulting dataset has 8226 rows.


```python
# For 74 volunteers Date of Birth is not available.
# Also checking the vol_id to see if the individual can be identified
# For volunteers where both Date of Birth and vol_id is not available -
# 59 nos. - these are dropped as there is no way to identify them.
# In addition, most other fields have not be populated with info.

df_blanks = df_volunteer[(df_volunteer['Date_of_Birth'].isnull()) & (df_volunteer['vol_id'].isnull())]
df_blanks.head()
```


```python
df_blanks.shape
```




    (59, 19)




```python
# 59 volunteers do not have identifying details - vol_id, Date_of_Birth  
# dropping these 59 rows

index_blanks = df_blanks.index
print(index_blanks)
df_volunteer.drop(index_blanks, inplace=True)
```

    Int64Index([7742, 8227, 8228, 8229, 8230, 8231, 8232, 8233, 8234, 8235, 8236,
                8237, 8238, 8239, 8240, 8241, 8242, 8243, 8244, 8245, 8246, 8247,
                8248, 8249, 8250, 8251, 8252, 8253, 8254, 8255, 8256, 8257, 8258,
                8259, 8260, 8261, 8262, 8263, 8264, 8265, 8266, 8267, 8268, 8269,
                8270, 8271, 8272, 8273, 8274, 8275, 8276, 8277, 8278, 8279, 8280,
                8281, 8282, 8283, 8284],
               dtype='int64')



```python
df_volunteer.shape
```




    (8226, 19)




```python
# Other null values in 'vol_id' column have been given an Id of '1000Q'

df_volunteer['vol_id'].fillna('1000Q', inplace=True)
df_volunteer['vol_id'].astype('str')
df_volunteer['vol_id'] = df_volunteer['vol_id'].str[0:4]+ df_volunteer['vol_id'].str[4].str.upper()
df_volunteer.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date_Joined</th>
      <th>Gender</th>
      <th>Nationality</th>
      <th>vol_id</th>
      <th>Date_of_Birth</th>
      <th>Age</th>
      <th>Postal_Code</th>
      <th>Race</th>
      <th>Spoken_languages</th>
      <th>Interests</th>
      <th>Skills</th>
      <th>Hear_about_us</th>
      <th>Education_Qualification</th>
      <th>Current_Employment_Status</th>
      <th>Employer_Name</th>
      <th>Designation</th>
      <th>Status</th>
      <th>Registration_Date</th>
      <th>Membership_Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>11-01-2016</td>
      <td>Male</td>
      <td>NaN</td>
      <td>1000Q</td>
      <td>05-08-1938</td>
      <td>81.0</td>
      <td>788214.0</td>
      <td>Others</td>
      <td>Hokkien,English</td>
      <td>Infocomm Related,</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Retired</td>
      <td>ForumEnergy Technologies Pte Ltd</td>
      <td>Regional Manager</td>
      <td>Inactive</td>
      <td>22-05-2016</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>16-05-2002</td>
      <td>Female</td>
      <td>NaN</td>
      <td>0001H</td>
      <td>30-07-1941</td>
      <td>78.0</td>
      <td>572152.0</td>
      <td>Chinese</td>
      <td>Cantonese,Hokkien,Teochew,English,Mandarin</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Secondary</td>
      <td>Homemaker</td>
      <td>K K Hospital</td>
      <td>Midwife</td>
      <td>Inactive</td>
      <td>22-05-2016</td>
      <td>Ordinary Member</td>
    </tr>
    <tr>
      <th>2</th>
      <td>02-02-2016</td>
      <td>Male</td>
      <td>NaN</td>
      <td>0024H</td>
      <td>17-06-1963</td>
      <td>56.0</td>
      <td>161057.0</td>
      <td>Chinese</td>
      <td>Cantonese,Hokkien,Teochew,English,Mandarin</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Others, pls</td>
      <td>NTUC Fairprice</td>
      <td>Retail Assistant</td>
      <td>Inactive</td>
      <td>22-05-2016</td>
      <td>Ordinary Member</td>
    </tr>
    <tr>
      <th>3</th>
      <td>12-10-2010</td>
      <td>Male</td>
      <td>Singapore Permanent Resident</td>
      <td>0037I</td>
      <td>07-12-1935</td>
      <td>84.0</td>
      <td>570269.0</td>
      <td>Chinese</td>
      <td>Cantonese,English,Mandarin</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Retired</td>
      <td>Retired</td>
      <td>Bank Central Asia, Indonesia</td>
      <td>Clerk</td>
      <td>Active</td>
      <td>22-05-2016</td>
      <td>Ordinary Member</td>
    </tr>
    <tr>
      <th>4</th>
      <td>12-04-2013</td>
      <td>Female</td>
      <td>Singapore Citizen</td>
      <td>0066E</td>
      <td>29-07-1952</td>
      <td>67.0</td>
      <td>100050.0</td>
      <td>Chinese</td>
      <td>,English</td>
      <td>Office Admin.,Snr Guiding,Active Ageing Seniors</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Retired</td>
      <td>Retired</td>
      <td>Singapore Post Pte Ltd</td>
      <td>Part time CSO</td>
      <td>Active</td>
      <td>22-05-2016</td>
      <td>Ordinary</td>
    </tr>
  </tbody>
</table>
</div>




```python
# checking number of unique Id identifying volunteers

df_volunteer['vol_id'].nunique()
```




    7830




```python
# Checking duplicates of vol_id if any volunteer details are duplicated

df_duplicates = df_volunteer.groupby(by=['vol_id','Date_of_Birth']).count()
df_duplicates.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th></th>
      <th>Date_Joined</th>
      <th>Gender</th>
      <th>Nationality</th>
      <th>Age</th>
      <th>Postal_Code</th>
      <th>Race</th>
      <th>Spoken_languages</th>
      <th>Interests</th>
      <th>Skills</th>
      <th>Hear_about_us</th>
      <th>Education_Qualification</th>
      <th>Current_Employment_Status</th>
      <th>Employer_Name</th>
      <th>Designation</th>
      <th>Status</th>
      <th>Registration_Date</th>
      <th>Membership_Type</th>
    </tr>
    <tr>
      <th>vol_id</th>
      <th>Date_of_Birth</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0000D</th>
      <th>03-07-1962</th>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>0000J</th>
      <th>08-07-1948</th>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th rowspan="2" valign="top">0001H</th>
      <th>04-02-1945</th>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>30-07-1941</th>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
    </tr>
    <tr>
      <th>0002I</th>
      <th>16-02-1967</th>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>



## Basic profile of volunteer

- Based on the data available in the Volunteer database, the features defining a typical volunteer were shortlisted

- Total number of volunteers registered till 2018 = 8226

- Many have not provided much information about themselves.....
    - 7954 have stated Gender
        - female(5097, 62%)
        - male(2858,34.7%)
        - Unstated (272, 3.3%)
    - 6436 have stated Nationality
        - Singapore Citizen (6243,76%)
        - Singapore PR(153, 1.9%),
        - Foreigner(41, 0.5%),
        - Unknown(1790, 21.8%)
    - 4994 have provided information about Race
        - Chinese (4665, 56.7%),
        - Indian (190, 2.3%),
        - Malay (49,0.6%),
        - Others (39, 0.5%),
        - Eurasian (29, 0.4%),
        - Unstated (3232, 39.3%)
    - Recent years have seen rapid increase in signing up of volunteers
         - 2017: 2327 pax
         - 2018: 1694 pax
         - 2019: 1876 pax (till Oct 2019)



```python
# checking null values in 'Age' column - 15 values. using mean value to fill null values

df_volunteer['Age'].fillna(df_volunteer['Age'].mean(), inplace=True)
```


```python
# checking for null values in 'Nationality' column - replacing with 'NotStated'

df_volunteer['Nationality'].fillna('NotStated', inplace=True)
print(df_volunteer['Nationality'].value_counts())
df_volunteer['Nationality'].value_counts().plot(kind='bar');
```

    Singapore Citizen               6242
    NotStated                       1790
    Singapore Permanent Resident     153
    Foreigner                         41
    Name: Nationality, dtype: int64



![png](rsvp_01Dec_vol_profile_files/rsvp_01Dec_vol_profile_27_1.png)



```python
# checking for null values in 'Gender' column - replacing with 'NotStated'

df_volunteer['Gender'].fillna('NotStated', inplace=True)
print(df_volunteer['Gender'].value_counts())
df_volunteer['Gender'].value_counts().plot(kind='bar')
```

    Female       5097
    Male         2857
    NotStated     272
    Name: Gender, dtype: int64





    <matplotlib.axes._subplots.AxesSubplot at 0x1f01c28c2e8>




![png](rsvp_01Dec_vol_profile_files/rsvp_01Dec_vol_profile_28_2.png)



```python
# plotting gender and age of volunteers

df_volunteer.groupby('Gender').Age.hist()
plt.legend(['Female', 'Male'], facecolor='w' )
plt.show()

```


![png](rsvp_01Dec_vol_profile_files/rsvp_01Dec_vol_profile_29_0.png)



```python
# checking info in 'Race' column
df_volunteer['Race'].fillna('Unknown', inplace=True)
df_Race= pd.DataFrame(df_volunteer['Race'].value_counts())
df_Race.head(10)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Race</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Chinese</th>
      <td>4665</td>
    </tr>
    <tr>
      <th>Unknown</th>
      <td>3232</td>
    </tr>
    <tr>
      <th>Indian</th>
      <td>190</td>
    </tr>
    <tr>
      <th>Malay</th>
      <td>49</td>
    </tr>
    <tr>
      <th>Others</th>
      <td>39</td>
    </tr>
    <tr>
      <th>Eurasian</th>
      <td>29</td>
    </tr>
    <tr>
      <th>Others||Filipino</th>
      <td>6</td>
    </tr>
    <tr>
      <th>Others||Punjabi</th>
      <td>3</td>
    </tr>
    <tr>
      <th>Indonesian</th>
      <td>2</td>
    </tr>
    <tr>
      <th>Japanese</th>
      <td>2</td>
    </tr>
  </tbody>
</table>
</div>




```python
(df_Race.sort_values(by='Race')).plot(kind='barh',xlim=(0, 250))

```




    <matplotlib.axes._subplots.AxesSubplot at 0x1f01d316e80>




![png](rsvp_01Dec_vol_profile_files/rsvp_01Dec_vol_profile_31_1.png)



```python
df_volunteer['Spoken_languages'].head(10)
```




    0                                     Hokkien,English
    1          Cantonese,Hokkien,Teochew,English,Mandarin
    2          Cantonese,Hokkien,Teochew,English,Mandarin
    3                          Cantonese,English,Mandarin
    4                                            ,English
    5                                       ,English,Thai
    6                                             Chinese
    7    Cantonese,Hakka,Hokkien,Teochew,English,Mandarin
    8                                             Chinese
    9                          Cantonese,English,Mandarin
    Name: Spoken_languages, dtype: object




```python
df_volunteer['Spoken_languages'].isnull().sum()
```




    3317




```python
# Spoken languages info only available for 4909 volunteers (i.e., 8226-3317)

df_volunteer['Spoken_languages'].astype(str)
languages = df_volunteer['Spoken_languages'].str.get_dummies(',')
languages.sum().sort_values(ascending=False).head(10)

```




    Chinese      3277
    English      1508
    Mandarin     1141
    Hokkien       903
    Cantonese     754
    Teochew       489
    Malay         341
    Hainanese      82
    Hakka          69
    Tamil          57
    dtype: int64




```python
df_volunteer.columns
```




    Index(['Date_Joined', 'Gender', 'Nationality', 'vol_id', 'Date_of_Birth',
           'Age', 'Postal_Code', 'Race', 'Spoken_languages', 'Interests', 'Skills',
           'Hear_about_us', 'Education_Qualification', 'Current_Employment_Status',
           'Employer_Name', 'Designation', 'Status', 'Registration_Date',
           'Membership_Type'],
          dtype='object')




```python
df_volunteer['Education_Qualification'].notnull().sum()
```




    4395




```python
df_volunteer['Education_Qualification'].value_counts()
```




    Secondary                           755
    O Level                             565
    University Degree                   348
    GCE O Level                         340
    Polytechnic                         324
    Retired                             308
    Degree                              289
    A Levels                            232
    Primary                             202
    Diploma                             194
    GCE A Level                         130
    Postgraduate Degree                 109
    Masters                              70
    Employed (Full-Time)                 53
    Semi-retired                         52
    Homemaker                            41
    Self-employed                        38
    Employed (Part-Time)                 35
    Others, pls                          34
    ITE/NTC                              32
    College                              29
    Professional Qualifications          22
    Post Graduate Diploma                21
    No Formal Education                  21
    GCE N Level                          18
    Doctorate                            17
    Freelance Work                       16
    Certificate/Advanced Certificate     15
    N Level                              15
    Higher Nitec                         11
    Awaiting Employment                  11
    A Level                               7
    Nitec (ITE)                           6
    Bachelor Degree                       4
    secondary                             3
    Bachelor"s Degree                     3
    diploma                               3
    Post Graduate                         2
    others                                2
    A level                               2
    Post secondary                        2
    degree                                2
    o.level                               2
    Advanced Diploma                      1
    Senior Cambridge                      1
    Others                                1
    GCE O level                           1
    A-Level                               1
    post secondary                        1
    GCE O LEVEL                           1
    Postgraduate                          1
    No Formal education                   1
    Post-Graduate                         1
    Name: Education_Qualification, dtype: int64




```python
# growth of number of volunteers
df_volunteer['Date_Joined'].fillna(df_volunteer['Registration_Date'], inplace=True)
df_volunteer['join_yr']=pd.to_datetime(df_volunteer['Date_Joined'], format='%d-%m-%Y').dt.year
df_volunteer['join_yr'].fillna(1999)
df_volunteer['join_yr'].replace(to_replace=[1954,1953,1946,1936,1935,1949,1933,1965,1944,1996,1955,1997],
                                value=1999, inplace=True)
dataviz_vol= pd.DataFrame(df_volunteer['join_yr'].sort_index().value_counts())
print(df_volunteer['join_yr'].sort_index().value_counts())
df_volunteer['join_yr'].sort_index().plot(kind='hist')
plt.gcf().set_size_inches(10, 4)
```

    2017    2327
    2019    1876
    2018    1694
    2009     273
    2010     238
    2013     230
    2012     227
    2007     196
    2008     185
    2011     172
    2016     158
    2015     134
    2014     103
    2006      95
    2005      60
    2000      42
    1999      41
    2004      40
    2001      40
    2002      38
    1998      31
    2003      26
    Name: join_yr, dtype: int64



![png](rsvp_01Dec_vol_profile_files/rsvp_01Dec_vol_profile_38_1.png)



```python
dataviz_vol= dataviz_vol.sort_index()
# ser = pd.Series(np.random.normal(size=1000))

dataviz_vol.hist(cumulative=True, density=1, bins=200)

plt.show()

```


```python
df_volunteer[df_volunteer['join_yr'] > 2016]['Education_Qualification'].value_counts()
```




    O Level                  554
    Secondary                479
    University Degree        339
    Polytechnic              312
    A Levels                 227
    Primary                  135
    Postgraduate Degree      108
    Diploma                   43
    Degree                    42
    ITE/NTC                   32
    Retired                   26
    No Formal Education       21
    GCE O Level               20
    N Level                   15
    Semi-retired              13
    GCE A Level               11
    Others, pls                7
    Employed (Full-Time)       7
    A Level                    6
    Masters                    5
    Homemaker                  4
    Post Graduate Diploma      4
    secondary                  3
    Bachelor Degree            3
    Bachelor"s Degree          3
    o.level                    2
    Post Graduate              2
    Self-employed              2
    Freelance Work             2
    A level                    2
    Post secondary             2
    others                     1
    Employed (Part-Time)       1
    Postgraduate               1
    Senior Cambridge           1
    diploma                    1
    Advanced Diploma           1
    Others                     1
    GCE O level                1
    A-Level                    1
    post secondary             1
    Higher Nitec               1
    GCE O LEVEL                1
    degree                     1
    No Formal education        1
    College                    1
    Post-Graduate              1
    Name: Education_Qualification, dtype: int64




```python
# To extract year of joining from Registration Date
df_volunteer['Years']=2019 - (pd.to_datetime(df_volunteer['Date_Joined'], format='%d-%m-%Y').dt.year)

```

### Interest of volunteers as stated during registration
- info available from only 1342 persons


```python
df_volunteer['Interests'].notnull().sum()
```




    1342




```python
# To look at interests of volunteers

df_volunteer['Interests'].str.lower()
interests =df_volunteer['Interests'].dropna()
```


```python
# creating WordCloud - interests
from wordcloud import WordCloud, STOPWORDS, ImageColorGenerator

wordcloud = WordCloud(max_font_size=50, max_words=50, background_color="white").generate(' '.join(interests))

# Display the generated image:
plt.figure(figsize=(10,4))
plt.imshow(wordcloud, interpolation='bilinear')
plt.axis("off")
plt.show()
```


![png](rsvp_01Dec_vol_profile_files/rsvp_01Dec_vol_profile_45_0.png)



```python
# saving dataset as csv file

df_volunteer.to_csv('./datasets/df_volunteer.csv')
```

## Creating a basic model to predict if member will be 'active'

- From the available information which was quite limited, a predictive model was prepared to study the profile of members who are active.
- Logistic regression, Lasso regression and Decision tree models were used to identify features that were most likely to indicate 'activeness' in volunteers
- The 3 models highighted Nationality to be highly positive correlated and gender to be highly negative.

- However, due to the limitations of the data as well as absence of any health / mobility related data, the model is not very effective in predictions.
- Also the status of 'Active' and 'Inactive' is determined by the renewal of membership by the volunteer and hence is not a reliable measure. A volunteer may have not renewed his memebrship for various reasons, such as ill-health, other commitments on their time, forgetfulness, taken up employment, travelling, caring for family members, etc.


```python
## creating dummy columns for nominal columns - df_merged_dummies

df_baseline = df_volunteer[['vol_id','Gender','Nationality', 'Race', 'Age', 'Years', 'Spoken_languages', 'Status']]
df_baseline.head(10)

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>vol_id</th>
      <th>Gender</th>
      <th>Nationality</th>
      <th>Race</th>
      <th>Age</th>
      <th>Years</th>
      <th>Spoken_languages</th>
      <th>Status</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1000Q</td>
      <td>Male</td>
      <td>NotStated</td>
      <td>Others</td>
      <td>81.0</td>
      <td>3</td>
      <td>Hokkien,English</td>
      <td>Inactive</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0001H</td>
      <td>Female</td>
      <td>NotStated</td>
      <td>Chinese</td>
      <td>78.0</td>
      <td>17</td>
      <td>Cantonese,Hokkien,Teochew,English,Mandarin</td>
      <td>Inactive</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0024H</td>
      <td>Male</td>
      <td>NotStated</td>
      <td>Chinese</td>
      <td>56.0</td>
      <td>3</td>
      <td>Cantonese,Hokkien,Teochew,English,Mandarin</td>
      <td>Inactive</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0037I</td>
      <td>Male</td>
      <td>Singapore Permanent Resident</td>
      <td>Chinese</td>
      <td>84.0</td>
      <td>9</td>
      <td>Cantonese,English,Mandarin</td>
      <td>Active</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0066E</td>
      <td>Female</td>
      <td>Singapore Citizen</td>
      <td>Chinese</td>
      <td>67.0</td>
      <td>6</td>
      <td>,English</td>
      <td>Active</td>
    </tr>
    <tr>
      <th>5</th>
      <td>0067I</td>
      <td>Female</td>
      <td>Singapore Citizen</td>
      <td>Chinese</td>
      <td>68.0</td>
      <td>5</td>
      <td>,English,Thai</td>
      <td>Active</td>
    </tr>
    <tr>
      <th>6</th>
      <td>0068H</td>
      <td>Female</td>
      <td>Singapore Citizen</td>
      <td>Chinese</td>
      <td>73.0</td>
      <td>20</td>
      <td>Chinese</td>
      <td>Active</td>
    </tr>
    <tr>
      <th>7</th>
      <td>0072Z</td>
      <td>Female</td>
      <td>Singapore Citizen</td>
      <td>Chinese</td>
      <td>82.0</td>
      <td>11</td>
      <td>Cantonese,Hakka,Hokkien,Teochew,English,Mandarin</td>
      <td>Active</td>
    </tr>
    <tr>
      <th>8</th>
      <td>0074J</td>
      <td>Male</td>
      <td>Singapore Citizen</td>
      <td>Chinese</td>
      <td>68.0</td>
      <td>13</td>
      <td>Chinese</td>
      <td>Active</td>
    </tr>
    <tr>
      <th>9</th>
      <td>0081G</td>
      <td>Male</td>
      <td>NotStated</td>
      <td>Chinese</td>
      <td>75.0</td>
      <td>17</td>
      <td>Cantonese,English,Mandarin</td>
      <td>Inactive</td>
    </tr>
  </tbody>
</table>
</div>




```python
df_baseline['Status'].unique()
```




    array(['Inactive', 'Active', 'Special Attention', 'Probation', 'New'],
          dtype=object)




```python
mapping = {'Active':1, 'Special Attention':1, 'Probation':1, 'New': 1, 'Inactive': 0}
df_baseline['Status_curr']= df_baseline['Status'].apply(lambda x : mapping[x])

df_baseline.head(10)

```

    C:\Users\bhavn\Anaconda3\lib\site-packages\ipykernel_launcher.py:2: SettingWithCopyWarning:
    A value is trying to be set on a copy of a slice from a DataFrame.
    Try using .loc[row_indexer,col_indexer] = value instead

    See the caveats in the documentation: http://pandas.pydata.org/pandas-docs/stable/indexing.html#indexing-view-versus-copy






<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>vol_id</th>
      <th>Gender</th>
      <th>Nationality</th>
      <th>Race</th>
      <th>Age</th>
      <th>Years</th>
      <th>Spoken_languages</th>
      <th>Status</th>
      <th>Status_curr</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1000Q</td>
      <td>Male</td>
      <td>NotStated</td>
      <td>Others</td>
      <td>81.0</td>
      <td>3</td>
      <td>Hokkien,English</td>
      <td>Inactive</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0001H</td>
      <td>Female</td>
      <td>NotStated</td>
      <td>Chinese</td>
      <td>78.0</td>
      <td>17</td>
      <td>Cantonese,Hokkien,Teochew,English,Mandarin</td>
      <td>Inactive</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0024H</td>
      <td>Male</td>
      <td>NotStated</td>
      <td>Chinese</td>
      <td>56.0</td>
      <td>3</td>
      <td>Cantonese,Hokkien,Teochew,English,Mandarin</td>
      <td>Inactive</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0037I</td>
      <td>Male</td>
      <td>Singapore Permanent Resident</td>
      <td>Chinese</td>
      <td>84.0</td>
      <td>9</td>
      <td>Cantonese,English,Mandarin</td>
      <td>Active</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0066E</td>
      <td>Female</td>
      <td>Singapore Citizen</td>
      <td>Chinese</td>
      <td>67.0</td>
      <td>6</td>
      <td>,English</td>
      <td>Active</td>
      <td>1</td>
    </tr>
    <tr>
      <th>5</th>
      <td>0067I</td>
      <td>Female</td>
      <td>Singapore Citizen</td>
      <td>Chinese</td>
      <td>68.0</td>
      <td>5</td>
      <td>,English,Thai</td>
      <td>Active</td>
      <td>1</td>
    </tr>
    <tr>
      <th>6</th>
      <td>0068H</td>
      <td>Female</td>
      <td>Singapore Citizen</td>
      <td>Chinese</td>
      <td>73.0</td>
      <td>20</td>
      <td>Chinese</td>
      <td>Active</td>
      <td>1</td>
    </tr>
    <tr>
      <th>7</th>
      <td>0072Z</td>
      <td>Female</td>
      <td>Singapore Citizen</td>
      <td>Chinese</td>
      <td>82.0</td>
      <td>11</td>
      <td>Cantonese,Hakka,Hokkien,Teochew,English,Mandarin</td>
      <td>Active</td>
      <td>1</td>
    </tr>
    <tr>
      <th>8</th>
      <td>0074J</td>
      <td>Male</td>
      <td>Singapore Citizen</td>
      <td>Chinese</td>
      <td>68.0</td>
      <td>13</td>
      <td>Chinese</td>
      <td>Active</td>
      <td>1</td>
    </tr>
    <tr>
      <th>9</th>
      <td>0081G</td>
      <td>Male</td>
      <td>NotStated</td>
      <td>Chinese</td>
      <td>75.0</td>
      <td>17</td>
      <td>Cantonese,English,Mandarin</td>
      <td>Inactive</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>




```python
# replacing 'Spoken_languages' with dummy columns for languages

df_baseline = pd.concat([df_baseline, languages], axis=1, join='inner')
df_baseline.drop(['Spoken_languages', 'Status'], axis=1, inplace=True)

# saving dataset as csv file
df_baseline.to_csv('./datasets/df_baseline.csv')
df_baseline.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>vol_id</th>
      <th>Gender</th>
      <th>Nationality</th>
      <th>Race</th>
      <th>Age</th>
      <th>Years</th>
      <th>Status_curr</th>
      <th>Cantonese</th>
      <th>Filipino</th>
      <th>Mandarin</th>
      <th>Teochew/Hokkien (weak)</th>
      <th>Bahasa Indonesia</th>
      <th>Cantonese</th>
      <th>Chinese</th>
      <th>Dutch</th>
      <th>English</th>
      <th>Foochow</th>
      <th>French</th>
      <th>Fuqing</th>
      <th>German</th>
      <th>Hainanese</th>
      <th>Hakka</th>
      <th>Hengwah</th>
      <th>Hindi</th>
      <th>Hindi sanskrit</th>
      <th>Hockchew</th>
      <th>Hokkien</th>
      <th>Japanese</th>
      <th>Malay</th>
      <th>Mandarin</th>
      <th>Mandarin</th>
      <th>Mandarin (weak)</th>
      <th>Norwegian</th>
      <th>Not fluent in Malay</th>
      <th>Others</th>
      <th>Shanghainese</th>
      <th>Spanish</th>
      <th>Tamil</th>
      <th>Teochew</th>
      <th>Thai</th>
      <th>Vietnamese</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1000Q</td>
      <td>Male</td>
      <td>NotStated</td>
      <td>Others</td>
      <td>81.0</td>
      <td>3</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0001H</td>
      <td>Female</td>
      <td>NotStated</td>
      <td>Chinese</td>
      <td>78.0</td>
      <td>17</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0024H</td>
      <td>Male</td>
      <td>NotStated</td>
      <td>Chinese</td>
      <td>56.0</td>
      <td>3</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0037I</td>
      <td>Male</td>
      <td>Singapore Permanent Resident</td>
      <td>Chinese</td>
      <td>84.0</td>
      <td>9</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0066E</td>
      <td>Female</td>
      <td>Singapore Citizen</td>
      <td>Chinese</td>
      <td>67.0</td>
      <td>6</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>




```python

columns_to_getdummies =['Gender','Nationality', 'Race']
df_baseline_dummies = pd.get_dummies(df_baseline, columns=(columns_to_getdummies), prefix=(columns_to_getdummies), prefix_sep='')

df_baseline_dummies.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>vol_id</th>
      <th>Age</th>
      <th>Years</th>
      <th>Status_curr</th>
      <th>Cantonese</th>
      <th>Filipino</th>
      <th>Mandarin</th>
      <th>Teochew/Hokkien (weak)</th>
      <th>Bahasa Indonesia</th>
      <th>Cantonese</th>
      <th>Chinese</th>
      <th>Dutch</th>
      <th>English</th>
      <th>Foochow</th>
      <th>French</th>
      <th>Fuqing</th>
      <th>German</th>
      <th>Hainanese</th>
      <th>Hakka</th>
      <th>Hengwah</th>
      <th>Hindi</th>
      <th>Hindi sanskrit</th>
      <th>Hockchew</th>
      <th>Hokkien</th>
      <th>Japanese</th>
      <th>Malay</th>
      <th>Mandarin</th>
      <th>Mandarin</th>
      <th>Mandarin (weak)</th>
      <th>Norwegian</th>
      <th>Not fluent in Malay</th>
      <th>Others</th>
      <th>Shanghainese</th>
      <th>Spanish</th>
      <th>Tamil</th>
      <th>Teochew</th>
      <th>Thai</th>
      <th>Vietnamese</th>
      <th>GenderFemale</th>
      <th>GenderMale</th>
      <th>GenderNotStated</th>
      <th>NationalityForeigner</th>
      <th>NationalityNotStated</th>
      <th>NationalitySingapore Citizen</th>
      <th>NationalitySingapore Permanent Resident</th>
      <th>RaceChinese</th>
      <th>RaceEurasian</th>
      <th>RaceIndian</th>
      <th>RaceIndonesian</th>
      <th>RaceJapanese</th>
      <th>RaceMalay</th>
      <th>RaceOthers</th>
      <th>RaceOthers||Caucasian</th>
      <th>RaceOthers||Ceylonese</th>
      <th>RaceOthers||Filipino</th>
      <th>RaceOthers||Punjabi</th>
      <th>RaceOthers||Sinhalese</th>
      <th>RaceOthers||Thai</th>
      <th>RaceOthers||Vietnamese</th>
      <th>RacePakistani</th>
      <th>RaceSinhalese</th>
      <th>RaceUnknown</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1000Q</td>
      <td>81.0</td>
      <td>3</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0001H</td>
      <td>78.0</td>
      <td>17</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0024H</td>
      <td>56.0</td>
      <td>3</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0037I</td>
      <td>84.0</td>
      <td>9</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0066E</td>
      <td>67.0</td>
      <td>6</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>




```python
# baseline score of data on current status

df_baseline_dummies['Status_curr'].value_counts(normalize=True)
```




    1    0.771821
    0    0.228179
    Name: Status_curr, dtype: float64




```python
df_baseline_dummies.to_csv('./datasets/baseline.csv')
```


```python
# preparing X and y for modelling

X = df_baseline_dummies[['Age', 'Years', 'Cantonese', 'Mandarin', 'Chinese', 'English',
                         'Hainanese', 'Hakka', 'Hindi', 'Hokkien', 'Malay', 'Mandarin', 'Tamil', 'Teochew',
                         'GenderFemale', 'GenderMale', 'NationalityForeigner',  
                         'NationalitySingapore Citizen', 'NationalitySingapore Permanent Resident',
                         'RaceChinese', 'RaceEurasian','RaceIndian', 'RaceMalay']]

y = df_baseline_dummies['Status_curr']
X.shape, y.shape

```




    ((8226, 23), (8226,))




```python
# saving dataset as csv file

df_baseline_dummies.to_csv('./datasets/df_baseline_dummies.csv')
```

### Applying Standard Scaler


```python
# setting aside 20% of X and y for test purposes
# applying Standard scaler

X_train,X_test,y_train,y_test=train_test_split(X,y,test_size=0.25,random_state=0, stratify=y)

# standard scaling
ss = StandardScaler()
ss.fit(X_train)
X_train = ss.transform(X_train)
X_test = ss.transform(X_test)

```


```python
X_train.shape, X_test.shape
```




    ((6169, 23), (2057, 23))



### Model 1 :Logistic regression - training and validation


```python
# creating a logistic model - X_train1, X_val, y_train1, y_val

# split X and y into training and testing sets
X_train1,X_val,y_train1,y_val=train_test_split(X_train,y_train,test_size=0.25,random_state=0)

# standard scaling
ss = StandardScaler()
ss.fit(X_train1)
X_train1 = ss.transform(X_train1)
X_val = ss.transform(X_val)

# instantiate the model (using the default parameters)
lg_baseline = LogisticRegression(solver='lbfgs')

# fit the model with data
lg_baseline.fit(X_train1,y_train1)

# getting predictions
y_pred=lg_baseline.predict(X_val)

# calculating probabilities
prob_lg_baseline = lg_baseline.predict_proba(X_val)

# validation score
training_score = lg_baseline.score(X_train1, y_train1)
validation_score = lg_baseline.score(X_val, y_val)

# Generate a confusion matrix.
confusion_matrix(y_val, y_pred)

tn, fp, fn, tp = confusion_matrix(y_val, y_pred).ravel()

print('True Negatives: %s' % tn)
print('False Positives: %s' % fp)
print('False Negatives: %s' % fn)
print('True Positives: %s' % tp)

print('Training score:', training_score)
print('Validation score:', validation_score)
print('MSE:',mean_squared_error(y_val, y_pred))

# Print out intercept and coefficients.
print('Intercept:', lg_baseline.intercept_)
print('Coefficient:', lg_baseline.coef_)
print(type(lg_baseline.coef_))
```

    True Negatives: 253
    False Positives: 70
    False Negatives: 7
    True Positives: 1213
    Training score: 0.9420665801988759
    Validation score: 0.950097213220998
    MSE: 0.049902786779001944
    Intercept: [2.11751837]
    Coefficient: [[-0.01523056 -0.4101083  -0.11754014  0.02185603  0.10445194 -0.10417632
       0.09231091  0.08439391 -0.08350564 -0.09991119 -0.06327909  0.02185603
      -0.06003371 -0.01040314 -2.60230975 -2.56801013  0.64389587  2.49393104
       0.69417795 -1.26545949 -0.09677627 -0.43664819 -0.14489351]]
    <class 'numpy.ndarray'>



```python
coeff_df = pd.DataFrame(X.columns)
arr = np.array(lg_baseline.coef_)
df_arr = pd.DataFrame(data=arr).T
coeff_df = coeff_df.merge(df_arr, left_index=True, right_index=True, how='inner')
coeff_df.columns= ['feature', 'coeff_logreg']
print(coeff_df.sort_values(by='coeff_logreg',ascending=False))
coeff_df.sort_values(by='coeff_logreg',ascending=False).plot(kind='bar', x='feature')
```

                                        feature  coeff_logreg
    17             NationalitySingapore Citizen      2.493931
    18  NationalitySingapore Permanent Resident      0.694178
    16                     NationalityForeigner      0.643896
    4                                   Chinese      0.104452
    6                                 Hainanese      0.092311
    7                                     Hakka      0.084394
    11                                 Mandarin      0.021856
    3                                  Mandarin      0.021856
    13                                  Teochew     -0.010403
    0                                       Age     -0.015231
    12                                    Tamil     -0.060034
    10                                    Malay     -0.063279
    8                                     Hindi     -0.083506
    20                             RaceEurasian     -0.096776
    9                                   Hokkien     -0.099911
    5                                   English     -0.104176
    2                                 Cantonese     -0.117540
    22                                RaceMalay     -0.144894
    1                                     Years     -0.410108
    21                               RaceIndian     -0.436648
    19                              RaceChinese     -1.265459
    15                               GenderMale     -2.568010
    14                             GenderFemale     -2.602310





    <matplotlib.axes._subplots.AxesSubplot at 0x1f020a740f0>




![png](rsvp_01Dec_vol_profile_files/rsvp_01Dec_vol_profile_63_2.png)



```python
y_pred_proba = lg_baseline.predict_proba(X_test)[::,1]
fpr, tpr, _ = metrics.roc_curve(y_val,  y_pred)
auc = metrics.roc_auc_score(y_val,y_pred)
plt.plot(fpr,tpr,label="logreg model, auc="+str(auc))
plt.legend(loc=4)
plt.show()

```


![png](rsvp_01Dec_vol_profile_files/rsvp_01Dec_vol_profile_64_0.png)


### Model 2 :Lasso model - training and validation


```python
## Applying Lasso

# Lasso regression for given X_train, X_test, y_train, y_test, name of regression model

def lasso_reg(X_train, X_test, y_train, y_test, name):

    # Calculation of optimal alpha
    optimal_lasso = LassoCV(n_alphas=500, cv=10, verbose=1)
    optimal_lasso.fit(X_train, y_train)

    # instantiate lasso model with optimal alpha
    lasso = Lasso(alpha=optimal_lasso.alpha_)

    # Training the model
    lasso.fit(X_train, y_train)
    lasso_scores_train = cross_val_score(lasso, X_train, y_train, cv=10)
    print ("Mean score:", np.mean(lasso_scores_train))

    # getting co-eff values
    coeff_df = pd.DataFrame(lasso.coef_ , X.columns, columns=['Coefficient'])  

    # Fitting the model
    lasso.score(X_test, y_test)
    print('Validation/Test score:', lasso.score(X_test, y_test))
    pred = lasso.predict(X_test)

    # Metrics
    print ("Means Square Error:", metrics.mean_squared_error(y_test, pred ))
    print("Root Mean Square:", np.sqrt(metrics.mean_squared_error(y_test, pred)))


    return coeff_df, pred

```


```python
coeff_df, pred = lasso_reg(X_train1, X_val, y_train1, y_val, 'lasso')
```

    [Parallel(n_jobs=1)]: Using backend SequentialBackend with 1 concurrent workers.
    ........................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................[Parallel(n_jobs=1)]: Done  10 out of  10 | elapsed:    1.4s finished


    Mean score: 0.7242563051897465
    Validation/Test score: 0.7348770422392643
    Means Square Error: 0.04388113346759728
    Root Mean Square: 0.20947824103614504



```python
coeff_df.sort_values(by='Coefficient',ascending=False).head(20).plot(kind='bar')
```




    <matplotlib.axes._subplots.AxesSubplot at 0x1f01da0d780>




![png](rsvp_01Dec_vol_profile_files/rsvp_01Dec_vol_profile_68_1.png)


### Model 3: Decision Tree Classifier - training and validation


```python
# fitting Decision Tree Classifier to training, validation

# Instantiate model.
dt = DecisionTreeClassifier(max_depth=8,random_state = 42)

# Fit training data
model_dt = dt.fit(X_train1, y_train1)

# Evaluate model.
print(f'Score on training set: {model_dt.score(X_train1, y_train1)}')
print(f'Score on validation set: {model_dt.score(X_val, y_val)}')

# testing for validation set - X_val, y_val
model_dt_val = model_dt.fit(X_val, y_val)

#predictions
preds_dt=model_dt.predict(X_val)

# Generate a confusion matrix.
confusion_matrix(y_val, preds_dt)

tn, fp, fn, tp = confusion_matrix(y_val, preds_dt).ravel()

print("True Negatives: %s" % tn)
print("False Positives: %s" % fp)
print("False Negatives: %s" % fn)
print("True Positives: %s" % tp)

```

    Score on training set: 0.9589277993947255
    Score on validation set: 0.948801036941024
    True Negatives: 310
    False Positives: 13
    False Negatives: 24
    True Positives: 1196



```python
#Create a new tree with a lower depth (easier to visualize)

clf = DecisionTreeClassifier(max_depth = 8)

clf.fit(X_train1, y_train1)
dot_data = StringIO()
export_graphviz(clf, out_file=dot_data, feature_names=X.columns,
               filled=True, rounded=True,
               special_characters=True)
graph = pydotplus.graph_from_dot_data(dot_data.getvalue())
Image(graph.create_png())
```




![png](rsvp_01Dec_vol_profile_files/rsvp_01Dec_vol_profile_71_0.png)



## Testing of model

### Model 1: Logistic Regression - testing


```python
# using logistic regression model - X_train, X_test, y_train, y_test

# standard scaling
ss = StandardScaler()
ss.fit(X_train)
X_train = ss.transform(X_train)
X_test = ss.transform(X_test)

# instantiate the model (using the default parameters)
lg_baseline_test = LogisticRegression(solver='lbfgs')

# fit the model with data
lg_baseline_test.fit(X_train,y_train)

# getting predictions
y_pred_test=lg_baseline_test.predict(X_test)

# calculating probabilities
probability_lg_baseline_test = lg_baseline.predict_proba(X_test)

# validation score
training_score = lg_baseline.score(X_train, y_train)
test_score = lg_baseline.score(X_test, y_test)

# Generate a confusion matrix.
confusion_matrix(y_test, y_pred_test)

tn, fp, fn, tp = confusion_matrix(y_test, y_pred_test).ravel()

print("True Negatives: %s" % tn)
print("False Positives: %s" % fp)
print("False Negatives: %s" % fn)
print("True Positives: %s" % tp)

print('Training score:', training_score)
print('Test score:', test_score)
print("MSE:",mean_squared_error(y_test, y_pred_test))


```

    True Negatives: 379
    False Positives: 90
    False Negatives: 23
    True Positives: 1565
    Training score: 0.9442373156103097
    Test score: 0.9445794846864366
    MSE: 0.054934370442391835



```python
# to get co-efficients for model

coeff_df_test = pd.DataFrame(X.columns)
arr = np.array(lg_baseline_test.coef_)
df_arr_test = pd.DataFrame(data=arr).T
coeff_df_test = coeff_df_test.merge(df_arr_test, left_index=True, right_index=True, how='inner')
coeff_df_test.columns= ['feature', 'coef_logreg']
print(coeff_df_test.sort_values(by='coef_logreg',ascending=False))
coeff_df_test.sort_values(by='coef_logreg',ascending=False).plot(kind='bar', x='feature')
```

                                        feature  coef_logreg
    17             NationalitySingapore Citizen     2.560097
    18  NationalitySingapore Permanent Resident     0.692651
    16                     NationalityForeigner     0.661561
    4                                   Chinese     0.092881
    6                                 Hainanese     0.043636
    7                                     Hakka     0.042051
    11                                 Mandarin     0.011858
    3                                  Mandarin     0.011858
    12                                    Tamil    -0.049496
    0                                       Age    -0.055801
    9                                   Hokkien    -0.062695
    13                                  Teochew    -0.062806
    10                                    Malay    -0.068920
    2                                 Cantonese    -0.082700
    20                             RaceEurasian    -0.087335
    8                                     Hindi    -0.092611
    5                                   English    -0.101242
    22                                RaceMalay    -0.164994
    1                                     Years    -0.363874
    21                               RaceIndian    -0.387989
    19                              RaceChinese    -1.235166
    15                               GenderMale    -2.822673
    14                             GenderFemale    -2.885762





    <matplotlib.axes._subplots.AxesSubplot at 0x1f01c2b6e10>




![png](rsvp_01Dec_vol_profile_files/rsvp_01Dec_vol_profile_75_2.png)



```python
y_pred_proba = lg_baseline_test.predict_proba(X_test)[::,1]
fpr, tpr, _ = metrics.roc_curve(y_test,  y_pred_proba)
auc = metrics.roc_auc_score(y_test, y_pred_proba)
plt.plot(fpr,tpr,label="data 1, auc="+str(auc))
plt.legend(loc=4)
plt.show()
```


![png](rsvp_01Dec_vol_profile_files/rsvp_01Dec_vol_profile_76_0.png)


### Model 2: Lasso - testing


```python
coeff_df, pred = lasso_reg(X_train, X_test, y_train, y_test, 'lasso')
```

    [Parallel(n_jobs=1)]: Using backend SequentialBackend with 1 concurrent workers.
    ........................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................[Parallel(n_jobs=1)]: Done  10 out of  10 | elapsed:    1.4s finished


    Mean score: 0.7276218355950257
    Validation/Test score: 0.737418933566127
    Means Square Error: 0.046218746760138305
    Root Mean Square: 0.21498545708986527



```python
coeff_df.sort_values(by='Coefficient',ascending=False).head(20).plot(kind='bar')
```




    <matplotlib.axes._subplots.AxesSubplot at 0x1f020e7aef0>




![png](rsvp_01Dec_vol_profile_files/rsvp_01Dec_vol_profile_79_1.png)


### Model 3: Decision Tree Classifier - testing


```python
# fitting Decision Tree Classifier to test data

# Instantiate model.
dt = DecisionTreeClassifier(max_depth=8,random_state = 42)

# Fit training data
model_dt_test = dt.fit(X_train, y_train)

# Evaluate model.
print(f'Score on training set: {model_dt_test.score(X_train, y_train)}')
print(f'Score on test set: {model_dt_test.score(X_test, y_test)}')

# testing  - X_test, y_test
test_dt = dt.fit(X_test, y_test)

#predictions
preds_dt_test=model_dt_test.predict(X_test)

# Generate a confusion matrix.
confusion_matrix(y_test, preds_dt_test)

tn, fp, fn, tp = confusion_matrix(y_test, preds_dt_test).ravel()

print("True Negatives: %s" % tn)
print("False Positives: %s" % fp)
print("False Negatives: %s" % fn)
print("True Positives: %s" % tp)


```

    Score on training set: 0.9586642891878748
    Score on test set: 0.9402041808458921
    True Negatives: 422
    False Positives: 47
    False Negatives: 18
    True Positives: 1570



```python
#Create a new tree with a lower depth (easier to visualize)

clf = DecisionTreeClassifier(max_depth = 8)

clf.fit(X_train, y_train)
dot_data = StringIO()
export_graphviz(clf, out_file=dot_data, feature_names=X.columns,
               filled=True, rounded=True,
               special_characters=True)
graph = pydotplus.graph_from_dot_data(dot_data.getvalue())
Image(graph.create_png())
```

## Volunteer profile and recommendations

- Membership has increased in last 3 years and interests of the volunteers are varied
- Among the 5897 volunteers who have registered since 2017, 2290 (39%) have indicated that they have post secondary qualifications.
-



```python

```
