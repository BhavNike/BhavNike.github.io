---
title: "ACTvsSAT code"
date: 2019-09-25
tags: [data wrangling, data science, data visualisation]
header:
  image: "/images/project1.jpg"
excerpt: "Data Wrangling, Data Science, Data Visualisation"
mathjax: "true"
---


# Project 1: SAT & ACT Analysis

<h1>Table of Contents<span class="tocSkip"></span></h1>
<div class="toc"><ul class="toc-item"><li><span><a href="#Project-1:-SAT-&amp;-ACT-Analysis" data-toc-modified-id="Project-1:-SAT-&amp;-ACT-Analysis-1"><span class="toc-item-num">1&nbsp;&nbsp;</span>Project 1: SAT &amp; ACT Analysis</a></span><ul class="toc-item"><li><span><a href="#Background" data-toc-modified-id="Background-1.1"><span class="toc-item-num">1.1&nbsp;&nbsp;</span>Background</a></span></li><li><span><a href="#Problem-statement:" data-toc-modified-id="Problem-statement:-1.2"><span class="toc-item-num">1.2&nbsp;&nbsp;</span>Problem statement:</a></span></li><li><span><a href="#Importing-relevant-libraries" data-toc-modified-id="Importing-relevant-libraries-1.3"><span class="toc-item-num">1.3&nbsp;&nbsp;</span>Importing relevant libraries</a></span></li><li><span><a href="#2017-Data-Import-and-Cleaning" data-toc-modified-id="2017-Data-Import-and-Cleaning-1.4"><span class="toc-item-num">1.4&nbsp;&nbsp;</span>2017 Data Import and Cleaning</a></span><ul class="toc-item"><li><span><a href="#Read-In-SAT-&amp;-ACT--Data" data-toc-modified-id="Read-In-SAT-&amp;-ACT--Data-1.4.1"><span class="toc-item-num">1.4.1&nbsp;&nbsp;</span>Read In SAT &amp; ACT  Data</a></span></li><li><span><a href="#Display-Data" data-toc-modified-id="Display-Data-1.4.2"><span class="toc-item-num">1.4.2&nbsp;&nbsp;</span>Display Data</a></span></li><li><span><a href="#Description-of-Data" data-toc-modified-id="Description-of-Data-1.4.3"><span class="toc-item-num">1.4.3&nbsp;&nbsp;</span>Description of Data</a></span></li><li><span><a href="#To-Fix-any-errors-identified" data-toc-modified-id="To-Fix-any-errors-identified-1.4.4"><span class="toc-item-num">1.4.4&nbsp;&nbsp;</span>To Fix any errors identified</a></span></li><li><span><a href="#7.-Renaming-Columns" data-toc-modified-id="7.-Renaming-Columns-1.4.5"><span class="toc-item-num">1.4.5&nbsp;&nbsp;</span>7. Renaming Columns</a></span></li><li><span><a href="#Creating-a-data-dictionary" data-toc-modified-id="Creating-a-data-dictionary-1.4.6"><span class="toc-item-num">1.4.6&nbsp;&nbsp;</span>Creating a data dictionary</a></span></li><li><span><a href="#Dropping-extra-rows" data-toc-modified-id="Dropping-extra-rows-1.4.7"><span class="toc-item-num">1.4.7&nbsp;&nbsp;</span>Dropping extra rows</a></span></li><li><span><a href="#Merging-Dataframes" data-toc-modified-id="Merging-Dataframes-1.4.8"><span class="toc-item-num">1.4.8&nbsp;&nbsp;</span>Merging Dataframes</a></span></li><li><span><a href="#Saving-dataframe-as-csv" data-toc-modified-id="Saving-dataframe-as-csv-1.4.9"><span class="toc-item-num">1.4.9&nbsp;&nbsp;</span>Saving dataframe as csv</a></span></li></ul></li><li><span><a href="#2018-Data-Import-and-Cleaning" data-toc-modified-id="2018-Data-Import-and-Cleaning-1.5"><span class="toc-item-num">1.5&nbsp;&nbsp;</span>2018 Data Import and Cleaning</a></span><ul class="toc-item"><li><span><a href="#Combining-2017-and-2018-data-into-a-single-dataframe" data-toc-modified-id="Combining-2017-and-2018-data-into-a-single-dataframe-1.5.1"><span class="toc-item-num">1.5.1&nbsp;&nbsp;</span>Combining 2017 and 2018 data into a single dataframe</a></span></li></ul></li><li><span><a href="#Exploratory-Data-Analysis" data-toc-modified-id="Exploratory-Data-Analysis-1.6"><span class="toc-item-num">1.6&nbsp;&nbsp;</span>Exploratory Data Analysis</a></span><ul class="toc-item"><li><span><a href="#Summary-Statistics" data-toc-modified-id="Summary-Statistics-1.6.1"><span class="toc-item-num">1.6.1&nbsp;&nbsp;</span>Summary Statistics</a></span><ul class="toc-item"><li><span><a href="#Manually-calculating-standard-deviation" data-toc-modified-id="Manually-calculating-standard-deviation-1.6.1.1"><span class="toc-item-num">1.6.1.1&nbsp;&nbsp;</span>Manually calculating standard deviation</a></span></li><li><span><a href="#Investigating-trends-in-the-data" data-toc-modified-id="Investigating-trends-in-the-data-1.6.1.2"><span class="toc-item-num">1.6.1.2&nbsp;&nbsp;</span>Investigating trends in the data</a></span></li></ul></li></ul></li><li><span><a href="#Data-Visualisations" data-toc-modified-id="Data-Visualisations-1.7"><span class="toc-item-num">1.7&nbsp;&nbsp;</span>Data Visualisations</a></span><ul class="toc-item"><li><span><a href="#Use-Seaborn's-heatmap-with-pandas-.corr()-to-visualize-correlations-between-all-numeric-features" data-toc-modified-id="Use-Seaborn's-heatmap-with-pandas-.corr()-to-visualize-correlations-between-all-numeric-features-1.7.1"><span class="toc-item-num">1.7.1&nbsp;&nbsp;</span>Use Seaborn's heatmap with pandas <code>.corr()</code> to visualize correlations between all numeric features</a></span></li><li><span><a href="#Defining-a-custom-function-to-subplot-histograms" data-toc-modified-id="Defining-a-custom-function-to-subplot-histograms-1.7.2"><span class="toc-item-num">1.7.2&nbsp;&nbsp;</span>Defining a custom function to subplot histograms</a></span></li><li><span><a href="#Plotting-and-interpretting-scatter-plots" data-toc-modified-id="Plotting-and-interpretting-scatter-plots-1.7.3"><span class="toc-item-num">1.7.3&nbsp;&nbsp;</span>Plotting and interpretting scatter plots</a></span></li><li><span><a href="#Plotting-and-interpretting-boxplots" data-toc-modified-id="Plotting-and-interpretting-boxplots-1.7.4"><span class="toc-item-num">1.7.4&nbsp;&nbsp;</span>Plotting and interpretting boxplots</a></span></li></ul></li><li><span><a href="#Descriptive-and-Inferential-Statistics" data-toc-modified-id="Descriptive-and-Inferential-Statistics-1.8"><span class="toc-item-num">1.8&nbsp;&nbsp;</span>Descriptive and Inferential Statistics</a></span><ul class="toc-item"><li><span><a href="#Studying-plots-for-Normal-distribution" data-toc-modified-id="Studying-plots-for-Normal-distribution-1.8.1"><span class="toc-item-num">1.8.1&nbsp;&nbsp;</span>Studying plots for Normal distribution</a></span></li><li><span><a href="#Limitations-of-Data" data-toc-modified-id="Limitations-of-Data-1.8.2"><span class="toc-item-num">1.8.2&nbsp;&nbsp;</span>Limitations of Data</a></span></li><li><span><a href="#Statistical-Evaluation-of-Distributions" data-toc-modified-id="Statistical-Evaluation-of-Distributions-1.8.3"><span class="toc-item-num">1.8.3&nbsp;&nbsp;</span>Statistical Evaluation of Distributions</a></span></li></ul></li><li><span><a href="#Conclusions-and-Recommendations" data-toc-modified-id="Conclusions-and-Recommendations-1.9"><span class="toc-item-num">1.9&nbsp;&nbsp;</span>Conclusions and Recommendations</a></span></li></ul></li></ul></div>

## Background

In 2018, over 2.1 million students took the US college admission tests. Most of them are taking both ACT and SAT.

This project is to study the rise in popularity of the SAT test through data available for 2017 and 2018.


SAT has since become the more popualar admission test, although ACT does dominate in the MidWest regions of the country.

A common myth is that elite colleges prefer the SAT over the ACT. In reality, all colleges and universities which require standardized testing accept BOTH the ACT and SAT. And college admissions counselors have openly stated they do not prefer one test over the other.

It is also sometimes argued that, while colleges don’t admit to preferring the SAT, the fact that many more students accepted to competitive colleges submit the SAT than ACT seems to indicate there is a bias.

reference: https://www.collegeraptor.com/getting-in/articles/act-sat/act-vs-sat-which-college-entrance-exam-is-more-popular/



## Problem statement:
- To study the scoring patterns of ACT and SAT and to position SAT as the preferred test for assessment for colleges /insittutes of higher learning
- SAT is increasingly the ‘preferred’ test with 100% participation in 5 states currently. However, the SAT board would like to expand and reach out to other states for more participants to adopt SAT as their preferred choice.

## Importing relevant libraries


```python
#Imports:
import numpy as np
import pandas as pd
import scipy.stats as stats
from scipy.stats import norm
import seaborn as sns
import matplotlib.pyplot as plt

sns.set_style('whitegrid')

%config InlineBackend.figure_format = 'retina'
%matplotlib inline
```

## 2017 Data Import and Cleaning

### Read In SAT & ACT  Data

Read in the `sat_2017.csv` and `act_2017.csv` files and assign them to appropriately named pandas dataframes.


```python
pwd
```




    'C:\\Users\\bhavn\\Desktop\\dsi_projects\\project 1\\code'




```python
#converting csv file to dataframe
act2017 = pd.read_csv('../data/act_2017.csv')
sat2017 = pd.read_csv('../data/sat_2017.csv')

```

### Display Data

Print the first 10 rows of each dataframe to your jupyter notebook


```python
act2017.head(10)
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
      <th>State</th>
      <th>Participation</th>
      <th>English</th>
      <th>Math</th>
      <th>Reading</th>
      <th>Science</th>
      <th>Composite</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>National</td>
      <td>60%</td>
      <td>20.3</td>
      <td>20.7</td>
      <td>21.4</td>
      <td>21.0</td>
      <td>21.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Alabama</td>
      <td>100%</td>
      <td>18.9</td>
      <td>18.4</td>
      <td>19.7</td>
      <td>19.4</td>
      <td>19.2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Alaska</td>
      <td>65%</td>
      <td>18.7</td>
      <td>19.8</td>
      <td>20.4</td>
      <td>19.9</td>
      <td>19.8</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Arizona</td>
      <td>62%</td>
      <td>18.6</td>
      <td>19.8</td>
      <td>20.1</td>
      <td>19.8</td>
      <td>19.7</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Arkansas</td>
      <td>100%</td>
      <td>18.9</td>
      <td>19.0</td>
      <td>19.7</td>
      <td>19.5</td>
      <td>19.4</td>
    </tr>
    <tr>
      <th>5</th>
      <td>California</td>
      <td>31%</td>
      <td>22.5</td>
      <td>22.7</td>
      <td>23.1</td>
      <td>22.2</td>
      <td>22.8</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Colorado</td>
      <td>100%</td>
      <td>20.1</td>
      <td>20.3</td>
      <td>21.2</td>
      <td>20.9</td>
      <td>20.8</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Connecticut</td>
      <td>31%</td>
      <td>25.5</td>
      <td>24.6</td>
      <td>25.6</td>
      <td>24.6</td>
      <td>25.2</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Delaware</td>
      <td>18%</td>
      <td>24.1</td>
      <td>23.4</td>
      <td>24.8</td>
      <td>23.6</td>
      <td>24.1</td>
    </tr>
    <tr>
      <th>9</th>
      <td>District of Columbia</td>
      <td>32%</td>
      <td>24.4</td>
      <td>23.5</td>
      <td>24.9</td>
      <td>23.5</td>
      <td>24.2</td>
    </tr>
  </tbody>
</table>
</div>




```python
sat2017.head(10)
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
      <th>State</th>
      <th>Participation</th>
      <th>Evidence-Based Reading and Writing</th>
      <th>Math</th>
      <th>Total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Alabama</td>
      <td>5%</td>
      <td>593</td>
      <td>572</td>
      <td>1165</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Alaska</td>
      <td>38%</td>
      <td>547</td>
      <td>533</td>
      <td>1080</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Arizona</td>
      <td>30%</td>
      <td>563</td>
      <td>553</td>
      <td>1116</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Arkansas</td>
      <td>3%</td>
      <td>614</td>
      <td>594</td>
      <td>1208</td>
    </tr>
    <tr>
      <th>4</th>
      <td>California</td>
      <td>53%</td>
      <td>531</td>
      <td>524</td>
      <td>1055</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Colorado</td>
      <td>11%</td>
      <td>606</td>
      <td>595</td>
      <td>1201</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Connecticut</td>
      <td>100%</td>
      <td>530</td>
      <td>512</td>
      <td>1041</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Delaware</td>
      <td>100%</td>
      <td>503</td>
      <td>492</td>
      <td>996</td>
    </tr>
    <tr>
      <th>8</th>
      <td>District of Columbia</td>
      <td>100%</td>
      <td>482</td>
      <td>468</td>
      <td>950</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Florida</td>
      <td>83%</td>
      <td>520</td>
      <td>497</td>
      <td>1017</td>
    </tr>
  </tbody>
</table>
</div>



###  Description of Data


ACT: The data is in columns of individual state-wise averages in participation rates(in %), English, Math, Reading, Science and Composite scores(in float)

SAT: The data is in columns of individual state-wise averages in participation rates(in %), Evidence-Based Reading and Writing, Math and Total scores (in integers)

Some of the values appear to have errors

The highest possible score on the ACT is 36. The current average ACT score is 21.
Scores below a 15 on the ACT are considered low at just about any four-year college. You can overcome low scores with a great GPA or an outstanding college application. But even if you're accepted, the school may ask you to take some remedial courses before enrolling.
Ref: https://www.princetonreview.com/college-advice/good-act-scores

Score Structure
•	Total score: 400–1600
•	Evidence-Based Reading and Writing Section: 200–800
•	Math Section: 200–800
•	SAT Essay: Three scores ranging from 2–8
Ref: https://collegereadiness.collegeboard.org/sat/scores/understanding-scores/interpreting



```python
#getting reference values from approved sources for data checking
act2017_ref = pd.read_csv('../data/ACT2017.csv')
act2017_ref.head()
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
      <th>State</th>
      <th>Participation</th>
      <th>English</th>
      <th>Math</th>
      <th>Reading</th>
      <th>Science</th>
      <th>Composite</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>National</td>
      <td>60%</td>
      <td>20.3</td>
      <td>20.7</td>
      <td>21.4</td>
      <td>21.0</td>
      <td>21.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Alabama</td>
      <td>100%</td>
      <td>18.9</td>
      <td>18.4</td>
      <td>19.7</td>
      <td>19.4</td>
      <td>19.2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Alaska</td>
      <td>65%</td>
      <td>18.7</td>
      <td>19.8</td>
      <td>20.4</td>
      <td>19.9</td>
      <td>19.8</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Arizona</td>
      <td>62%</td>
      <td>18.6</td>
      <td>19.8</td>
      <td>20.1</td>
      <td>19.8</td>
      <td>19.7</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Arkansas</td>
      <td>100%</td>
      <td>18.9</td>
      <td>19.0</td>
      <td>19.7</td>
      <td>19.5</td>
      <td>19.4</td>
    </tr>
  </tbody>
</table>
</div>



### To Fix any errors identified

**The data is available** so there's no need to guess or calculate anything. If you didn't find any errors, continue to the next step.


```python
# checking the data using .describe

act2017.describe()                
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
      <th>English</th>
      <th>Math</th>
      <th>Reading</th>
      <th>Science</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>52.000000</td>
      <td>52.000000</td>
      <td>52.000000</td>
      <td>52.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>20.919231</td>
      <td>21.173077</td>
      <td>22.001923</td>
      <td>21.040385</td>
    </tr>
    <tr>
      <th>std</th>
      <td>2.332132</td>
      <td>1.963602</td>
      <td>2.048672</td>
      <td>3.151113</td>
    </tr>
    <tr>
      <th>min</th>
      <td>16.300000</td>
      <td>18.000000</td>
      <td>18.100000</td>
      <td>2.300000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>19.000000</td>
      <td>19.400000</td>
      <td>20.475000</td>
      <td>19.900000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>20.550000</td>
      <td>20.900000</td>
      <td>21.700000</td>
      <td>21.150000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>23.300000</td>
      <td>23.100000</td>
      <td>24.125000</td>
      <td>22.525000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>25.500000</td>
      <td>25.300000</td>
      <td>26.000000</td>
      <td>24.900000</td>
    </tr>
  </tbody>
</table>
</div>




```python
# checking data using .info

act2017.info()                  
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 52 entries, 0 to 51
    Data columns (total 7 columns):
    State            52 non-null object
    Participation    52 non-null object
    English          52 non-null float64
    Math             52 non-null float64
    Reading          52 non-null float64
    Science          52 non-null float64
    Composite        52 non-null object
    dtypes: float64(4), object(3)
    memory usage: 2.9+ KB


- Observation: Errors in data to be resolved
    - Minimum for Science appears to be in error
    - Composite identified as non-null object


```python
#act2017 - Science score min is not inline with other values for one state.
#checking for values below 25$ percentile
#act2017 - 'Composite' column returned type as non-null, so identifying non-numerical input
act2017[act2017['Science']<19.9]
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
      <th>State</th>
      <th>Participation</th>
      <th>English</th>
      <th>Math</th>
      <th>Reading</th>
      <th>Science</th>
      <th>Composite</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Alabama</td>
      <td>100%</td>
      <td>18.9</td>
      <td>18.4</td>
      <td>19.7</td>
      <td>19.4</td>
      <td>19.2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Arizona</td>
      <td>62%</td>
      <td>18.6</td>
      <td>19.8</td>
      <td>20.1</td>
      <td>19.8</td>
      <td>19.7</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Arkansas</td>
      <td>100%</td>
      <td>18.9</td>
      <td>19.0</td>
      <td>19.7</td>
      <td>19.5</td>
      <td>19.4</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Florida</td>
      <td>73%</td>
      <td>19.0</td>
      <td>19.4</td>
      <td>21.0</td>
      <td>19.4</td>
      <td>19.8</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Hawaii</td>
      <td>90%</td>
      <td>17.8</td>
      <td>19.2</td>
      <td>19.2</td>
      <td>19.3</td>
      <td>19.0</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Louisiana</td>
      <td>100%</td>
      <td>19.4</td>
      <td>18.8</td>
      <td>19.8</td>
      <td>19.6</td>
      <td>19.5</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Maryland</td>
      <td>28%</td>
      <td>23.3</td>
      <td>23.1</td>
      <td>24.2</td>
      <td>2.3</td>
      <td>23.6</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Mississippi</td>
      <td>100%</td>
      <td>18.2</td>
      <td>18.1</td>
      <td>18.8</td>
      <td>18.8</td>
      <td>18.6</td>
    </tr>
    <tr>
      <th>29</th>
      <td>Nevada</td>
      <td>100%</td>
      <td>16.3</td>
      <td>18.0</td>
      <td>18.1</td>
      <td>18.2</td>
      <td>17.8</td>
    </tr>
    <tr>
      <th>34</th>
      <td>North Carolina</td>
      <td>100%</td>
      <td>17.8</td>
      <td>19.3</td>
      <td>19.6</td>
      <td>19.3</td>
      <td>19.1</td>
    </tr>
    <tr>
      <th>37</th>
      <td>Oklahoma</td>
      <td>100%</td>
      <td>18.5</td>
      <td>18.8</td>
      <td>20.1</td>
      <td>19.6</td>
      <td>19.4</td>
    </tr>
    <tr>
      <th>41</th>
      <td>South Carolina</td>
      <td>100%</td>
      <td>17.5</td>
      <td>18.6</td>
      <td>19.1</td>
      <td>18.9</td>
      <td>18.7</td>
    </tr>
  </tbody>
</table>
</div>




```python
# comparing values of individual cells with range of average score in reference document.
# values found outside the range /values with errors identified and replaced
#replacing defective values with values from act2017_ref, obtained from ACT website.

act2017.loc[21, 'Science'] = 23.2
act2017.loc[51, 'Composite'] = 20.2

```


```python
#converting 'Participation' into integer and removing '%' sign

act2017['Participation'] = act2017['Participation'].str[:-1].astype(float)
act2017.head()
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
      <th>State</th>
      <th>Participation</th>
      <th>English</th>
      <th>Math</th>
      <th>Reading</th>
      <th>Science</th>
      <th>Composite</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>National</td>
      <td>60.0</td>
      <td>20.3</td>
      <td>20.7</td>
      <td>21.4</td>
      <td>21.0</td>
      <td>21.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Alabama</td>
      <td>100.0</td>
      <td>18.9</td>
      <td>18.4</td>
      <td>19.7</td>
      <td>19.4</td>
      <td>19.2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Alaska</td>
      <td>65.0</td>
      <td>18.7</td>
      <td>19.8</td>
      <td>20.4</td>
      <td>19.9</td>
      <td>19.8</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Arizona</td>
      <td>62.0</td>
      <td>18.6</td>
      <td>19.8</td>
      <td>20.1</td>
      <td>19.8</td>
      <td>19.7</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Arkansas</td>
      <td>100.0</td>
      <td>18.9</td>
      <td>19.0</td>
      <td>19.7</td>
      <td>19.5</td>
      <td>19.4</td>
    </tr>
  </tbody>
</table>
</div>




```python
# replacing datatype

act2017['Composite']= act2017['Composite'].astype(float)
act2017.head()
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
      <th>State</th>
      <th>Participation</th>
      <th>English</th>
      <th>Math</th>
      <th>Reading</th>
      <th>Science</th>
      <th>Composite</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>National</td>
      <td>60.0</td>
      <td>20.3</td>
      <td>20.7</td>
      <td>21.4</td>
      <td>21.0</td>
      <td>21.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Alabama</td>
      <td>100.0</td>
      <td>18.9</td>
      <td>18.4</td>
      <td>19.7</td>
      <td>19.4</td>
      <td>19.2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Alaska</td>
      <td>65.0</td>
      <td>18.7</td>
      <td>19.8</td>
      <td>20.4</td>
      <td>19.9</td>
      <td>19.8</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Arizona</td>
      <td>62.0</td>
      <td>18.6</td>
      <td>19.8</td>
      <td>20.1</td>
      <td>19.8</td>
      <td>19.7</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Arkansas</td>
      <td>100.0</td>
      <td>18.9</td>
      <td>19.0</td>
      <td>19.7</td>
      <td>19.5</td>
      <td>19.4</td>
    </tr>
  </tbody>
</table>
</div>




```python
# checking for errors in data using .describe

sat2017.describe()
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
      <th>Evidence-Based Reading and Writing</th>
      <th>Math</th>
      <th>Total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>51.000000</td>
      <td>51.000000</td>
      <td>51.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>569.117647</td>
      <td>547.627451</td>
      <td>1126.098039</td>
    </tr>
    <tr>
      <th>std</th>
      <td>45.666901</td>
      <td>84.909119</td>
      <td>92.494812</td>
    </tr>
    <tr>
      <th>min</th>
      <td>482.000000</td>
      <td>52.000000</td>
      <td>950.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>533.500000</td>
      <td>522.000000</td>
      <td>1055.500000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>559.000000</td>
      <td>548.000000</td>
      <td>1107.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>613.000000</td>
      <td>599.000000</td>
      <td>1212.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>644.000000</td>
      <td>651.000000</td>
      <td>1295.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
# checking for errors in data using .info

sat2017.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 51 entries, 0 to 50
    Data columns (total 5 columns):
    State                                 51 non-null object
    Participation                         51 non-null object
    Evidence-Based Reading and Writing    51 non-null int64
    Math                                  51 non-null int64
    Total                                 51 non-null int64
    dtypes: int64(3), object(2)
    memory usage: 2.1+ KB



```python
#getting refernce values from approved sources for data checking
sat2017_ref = pd.read_csv('../data/SAT2017.csv')
sat2017_ref.head()
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
      <th>State</th>
      <th>Participation</th>
      <th>ERW</th>
      <th>Math</th>
      <th>Total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Alabama</td>
      <td>5%</td>
      <td>593</td>
      <td>572</td>
      <td>1165</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Alaska</td>
      <td>38%</td>
      <td>547</td>
      <td>533</td>
      <td>1080</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Arizona</td>
      <td>30%</td>
      <td>563</td>
      <td>553</td>
      <td>1116</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Arkansas</td>
      <td>3%</td>
      <td>614</td>
      <td>594</td>
      <td>1208</td>
    </tr>
    <tr>
      <th>4</th>
      <td>California</td>
      <td>53%</td>
      <td>531</td>
      <td>524</td>
      <td>1055</td>
    </tr>
  </tbody>
</table>
</div>




```python
#sat2017 - Math min is in variance from other min values
#checking values less than 25% percentile
#identified value of 'Maryland' is faulty and obtained correct value from sat2017_ref obtained from website
sat2017[sat2017['Math']<522]
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
      <th>State</th>
      <th>Participation</th>
      <th>Evidence-Based Reading and Writing</th>
      <th>Math</th>
      <th>Total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>6</th>
      <td>Connecticut</td>
      <td>100%</td>
      <td>530</td>
      <td>512</td>
      <td>1041</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Delaware</td>
      <td>100%</td>
      <td>503</td>
      <td>492</td>
      <td>996</td>
    </tr>
    <tr>
      <th>8</th>
      <td>District of Columbia</td>
      <td>100%</td>
      <td>482</td>
      <td>468</td>
      <td>950</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Florida</td>
      <td>83%</td>
      <td>520</td>
      <td>497</td>
      <td>1017</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Georgia</td>
      <td>61%</td>
      <td>535</td>
      <td>515</td>
      <td>1050</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Idaho</td>
      <td>93%</td>
      <td>513</td>
      <td>493</td>
      <td>1005</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Maine</td>
      <td>95%</td>
      <td>513</td>
      <td>499</td>
      <td>1012</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Maryland</td>
      <td>69%</td>
      <td>536</td>
      <td>52</td>
      <td>1060</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Michigan</td>
      <td>100%</td>
      <td>509</td>
      <td>495</td>
      <td>1005</td>
    </tr>
    <tr>
      <th>29</th>
      <td>New Hampshire</td>
      <td>96%</td>
      <td>532</td>
      <td>520</td>
      <td>1052</td>
    </tr>
    <tr>
      <th>36</th>
      <td>Oklahoma</td>
      <td>7%</td>
      <td>530</td>
      <td>517</td>
      <td>1047</td>
    </tr>
    <tr>
      <th>40</th>
      <td>South Carolina</td>
      <td>50%</td>
      <td>543</td>
      <td>521</td>
      <td>1064</td>
    </tr>
    <tr>
      <th>43</th>
      <td>Texas</td>
      <td>62%</td>
      <td>513</td>
      <td>507</td>
      <td>1020</td>
    </tr>
  </tbody>
</table>
</div>



Observation: Errors in data in sat2017
- Math min is in variance from other min values, checking values less than 25% percentile


```python
#converting Participation into float
#replacing with corrected value for Maryland.Math
sat2017['Participation'] = sat2017['Participation'].str[:-1].astype(float)
sat2017.loc[20, 'Math'] = 524
sat2017.head()
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
      <th>State</th>
      <th>Participation</th>
      <th>Evidence-Based Reading and Writing</th>
      <th>Math</th>
      <th>Total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Alabama</td>
      <td>5.0</td>
      <td>593</td>
      <td>572</td>
      <td>1165</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Alaska</td>
      <td>38.0</td>
      <td>547</td>
      <td>533</td>
      <td>1080</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Arizona</td>
      <td>30.0</td>
      <td>563</td>
      <td>553</td>
      <td>1116</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Arkansas</td>
      <td>3.0</td>
      <td>614</td>
      <td>594</td>
      <td>1208</td>
    </tr>
    <tr>
      <th>4</th>
      <td>California</td>
      <td>53.0</td>
      <td>531</td>
      <td>524</td>
      <td>1055</td>
    </tr>
  </tbody>
</table>
</div>




```python
# confirming datatypes

sat2017.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 51 entries, 0 to 50
    Data columns (total 5 columns):
    State                                 51 non-null object
    Participation                         51 non-null float64
    Evidence-Based Reading and Writing    51 non-null int64
    Math                                  51 non-null int64
    Total                                 51 non-null int64
    dtypes: float64(1), int64(3), object(1)
    memory usage: 2.1+ KB



```python
#confirming datatypes

act2017.info()
sat2017.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 52 entries, 0 to 51
    Data columns (total 7 columns):
    State            52 non-null object
    Participation    52 non-null float64
    English          52 non-null float64
    Math             52 non-null float64
    Reading          52 non-null float64
    Science          52 non-null float64
    Composite        52 non-null float64
    dtypes: float64(6), object(1)
    memory usage: 2.9+ KB
    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 51 entries, 0 to 50
    Data columns (total 5 columns):
    State                                 51 non-null object
    Participation                         51 non-null float64
    Evidence-Based Reading and Writing    51 non-null int64
    Math                                  51 non-null int64
    Total                                 51 non-null int64
    dtypes: float64(1), int64(3), object(1)
    memory usage: 2.1+ KB


### 7. Renaming Columns
Changing the names of the columns to allow for combining of data of 2017 and 2018 at later point.



```python
act2017.rename(columns={'State':'state', 'Participation':'act2017_participation',
                        'English':'act2017_eng', 'Math':'act2017_math', 'Reading':'act2017_reading',
                        'Science':'act2017_science','Composite':'act2017_composite'}, inplace=True)

act2017.head()
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
      <th>state</th>
      <th>act2017_participation</th>
      <th>act2017_eng</th>
      <th>act2017_math</th>
      <th>act2017_reading</th>
      <th>act2017_science</th>
      <th>act2017_composite</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>National</td>
      <td>60.0</td>
      <td>20.3</td>
      <td>20.7</td>
      <td>21.4</td>
      <td>21.0</td>
      <td>21.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Alabama</td>
      <td>100.0</td>
      <td>18.9</td>
      <td>18.4</td>
      <td>19.7</td>
      <td>19.4</td>
      <td>19.2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Alaska</td>
      <td>65.0</td>
      <td>18.7</td>
      <td>19.8</td>
      <td>20.4</td>
      <td>19.9</td>
      <td>19.8</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Arizona</td>
      <td>62.0</td>
      <td>18.6</td>
      <td>19.8</td>
      <td>20.1</td>
      <td>19.8</td>
      <td>19.7</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Arkansas</td>
      <td>100.0</td>
      <td>18.9</td>
      <td>19.0</td>
      <td>19.7</td>
      <td>19.5</td>
      <td>19.4</td>
    </tr>
  </tbody>
</table>
</div>




```python
#replace column names for act2017
act2017.rename(columns={'State':'state', 'Participation':'act2017_participation',
                        'English':'act2017_eng', 'Math':'act2017_math', 'Reading':'act2017_reading',
                        'Science':'act2017_science','Composite':'act2017_composite'}, inplace=True)
act2017.head()
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
      <th>state</th>
      <th>act2017_participation</th>
      <th>act2017_eng</th>
      <th>act2017_math</th>
      <th>act2017_reading</th>
      <th>act2017_science</th>
      <th>act2017_composite</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>National</td>
      <td>60.0</td>
      <td>20.3</td>
      <td>20.7</td>
      <td>21.4</td>
      <td>21.0</td>
      <td>21.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Alabama</td>
      <td>100.0</td>
      <td>18.9</td>
      <td>18.4</td>
      <td>19.7</td>
      <td>19.4</td>
      <td>19.2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Alaska</td>
      <td>65.0</td>
      <td>18.7</td>
      <td>19.8</td>
      <td>20.4</td>
      <td>19.9</td>
      <td>19.8</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Arizona</td>
      <td>62.0</td>
      <td>18.6</td>
      <td>19.8</td>
      <td>20.1</td>
      <td>19.8</td>
      <td>19.7</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Arkansas</td>
      <td>100.0</td>
      <td>18.9</td>
      <td>19.0</td>
      <td>19.7</td>
      <td>19.5</td>
      <td>19.4</td>
    </tr>
  </tbody>
</table>
</div>




```python
sat2017.columns
```




    Index(['State', 'Participation', 'Evidence-Based Reading and Writing', 'Math',
           'Total'],
          dtype='object')




```python
#replace column names for sat2017
sat2017.rename(columns={'State':'state', 'Participation':'sat2017_participation',
                        'Evidence-Based Reading and Writing':'sat2017_evi_based_read_write', 'Math':'sat2017_math', 'Total':'sat2017_total'}, inplace=True)
sat2017.head()
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
      <th>state</th>
      <th>sat2017_participation</th>
      <th>sat2017_evi_based_read_write</th>
      <th>sat2017_math</th>
      <th>sat2017_total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Alabama</td>
      <td>5.0</td>
      <td>593</td>
      <td>572</td>
      <td>1165</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Alaska</td>
      <td>38.0</td>
      <td>547</td>
      <td>533</td>
      <td>1080</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Arizona</td>
      <td>30.0</td>
      <td>563</td>
      <td>553</td>
      <td>1116</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Arkansas</td>
      <td>3.0</td>
      <td>614</td>
      <td>594</td>
      <td>1208</td>
    </tr>
    <tr>
      <th>4</th>
      <td>California</td>
      <td>53.0</td>
      <td>531</td>
      <td>524</td>
      <td>1055</td>
    </tr>
  </tbody>
</table>
</div>




```python
sat2017.columns
```




    Index(['state', 'sat2017_participation', 'sat2017_evi_based_read_write',
           'sat2017_math', 'sat2017_total'],
          dtype='object')




```python
sat2017['sat2017_evi_based_read_write']= sat2017['sat2017_evi_based_read_write'].astype(float)
sat2017['sat2017_math']= sat2017['sat2017_math'].astype(float)
sat2017['sat2017_total']= sat2017['sat2017_total'].astype(float)
```


```python

```

### Creating a data dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**state**| *object* | ACT /SAT |Name of State|
|**act2017/2018_participation** | *float* | ACT|average %|
|**act2017/2018_eng**| *float* | ACT |average score|
|**act2017/2018_math**| *float* | ACT |average score|
|**act2017/2018_reading** | *float* | ACT |average score|
|**act2017/2018_science** | *float* | ACT |average score|
|**act2017/2018_composite**|*float*|ACT |average score|
|**sat2017/2018_participation**| *float* | SAT |average %|
|**sat2017/2018_evi_based_read_write**| *float* |SAT|average score|
|**sat2017/2018_math**| *float* | SAT |average score|
|**sat2017/2018_total**| *float* | SAT |average score|


### Dropping extra rows

One of our dataframes contains an extra row. Identify and remove this from the dataframe.


```python
# dropping of extra rows

act2017 = act2017.drop(0, axis=0)
act2017.head()
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
      <th>state</th>
      <th>act2017_participation</th>
      <th>act2017_eng</th>
      <th>act2017_math</th>
      <th>act2017_reading</th>
      <th>act2017_science</th>
      <th>act2017_composite</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Alabama</td>
      <td>100.0</td>
      <td>18.9</td>
      <td>18.4</td>
      <td>19.7</td>
      <td>19.4</td>
      <td>19.2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Alaska</td>
      <td>65.0</td>
      <td>18.7</td>
      <td>19.8</td>
      <td>20.4</td>
      <td>19.9</td>
      <td>19.8</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Arizona</td>
      <td>62.0</td>
      <td>18.6</td>
      <td>19.8</td>
      <td>20.1</td>
      <td>19.8</td>
      <td>19.7</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Arkansas</td>
      <td>100.0</td>
      <td>18.9</td>
      <td>19.0</td>
      <td>19.7</td>
      <td>19.5</td>
      <td>19.4</td>
    </tr>
    <tr>
      <th>5</th>
      <td>California</td>
      <td>31.0</td>
      <td>22.5</td>
      <td>22.7</td>
      <td>23.1</td>
      <td>22.2</td>
      <td>22.8</td>
    </tr>
  </tbody>
</table>
</div>



### Merging Dataframes

Join the 2017 ACT and SAT dataframes using the state in each dataframe as the key. Assign this to a new variable.


```python
# combining dataframes

jt2017 = pd.merge(act2017, sat2017, on='state', how='outer' )
jt2017.head(10)
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
      <th>state</th>
      <th>act2017_participation</th>
      <th>act2017_eng</th>
      <th>act2017_math</th>
      <th>act2017_reading</th>
      <th>act2017_science</th>
      <th>act2017_composite</th>
      <th>sat2017_participation</th>
      <th>sat2017_evi_based_read_write</th>
      <th>sat2017_math</th>
      <th>sat2017_total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Alabama</td>
      <td>100.0</td>
      <td>18.9</td>
      <td>18.4</td>
      <td>19.7</td>
      <td>19.4</td>
      <td>19.2</td>
      <td>5.0</td>
      <td>593.0</td>
      <td>572.0</td>
      <td>1165.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Alaska</td>
      <td>65.0</td>
      <td>18.7</td>
      <td>19.8</td>
      <td>20.4</td>
      <td>19.9</td>
      <td>19.8</td>
      <td>38.0</td>
      <td>547.0</td>
      <td>533.0</td>
      <td>1080.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Arizona</td>
      <td>62.0</td>
      <td>18.6</td>
      <td>19.8</td>
      <td>20.1</td>
      <td>19.8</td>
      <td>19.7</td>
      <td>30.0</td>
      <td>563.0</td>
      <td>553.0</td>
      <td>1116.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Arkansas</td>
      <td>100.0</td>
      <td>18.9</td>
      <td>19.0</td>
      <td>19.7</td>
      <td>19.5</td>
      <td>19.4</td>
      <td>3.0</td>
      <td>614.0</td>
      <td>594.0</td>
      <td>1208.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>California</td>
      <td>31.0</td>
      <td>22.5</td>
      <td>22.7</td>
      <td>23.1</td>
      <td>22.2</td>
      <td>22.8</td>
      <td>53.0</td>
      <td>531.0</td>
      <td>524.0</td>
      <td>1055.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Colorado</td>
      <td>100.0</td>
      <td>20.1</td>
      <td>20.3</td>
      <td>21.2</td>
      <td>20.9</td>
      <td>20.8</td>
      <td>11.0</td>
      <td>606.0</td>
      <td>595.0</td>
      <td>1201.0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Connecticut</td>
      <td>31.0</td>
      <td>25.5</td>
      <td>24.6</td>
      <td>25.6</td>
      <td>24.6</td>
      <td>25.2</td>
      <td>100.0</td>
      <td>530.0</td>
      <td>512.0</td>
      <td>1041.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Delaware</td>
      <td>18.0</td>
      <td>24.1</td>
      <td>23.4</td>
      <td>24.8</td>
      <td>23.6</td>
      <td>24.1</td>
      <td>100.0</td>
      <td>503.0</td>
      <td>492.0</td>
      <td>996.0</td>
    </tr>
    <tr>
      <th>8</th>
      <td>District of Columbia</td>
      <td>32.0</td>
      <td>24.4</td>
      <td>23.5</td>
      <td>24.9</td>
      <td>23.5</td>
      <td>24.2</td>
      <td>100.0</td>
      <td>482.0</td>
      <td>468.0</td>
      <td>950.0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Florida</td>
      <td>73.0</td>
      <td>19.0</td>
      <td>19.4</td>
      <td>21.0</td>
      <td>19.4</td>
      <td>19.8</td>
      <td>83.0</td>
      <td>520.0</td>
      <td>497.0</td>
      <td>1017.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
# to know number of rows and columns

jt2017.shape
```




    (51, 11)



### Saving dataframe as csv



```python
 #saving data as csv file

jt2017.to_csv('../data/combined_2017.csv')
```

## 2018 Data Import and Cleaning

Links to the 2018 ACT and SAT data are provided in the README. These data live in PDFs, and so you'll get to enjoy practicing some *manual* data collection. Save these data as a CSV in your `data` directory, and import, explore, and clean these data in the same way you did above. **Make sure you comment on your steps so it is clear *why* you are doing each process**.


```python
# converting to dataframe
act2018 = pd.read_csv('../data/act_2018.csv')
sat2018 = pd.read_csv('../data/sat_2018.csv')

```


```python
act2018.head(10)
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
      <th>State</th>
      <th>Percentage of Students Tested</th>
      <th>Average Composite Score</th>
      <th>Average English Score</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>Average Science Score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Alabama</td>
      <td>100</td>
      <td>19.1</td>
      <td>18.9</td>
      <td>18.3</td>
      <td>19.6</td>
      <td>19.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Alaska</td>
      <td>33</td>
      <td>20.8</td>
      <td>19.8</td>
      <td>20.6</td>
      <td>21.6</td>
      <td>20.7</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Arizona</td>
      <td>66</td>
      <td>19.2</td>
      <td>18.2</td>
      <td>19.4</td>
      <td>19.5</td>
      <td>19.2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Arkansas</td>
      <td>100</td>
      <td>19.4</td>
      <td>19.1</td>
      <td>18.9</td>
      <td>19.7</td>
      <td>19.4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>California</td>
      <td>27</td>
      <td>22.7</td>
      <td>22.5</td>
      <td>22.5</td>
      <td>23.0</td>
      <td>22.1</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Colorado</td>
      <td>30</td>
      <td>23.9</td>
      <td>23.9</td>
      <td>23.2</td>
      <td>24.4</td>
      <td>23.5</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Connecticut</td>
      <td>26</td>
      <td>25.6</td>
      <td>26.0</td>
      <td>24.8</td>
      <td>26.1</td>
      <td>24.9</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Delaware</td>
      <td>17</td>
      <td>23.2</td>
      <td>23.7</td>
      <td>23.1</td>
      <td>24.5</td>
      <td>23.4</td>
    </tr>
    <tr>
      <th>8</th>
      <td>District of Columbia</td>
      <td>32</td>
      <td>23.6</td>
      <td>23.7</td>
      <td>22.7</td>
      <td>24.4</td>
      <td>23.0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Florida</td>
      <td>66</td>
      <td>19.9</td>
      <td>19.2</td>
      <td>19.3</td>
      <td>21.1</td>
      <td>19.5</td>
    </tr>
  </tbody>
</table>
</div>




```python
# to know number of rows and columns

act2018.shape
```




    (52, 7)




```python
# checking dataset with .info()

act2018.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 52 entries, 0 to 51
    Data columns (total 7 columns):
    State                            52 non-null object
    Percentage of Students Tested    52 non-null object
    Average Composite Score          52 non-null float64
    Average English Score            52 non-null float64
    Average Math Score               52 non-null float64
    Average Reading Score            52 non-null float64
    Average Science Score            52 non-null float64
    dtypes: float64(5), object(2)
    memory usage: 2.9+ KB



```python
# to know column index

act2018.columns
```




    Index(['State', 'Percentage of Students Tested', 'Average Composite Score',
           'Average English Score', 'Average Math Score', 'Average Reading Score',
           'Average Science Score'],
          dtype='object')




```python
# renaming of columns
act2018.rename(columns={'State':'state', 'Percentage of Students Tested':'act2018_participation',
                        'Average Composite Score':'act2018_composite',
                        'Average English Score':'act2018_eng',
                        'Average Math Score':'act2018_math',
                        'Average Reading Score':'act2018_reading',
                        'Average Science Score':'act2018_science'}, inplace=True)
act2018.head()
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
      <th>state</th>
      <th>act2018_participation</th>
      <th>act2018_composite</th>
      <th>act2018_eng</th>
      <th>act2018_math</th>
      <th>act2018_reading</th>
      <th>act2018_science</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Alabama</td>
      <td>100</td>
      <td>19.1</td>
      <td>18.9</td>
      <td>18.3</td>
      <td>19.6</td>
      <td>19.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Alaska</td>
      <td>33</td>
      <td>20.8</td>
      <td>19.8</td>
      <td>20.6</td>
      <td>21.6</td>
      <td>20.7</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Arizona</td>
      <td>66</td>
      <td>19.2</td>
      <td>18.2</td>
      <td>19.4</td>
      <td>19.5</td>
      <td>19.2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Arkansas</td>
      <td>100</td>
      <td>19.4</td>
      <td>19.1</td>
      <td>18.9</td>
      <td>19.7</td>
      <td>19.4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>California</td>
      <td>27</td>
      <td>22.7</td>
      <td>22.5</td>
      <td>22.5</td>
      <td>23.0</td>
      <td>22.1</td>
    </tr>
  </tbody>
</table>
</div>




```python
# confirming details with .describe

act2018.describe()
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
      <th>act2018_composite</th>
      <th>act2018_eng</th>
      <th>act2018_math</th>
      <th>act2018_reading</th>
      <th>act2018_science</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>52.000000</td>
      <td>52.000000</td>
      <td>52.000000</td>
      <td>52.000000</td>
      <td>52.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>21.473077</td>
      <td>20.973077</td>
      <td>21.113462</td>
      <td>22.001923</td>
      <td>21.332692</td>
    </tr>
    <tr>
      <th>std</th>
      <td>2.087696</td>
      <td>2.424719</td>
      <td>2.017573</td>
      <td>2.148186</td>
      <td>1.853848</td>
    </tr>
    <tr>
      <th>min</th>
      <td>17.700000</td>
      <td>16.600000</td>
      <td>17.800000</td>
      <td>18.000000</td>
      <td>17.900000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>19.975000</td>
      <td>19.100000</td>
      <td>19.400000</td>
      <td>20.475000</td>
      <td>19.925000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>21.050000</td>
      <td>20.200000</td>
      <td>20.650000</td>
      <td>21.450000</td>
      <td>20.950000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>23.525000</td>
      <td>23.700000</td>
      <td>23.125000</td>
      <td>24.050000</td>
      <td>23.025000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>25.600000</td>
      <td>26.000000</td>
      <td>25.200000</td>
      <td>26.100000</td>
      <td>24.900000</td>
    </tr>
  </tbody>
</table>
</div>




```python
# confirming details with .info

act2018.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 52 entries, 0 to 51
    Data columns (total 7 columns):
    state                    52 non-null object
    act2018_participation    52 non-null object
    act2018_composite        52 non-null float64
    act2018_eng              52 non-null float64
    act2018_math             52 non-null float64
    act2018_reading          52 non-null float64
    act2018_science          52 non-null float64
    dtypes: float64(5), object(2)
    memory usage: 2.9+ KB



```python
# identifying location of missing data

act2018[(act2018['act2018_participation'] == 'Not given') ]

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
      <th>state</th>
      <th>act2018_participation</th>
      <th>act2018_composite</th>
      <th>act2018_eng</th>
      <th>act2018_math</th>
      <th>act2018_reading</th>
      <th>act2018_science</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>18</th>
      <td>Louisiana</td>
      <td>Not given</td>
      <td>19.2</td>
      <td>19.0</td>
      <td>18.5</td>
      <td>19.6</td>
      <td>19.1</td>
    </tr>
    <tr>
      <th>33</th>
      <td>North Carolina</td>
      <td>Not given</td>
      <td>19.1</td>
      <td>18.0</td>
      <td>19.3</td>
      <td>19.5</td>
      <td>19.2</td>
    </tr>
    <tr>
      <th>36</th>
      <td>Oklahoma</td>
      <td>Not given</td>
      <td>19.3</td>
      <td>18.4</td>
      <td>18.8</td>
      <td>20.1</td>
      <td>19.4</td>
    </tr>
    <tr>
      <th>38</th>
      <td>Pennsylvania</td>
      <td>Not given</td>
      <td>23.5</td>
      <td>23.3</td>
      <td>23.2</td>
      <td>24.0</td>
      <td>23.1</td>
    </tr>
    <tr>
      <th>51</th>
      <td>National</td>
      <td>Not given</td>
      <td>20.8</td>
      <td>20.2</td>
      <td>20.5</td>
      <td>21.3</td>
      <td>20.7</td>
    </tr>
  </tbody>
</table>
</div>




```python
#replacing 'Not given' with values from reference doc


act2018.loc[18, 'act2018_participation'] = 100
act2018.loc[33, 'act2018_participation'] = 100
act2018.loc[36, 'act2018_participation'] = 100
act2018.loc[38, 'act2018_participation'] = 20
act2018.loc[51, 'act2018_participation'] = 55

```


```python
# change to float
act2018['act2018_participation']= act2018['act2018_participation'].astype(float)
act2018.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 52 entries, 0 to 51
    Data columns (total 7 columns):
    state                    52 non-null object
    act2018_participation    52 non-null float64
    act2018_composite        52 non-null float64
    act2018_eng              52 non-null float64
    act2018_math             52 non-null float64
    act2018_reading          52 non-null float64
    act2018_science          52 non-null float64
    dtypes: float64(6), object(1)
    memory usage: 2.9+ KB



```python
# size of dataframe

act2018 = act2018.drop(51, axis=0)
act2018.shape
```




    (51, 7)




```python
sat2018.head()
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
      <th>State</th>
      <th>Participation</th>
      <th>Evidence-Based Reading and Writing</th>
      <th>Math</th>
      <th>Total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Alabama</td>
      <td>6%</td>
      <td>595</td>
      <td>571</td>
      <td>1166</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Alaska</td>
      <td>43%</td>
      <td>562</td>
      <td>544</td>
      <td>1106</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Arizona</td>
      <td>29%</td>
      <td>577</td>
      <td>572</td>
      <td>1149</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Arkansas</td>
      <td>5%</td>
      <td>592</td>
      <td>576</td>
      <td>1169</td>
    </tr>
    <tr>
      <th>4</th>
      <td>California</td>
      <td>60%</td>
      <td>540</td>
      <td>536</td>
      <td>1076</td>
    </tr>
  </tbody>
</table>
</div>




```python
# to know details using .info

sat2018.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 51 entries, 0 to 50
    Data columns (total 5 columns):
    State                                 51 non-null object
    Participation                         51 non-null object
    Evidence-Based Reading and Writing    51 non-null int64
    Math                                  51 non-null int64
    Total                                 51 non-null int64
    dtypes: int64(3), object(2)
    memory usage: 2.1+ KB



```python
#to know details using .describe()

sat2018.describe()
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
      <th>Evidence-Based Reading and Writing</th>
      <th>Math</th>
      <th>Total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>51.000000</td>
      <td>51.000000</td>
      <td>51.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>563.686275</td>
      <td>556.235294</td>
      <td>1120.019608</td>
    </tr>
    <tr>
      <th>std</th>
      <td>47.502627</td>
      <td>47.772623</td>
      <td>94.155083</td>
    </tr>
    <tr>
      <th>min</th>
      <td>480.000000</td>
      <td>480.000000</td>
      <td>977.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>534.500000</td>
      <td>522.500000</td>
      <td>1057.500000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>552.000000</td>
      <td>544.000000</td>
      <td>1098.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>610.500000</td>
      <td>593.500000</td>
      <td>1204.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>643.000000</td>
      <td>655.000000</td>
      <td>1298.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
# conversion string to float

sat2018['Participation'] = sat2018['Participation'].str[:-1].astype(float)
sat2018.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 51 entries, 0 to 50
    Data columns (total 5 columns):
    State                                 51 non-null object
    Participation                         51 non-null float64
    Evidence-Based Reading and Writing    51 non-null int64
    Math                                  51 non-null int64
    Total                                 51 non-null int64
    dtypes: float64(1), int64(3), object(1)
    memory usage: 2.1+ KB



```python
# to know column index

sat2018.columns
```




    Index(['State', 'Participation', 'Evidence-Based Reading and Writing', 'Math',
           'Total'],
          dtype='object')




```python
sat2018.rename(columns={'State':'state',
                        'Participation':'sat2018_participation',
                        'Evidence-Based Reading and Writing':'sat2018_evi_based_read_write',
                        'Math':'sat2018_math',
                        'Total':'sat2018_total'}, inplace=True)
sat2018.head()
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
      <th>state</th>
      <th>sat2018_participation</th>
      <th>sat2018_evi_based_read_write</th>
      <th>sat2018_math</th>
      <th>sat2018_total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Alabama</td>
      <td>6.0</td>
      <td>595</td>
      <td>571</td>
      <td>1166</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Alaska</td>
      <td>43.0</td>
      <td>562</td>
      <td>544</td>
      <td>1106</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Arizona</td>
      <td>29.0</td>
      <td>577</td>
      <td>572</td>
      <td>1149</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Arkansas</td>
      <td>5.0</td>
      <td>592</td>
      <td>576</td>
      <td>1169</td>
    </tr>
    <tr>
      <th>4</th>
      <td>California</td>
      <td>60.0</td>
      <td>540</td>
      <td>536</td>
      <td>1076</td>
    </tr>
  </tbody>
</table>
</div>




```python
# changing datatype to float

sat2018['sat2018_evi_based_read_write']= sat2018['sat2018_evi_based_read_write'].astype(float)
sat2018['sat2018_math']= sat2018['sat2018_math'].astype(float)
sat2018['sat2018_total']= sat2018['sat2018_total'].astype(float)
```


```python
sat2018.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 51 entries, 0 to 50
    Data columns (total 5 columns):
    state                           51 non-null object
    sat2018_participation           51 non-null float64
    sat2018_evi_based_read_write    51 non-null float64
    sat2018_math                    51 non-null float64
    sat2018_total                   51 non-null float64
    dtypes: float64(4), object(1)
    memory usage: 2.1+ KB



```python
# combining ACT2018 and SAT2018

jt2018 = pd.merge(act2018, sat2018, on='state', how='outer' )
jt2018.head(10)
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
      <th>state</th>
      <th>act2018_participation</th>
      <th>act2018_composite</th>
      <th>act2018_eng</th>
      <th>act2018_math</th>
      <th>act2018_reading</th>
      <th>act2018_science</th>
      <th>sat2018_participation</th>
      <th>sat2018_evi_based_read_write</th>
      <th>sat2018_math</th>
      <th>sat2018_total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Alabama</td>
      <td>100.0</td>
      <td>19.1</td>
      <td>18.9</td>
      <td>18.3</td>
      <td>19.6</td>
      <td>19.0</td>
      <td>6.0</td>
      <td>595.0</td>
      <td>571.0</td>
      <td>1166.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Alaska</td>
      <td>33.0</td>
      <td>20.8</td>
      <td>19.8</td>
      <td>20.6</td>
      <td>21.6</td>
      <td>20.7</td>
      <td>43.0</td>
      <td>562.0</td>
      <td>544.0</td>
      <td>1106.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Arizona</td>
      <td>66.0</td>
      <td>19.2</td>
      <td>18.2</td>
      <td>19.4</td>
      <td>19.5</td>
      <td>19.2</td>
      <td>29.0</td>
      <td>577.0</td>
      <td>572.0</td>
      <td>1149.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Arkansas</td>
      <td>100.0</td>
      <td>19.4</td>
      <td>19.1</td>
      <td>18.9</td>
      <td>19.7</td>
      <td>19.4</td>
      <td>5.0</td>
      <td>592.0</td>
      <td>576.0</td>
      <td>1169.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>California</td>
      <td>27.0</td>
      <td>22.7</td>
      <td>22.5</td>
      <td>22.5</td>
      <td>23.0</td>
      <td>22.1</td>
      <td>60.0</td>
      <td>540.0</td>
      <td>536.0</td>
      <td>1076.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Colorado</td>
      <td>30.0</td>
      <td>23.9</td>
      <td>23.9</td>
      <td>23.2</td>
      <td>24.4</td>
      <td>23.5</td>
      <td>100.0</td>
      <td>519.0</td>
      <td>506.0</td>
      <td>1025.0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Connecticut</td>
      <td>26.0</td>
      <td>25.6</td>
      <td>26.0</td>
      <td>24.8</td>
      <td>26.1</td>
      <td>24.9</td>
      <td>100.0</td>
      <td>535.0</td>
      <td>519.0</td>
      <td>1053.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Delaware</td>
      <td>17.0</td>
      <td>23.2</td>
      <td>23.7</td>
      <td>23.1</td>
      <td>24.5</td>
      <td>23.4</td>
      <td>100.0</td>
      <td>505.0</td>
      <td>492.0</td>
      <td>998.0</td>
    </tr>
    <tr>
      <th>8</th>
      <td>District of Columbia</td>
      <td>32.0</td>
      <td>23.6</td>
      <td>23.7</td>
      <td>22.7</td>
      <td>24.4</td>
      <td>23.0</td>
      <td>92.0</td>
      <td>497.0</td>
      <td>480.0</td>
      <td>977.0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Florida</td>
      <td>66.0</td>
      <td>19.9</td>
      <td>19.2</td>
      <td>19.3</td>
      <td>21.1</td>
      <td>19.5</td>
      <td>56.0</td>
      <td>550.0</td>
      <td>549.0</td>
      <td>1099.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
jt2018.shape
```




    (51, 11)




```python
#saving data as csv file

jt2018.to_csv('../data/combined_2018.csv')
```

### Combining 2017 and 2018 data into a single dataframe



```python
#combining data for 2017 and 2018

final = pd.merge(jt2017, jt2018, on='state', how='outer' )
final.head(10)
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
      <th>state</th>
      <th>act2017_participation</th>
      <th>act2017_eng</th>
      <th>act2017_math</th>
      <th>act2017_reading</th>
      <th>act2017_science</th>
      <th>act2017_composite</th>
      <th>sat2017_participation</th>
      <th>sat2017_evi_based_read_write</th>
      <th>sat2017_math</th>
      <th>...</th>
      <th>act2018_participation</th>
      <th>act2018_composite</th>
      <th>act2018_eng</th>
      <th>act2018_math</th>
      <th>act2018_reading</th>
      <th>act2018_science</th>
      <th>sat2018_participation</th>
      <th>sat2018_evi_based_read_write</th>
      <th>sat2018_math</th>
      <th>sat2018_total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Alabama</td>
      <td>100.0</td>
      <td>18.9</td>
      <td>18.4</td>
      <td>19.7</td>
      <td>19.4</td>
      <td>19.2</td>
      <td>5.0</td>
      <td>593.0</td>
      <td>572.0</td>
      <td>...</td>
      <td>100.0</td>
      <td>19.1</td>
      <td>18.9</td>
      <td>18.3</td>
      <td>19.6</td>
      <td>19.0</td>
      <td>6.0</td>
      <td>595.0</td>
      <td>571.0</td>
      <td>1166.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Alaska</td>
      <td>65.0</td>
      <td>18.7</td>
      <td>19.8</td>
      <td>20.4</td>
      <td>19.9</td>
      <td>19.8</td>
      <td>38.0</td>
      <td>547.0</td>
      <td>533.0</td>
      <td>...</td>
      <td>33.0</td>
      <td>20.8</td>
      <td>19.8</td>
      <td>20.6</td>
      <td>21.6</td>
      <td>20.7</td>
      <td>43.0</td>
      <td>562.0</td>
      <td>544.0</td>
      <td>1106.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Arizona</td>
      <td>62.0</td>
      <td>18.6</td>
      <td>19.8</td>
      <td>20.1</td>
      <td>19.8</td>
      <td>19.7</td>
      <td>30.0</td>
      <td>563.0</td>
      <td>553.0</td>
      <td>...</td>
      <td>66.0</td>
      <td>19.2</td>
      <td>18.2</td>
      <td>19.4</td>
      <td>19.5</td>
      <td>19.2</td>
      <td>29.0</td>
      <td>577.0</td>
      <td>572.0</td>
      <td>1149.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Arkansas</td>
      <td>100.0</td>
      <td>18.9</td>
      <td>19.0</td>
      <td>19.7</td>
      <td>19.5</td>
      <td>19.4</td>
      <td>3.0</td>
      <td>614.0</td>
      <td>594.0</td>
      <td>...</td>
      <td>100.0</td>
      <td>19.4</td>
      <td>19.1</td>
      <td>18.9</td>
      <td>19.7</td>
      <td>19.4</td>
      <td>5.0</td>
      <td>592.0</td>
      <td>576.0</td>
      <td>1169.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>California</td>
      <td>31.0</td>
      <td>22.5</td>
      <td>22.7</td>
      <td>23.1</td>
      <td>22.2</td>
      <td>22.8</td>
      <td>53.0</td>
      <td>531.0</td>
      <td>524.0</td>
      <td>...</td>
      <td>27.0</td>
      <td>22.7</td>
      <td>22.5</td>
      <td>22.5</td>
      <td>23.0</td>
      <td>22.1</td>
      <td>60.0</td>
      <td>540.0</td>
      <td>536.0</td>
      <td>1076.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Colorado</td>
      <td>100.0</td>
      <td>20.1</td>
      <td>20.3</td>
      <td>21.2</td>
      <td>20.9</td>
      <td>20.8</td>
      <td>11.0</td>
      <td>606.0</td>
      <td>595.0</td>
      <td>...</td>
      <td>30.0</td>
      <td>23.9</td>
      <td>23.9</td>
      <td>23.2</td>
      <td>24.4</td>
      <td>23.5</td>
      <td>100.0</td>
      <td>519.0</td>
      <td>506.0</td>
      <td>1025.0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Connecticut</td>
      <td>31.0</td>
      <td>25.5</td>
      <td>24.6</td>
      <td>25.6</td>
      <td>24.6</td>
      <td>25.2</td>
      <td>100.0</td>
      <td>530.0</td>
      <td>512.0</td>
      <td>...</td>
      <td>26.0</td>
      <td>25.6</td>
      <td>26.0</td>
      <td>24.8</td>
      <td>26.1</td>
      <td>24.9</td>
      <td>100.0</td>
      <td>535.0</td>
      <td>519.0</td>
      <td>1053.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Delaware</td>
      <td>18.0</td>
      <td>24.1</td>
      <td>23.4</td>
      <td>24.8</td>
      <td>23.6</td>
      <td>24.1</td>
      <td>100.0</td>
      <td>503.0</td>
      <td>492.0</td>
      <td>...</td>
      <td>17.0</td>
      <td>23.2</td>
      <td>23.7</td>
      <td>23.1</td>
      <td>24.5</td>
      <td>23.4</td>
      <td>100.0</td>
      <td>505.0</td>
      <td>492.0</td>
      <td>998.0</td>
    </tr>
    <tr>
      <th>8</th>
      <td>District of Columbia</td>
      <td>32.0</td>
      <td>24.4</td>
      <td>23.5</td>
      <td>24.9</td>
      <td>23.5</td>
      <td>24.2</td>
      <td>100.0</td>
      <td>482.0</td>
      <td>468.0</td>
      <td>...</td>
      <td>32.0</td>
      <td>23.6</td>
      <td>23.7</td>
      <td>22.7</td>
      <td>24.4</td>
      <td>23.0</td>
      <td>92.0</td>
      <td>497.0</td>
      <td>480.0</td>
      <td>977.0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Florida</td>
      <td>73.0</td>
      <td>19.0</td>
      <td>19.4</td>
      <td>21.0</td>
      <td>19.4</td>
      <td>19.8</td>
      <td>83.0</td>
      <td>520.0</td>
      <td>497.0</td>
      <td>...</td>
      <td>66.0</td>
      <td>19.9</td>
      <td>19.2</td>
      <td>19.3</td>
      <td>21.1</td>
      <td>19.5</td>
      <td>56.0</td>
      <td>550.0</td>
      <td>549.0</td>
      <td>1099.0</td>
    </tr>
  </tbody>
</table>
<p>10 rows × 21 columns</p>
</div>




```python
# confirming size of dataframe

final.shape
```




    (51, 21)




```python
#saving data as csv file

final.to_csv('../data/final.csv')
```

## Exploratory Data Analysis


### Summary Statistics
Transpose the output of pandas `describe` method to create a quick overview of each numeric feature.


```python
# to transpose the describe function for 'final'
final.describe().T
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
      <th>count</th>
      <th>mean</th>
      <th>std</th>
      <th>min</th>
      <th>25%</th>
      <th>50%</th>
      <th>75%</th>
      <th>max</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>act2017_participation</th>
      <td>51.0</td>
      <td>65.254902</td>
      <td>32.140842</td>
      <td>8.0</td>
      <td>31.00</td>
      <td>69.0</td>
      <td>100.00</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>act2017_eng</th>
      <td>51.0</td>
      <td>20.931373</td>
      <td>2.353677</td>
      <td>16.3</td>
      <td>19.00</td>
      <td>20.7</td>
      <td>23.30</td>
      <td>25.5</td>
    </tr>
    <tr>
      <th>act2017_math</th>
      <td>51.0</td>
      <td>21.182353</td>
      <td>1.981989</td>
      <td>18.0</td>
      <td>19.40</td>
      <td>20.9</td>
      <td>23.10</td>
      <td>25.3</td>
    </tr>
    <tr>
      <th>act2017_reading</th>
      <td>51.0</td>
      <td>22.013725</td>
      <td>2.067271</td>
      <td>18.1</td>
      <td>20.45</td>
      <td>21.8</td>
      <td>24.15</td>
      <td>26.0</td>
    </tr>
    <tr>
      <th>act2017_science</th>
      <td>51.0</td>
      <td>21.450980</td>
      <td>1.739353</td>
      <td>18.2</td>
      <td>19.95</td>
      <td>21.3</td>
      <td>23.20</td>
      <td>24.9</td>
    </tr>
    <tr>
      <th>act2017_composite</th>
      <td>51.0</td>
      <td>21.519608</td>
      <td>2.020695</td>
      <td>17.8</td>
      <td>19.80</td>
      <td>21.4</td>
      <td>23.60</td>
      <td>25.5</td>
    </tr>
    <tr>
      <th>sat2017_participation</th>
      <td>51.0</td>
      <td>39.803922</td>
      <td>35.276632</td>
      <td>2.0</td>
      <td>4.00</td>
      <td>38.0</td>
      <td>66.00</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>sat2017_evi_based_read_write</th>
      <td>51.0</td>
      <td>569.117647</td>
      <td>45.666901</td>
      <td>482.0</td>
      <td>533.50</td>
      <td>559.0</td>
      <td>613.00</td>
      <td>644.0</td>
    </tr>
    <tr>
      <th>sat2017_math</th>
      <td>51.0</td>
      <td>556.882353</td>
      <td>47.121395</td>
      <td>468.0</td>
      <td>523.50</td>
      <td>548.0</td>
      <td>599.00</td>
      <td>651.0</td>
    </tr>
    <tr>
      <th>sat2017_total</th>
      <td>51.0</td>
      <td>1126.098039</td>
      <td>92.494812</td>
      <td>950.0</td>
      <td>1055.50</td>
      <td>1107.0</td>
      <td>1212.00</td>
      <td>1295.0</td>
    </tr>
    <tr>
      <th>act2018_participation</th>
      <td>51.0</td>
      <td>61.647059</td>
      <td>34.080976</td>
      <td>7.0</td>
      <td>28.50</td>
      <td>66.0</td>
      <td>100.00</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>act2018_composite</th>
      <td>51.0</td>
      <td>21.486275</td>
      <td>2.106278</td>
      <td>17.7</td>
      <td>19.95</td>
      <td>21.3</td>
      <td>23.55</td>
      <td>25.6</td>
    </tr>
    <tr>
      <th>act2018_eng</th>
      <td>51.0</td>
      <td>20.988235</td>
      <td>2.446356</td>
      <td>16.6</td>
      <td>19.10</td>
      <td>20.2</td>
      <td>23.70</td>
      <td>26.0</td>
    </tr>
    <tr>
      <th>act2018_math</th>
      <td>51.0</td>
      <td>21.125490</td>
      <td>2.035765</td>
      <td>17.8</td>
      <td>19.40</td>
      <td>20.7</td>
      <td>23.15</td>
      <td>25.2</td>
    </tr>
    <tr>
      <th>act2018_reading</th>
      <td>51.0</td>
      <td>22.015686</td>
      <td>2.167245</td>
      <td>18.0</td>
      <td>20.45</td>
      <td>21.6</td>
      <td>24.10</td>
      <td>26.1</td>
    </tr>
    <tr>
      <th>act2018_science</th>
      <td>51.0</td>
      <td>21.345098</td>
      <td>1.870114</td>
      <td>17.9</td>
      <td>19.85</td>
      <td>21.1</td>
      <td>23.05</td>
      <td>24.9</td>
    </tr>
    <tr>
      <th>sat2018_participation</th>
      <td>51.0</td>
      <td>45.745098</td>
      <td>37.314256</td>
      <td>2.0</td>
      <td>4.50</td>
      <td>52.0</td>
      <td>77.50</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>sat2018_evi_based_read_write</th>
      <td>51.0</td>
      <td>563.686275</td>
      <td>47.502627</td>
      <td>480.0</td>
      <td>534.50</td>
      <td>552.0</td>
      <td>610.50</td>
      <td>643.0</td>
    </tr>
    <tr>
      <th>sat2018_math</th>
      <td>51.0</td>
      <td>556.235294</td>
      <td>47.772623</td>
      <td>480.0</td>
      <td>522.50</td>
      <td>544.0</td>
      <td>593.50</td>
      <td>655.0</td>
    </tr>
    <tr>
      <th>sat2018_total</th>
      <td>51.0</td>
      <td>1120.019608</td>
      <td>94.155083</td>
      <td>977.0</td>
      <td>1057.50</td>
      <td>1098.0</td>
      <td>1204.00</td>
      <td>1298.0</td>
    </tr>
  </tbody>
</table>
</div>



- Observations:
    - Looking at average scores for individual subjects, the difference in mean and median (50% percentile) indicates the skewness of the data.
    - Skewness for ACT Math score has increased in 2018
    - Skewness for SAT Reading and Math scores is evident in both 2017 and 2018


```python
#comparing ACT scores stats fo 2017 and 2018

final[['act2017_math', 'act2018_math']].describe()
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
      <th>act2017_math</th>
      <th>act2018_math</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>51.000000</td>
      <td>51.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>21.182353</td>
      <td>21.125490</td>
    </tr>
    <tr>
      <th>std</th>
      <td>1.981989</td>
      <td>2.035765</td>
    </tr>
    <tr>
      <th>min</th>
      <td>18.000000</td>
      <td>17.800000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>19.400000</td>
      <td>19.400000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>20.900000</td>
      <td>20.700000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>23.100000</td>
      <td>23.150000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>25.300000</td>
      <td>25.200000</td>
    </tr>
  </tbody>
</table>
</div>




```python
# comparing SAT scores stats for 2017 and 2018

final[['sat2017_evi_based_read_write', 'sat2018_evi_based_read_write', 'sat2017_math', 'sat2018_math']].describe()
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
      <th>sat2017_evi_based_read_write</th>
      <th>sat2018_evi_based_read_write</th>
      <th>sat2017_math</th>
      <th>sat2018_math</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>51.000000</td>
      <td>51.000000</td>
      <td>51.000000</td>
      <td>51.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>569.117647</td>
      <td>563.686275</td>
      <td>556.882353</td>
      <td>556.235294</td>
    </tr>
    <tr>
      <th>std</th>
      <td>45.666901</td>
      <td>47.502627</td>
      <td>47.121395</td>
      <td>47.772623</td>
    </tr>
    <tr>
      <th>min</th>
      <td>482.000000</td>
      <td>480.000000</td>
      <td>468.000000</td>
      <td>480.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>533.500000</td>
      <td>534.500000</td>
      <td>523.500000</td>
      <td>522.500000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>559.000000</td>
      <td>552.000000</td>
      <td>548.000000</td>
      <td>544.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>613.000000</td>
      <td>610.500000</td>
      <td>599.000000</td>
      <td>593.500000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>644.000000</td>
      <td>643.000000</td>
      <td>651.000000</td>
      <td>655.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
#confirming number of rows

len(final.index)
```




    51




```python
# confirming number of columns

len(final.columns)
```




    21




```python
# confirming details with .info

final.info()
```

    <class 'pandas.core.frame.DataFrame'>
    Int64Index: 51 entries, 0 to 50
    Data columns (total 21 columns):
    state                           51 non-null object
    act2017_participation           51 non-null float64
    act2017_eng                     51 non-null float64
    act2017_math                    51 non-null float64
    act2017_reading                 51 non-null float64
    act2017_science                 51 non-null float64
    act2017_composite               51 non-null float64
    sat2017_participation           51 non-null float64
    sat2017_evi_based_read_write    51 non-null float64
    sat2017_math                    51 non-null float64
    sat2017_total                   51 non-null float64
    act2018_participation           51 non-null float64
    act2018_composite               51 non-null float64
    act2018_eng                     51 non-null float64
    act2018_math                    51 non-null float64
    act2018_reading                 51 non-null float64
    act2018_science                 51 non-null float64
    sat2018_participation           51 non-null float64
    sat2018_evi_based_read_write    51 non-null float64
    sat2018_math                    51 non-null float64
    sat2018_total                   51 non-null float64
    dtypes: float64(20), object(1)
    memory usage: 8.8+ KB


#### Manually calculating standard deviation

$$\sigma = \sqrt{\frac{1}{n}\sum_{i=1}^n(x_i - \mu)^2}$$

- Writing a function to calculate standard deviation using the formula above


```python
# calculation of std deviation

import math

def calc_std_dev(numbers):
    num_sum=0
    sq_sum=0
    num_sum = np.sum(numbers)
    mean = num_sum/(len(numbers))
    for i in numbers:
        sq_sum = sq_sum +((i - mean)**2)
    std_dev = math.sqrt(sq_sum/(len(numbers)))
    return std_dev


calc_std_dev(final['act2017_participation'])

```




    31.824175751231806



Comparing manually calculated standard deviations match up with the output from pandas `describe`? What about numpy's `std` method?


```python
np.std(final['act2017_participation'])
```




    31.824175751231806




```python
#Calcn of Std Dev using function

df_dict = {col: calc_std_dev(final[col]) for col in final.columns[1:]}
df_dict
```




    {'act2017_participation': 31.824175751231806,
     'act2017_eng': 2.3304876369363363,
     'act2017_math': 1.9624620273436781,
     'act2017_reading': 2.0469029314842646,
     'act2017_science': 1.7222161451443676,
     'act2017_composite': 2.000786081581989,
     'sat2017_participation': 34.92907076664508,
     'sat2017_evi_based_read_write': 45.21697020437866,
     'sat2017_math': 46.65713364485503,
     'sat2017_total': 91.58351056778743,
     'act2018_participation': 33.745194881997506,
     'act2018_composite': 2.0855261815801147,
     'act2018_eng': 2.4222536143202795,
     'act2018_math': 2.0157072555557174,
     'act2018_reading': 2.145891884510421,
     'act2018_science': 1.851688548483354,
     'sat2018_participation': 36.946619223539415,
     'sat2018_evi_based_read_write': 47.03460978357609,
     'sat2018_math': 47.30194550378352,
     'sat2018_total': 93.22742384464433}



Answer: There are minor differences in the values calculated manually and using the pandas.describe.
The manually calculated values, do however, match with numpy's std method.
Difference could be due to the variation in degrees of freedom

#### Investigating trends in the data
To consider the following questions:

- Which states have the highest and lowest participation rates for the:
    - 2017 SAT?
    - 2018 SAT?
    - 2017 ACT?
    - 2018 ACT?
- Which states have the highest and lowest mean total/composite scores for the:
    - 2017 SAT?
    - 2018 SAT?
    - 2017 ACT?
    - 2018 ACT?
- Do any states with 100% participation on a given test have a rate change year-to-year?
- Do any states show have >50% participation on *both* tests either year?




```python
final.columns
```




    Index(['state', 'act2017_participation', 'act2017_eng', 'act2017_math',
           'act2017_reading', 'act2017_science', 'act2017_composite',
           'sat2017_participation', 'sat2017_evi_based_read_write', 'sat2017_math',
           'sat2017_total', 'act2018_participation', 'act2018_composite',
           'act2018_eng', 'act2018_math', 'act2018_reading', 'act2018_science',
           'sat2018_participation', 'sat2018_evi_based_read_write', 'sat2018_math',
           'sat2018_total'],
          dtype='object')




```python
# highest participation rates

final.sort_values(['act2017_participation'], ascending = False).head(20)[['state','act2017_participation']]

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
      <th>state</th>
      <th>act2017_participation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Alabama</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Kentucky</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>49</th>
      <td>Wisconsin</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>44</th>
      <td>Utah</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>42</th>
      <td>Tennessee</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>40</th>
      <td>South Carolina</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>36</th>
      <td>Oklahoma</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>33</th>
      <td>North Carolina</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Nevada</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Montana</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Mississippi</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Minnesota</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Louisiana</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Missouri</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>50</th>
      <td>Wyoming</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Colorado</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Arkansas</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>34</th>
      <td>North Dakota</td>
      <td>98.0</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Illinois</td>
      <td>93.0</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Hawaii</td>
      <td>90.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
# highest participation rates

final.sort_values(['sat2017_participation'], ascending = False).head(10)[['state','sat2017_participation']]

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
      <th>state</th>
      <th>sat2017_participation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>8</th>
      <td>District of Columbia</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Michigan</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Connecticut</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Delaware</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>29</th>
      <td>New Hampshire</td>
      <td>96.0</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Maine</td>
      <td>95.0</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Idaho</td>
      <td>93.0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Florida</td>
      <td>83.0</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Massachusetts</td>
      <td>76.0</td>
    </tr>
    <tr>
      <th>39</th>
      <td>Rhode Island</td>
      <td>71.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
# highest participation rates

final.sort_values(['act2018_participation'], ascending = False).head(20)[['state','act2018_participation']]

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
      <th>state</th>
      <th>act2018_participation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Alabama</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Kentucky</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>49</th>
      <td>Wisconsin</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>44</th>
      <td>Utah</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>42</th>
      <td>Tennessee</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>40</th>
      <td>South Carolina</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>36</th>
      <td>Oklahoma</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>35</th>
      <td>Ohio</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>33</th>
      <td>North Carolina</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Nevada</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Nebraska</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Montana</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Mississippi</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Louisiana</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Missouri</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>50</th>
      <td>Wyoming</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Arkansas</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Minnesota</td>
      <td>99.0</td>
    </tr>
    <tr>
      <th>34</th>
      <td>North Dakota</td>
      <td>98.0</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Hawaii</td>
      <td>89.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
# highest participation rates

final.sort_values(['sat2018_participation'], ascending = False).head(10)[['state','sat2017_participation','sat2018_participation']]

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
      <th>state</th>
      <th>sat2017_participation</th>
      <th>sat2018_participation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>5</th>
      <td>Colorado</td>
      <td>11.0</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Connecticut</td>
      <td>100.0</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Delaware</td>
      <td>100.0</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Michigan</td>
      <td>100.0</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Idaho</td>
      <td>93.0</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Maine</td>
      <td>95.0</td>
      <td>99.0</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Illinois</td>
      <td>9.0</td>
      <td>99.0</td>
    </tr>
    <tr>
      <th>39</th>
      <td>Rhode Island</td>
      <td>71.0</td>
      <td>97.0</td>
    </tr>
    <tr>
      <th>29</th>
      <td>New Hampshire</td>
      <td>96.0</td>
      <td>96.0</td>
    </tr>
    <tr>
      <th>8</th>
      <td>District of Columbia</td>
      <td>100.0</td>
      <td>92.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
#lowest participation rates
final.sort_values(['act2017_participation'], ascending = False).tail()[['state','act2017_participation']]

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
      <th>state</th>
      <th>act2017_participation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>38</th>
      <td>Pennsylvania</td>
      <td>23.0</td>
    </tr>
    <tr>
      <th>39</th>
      <td>Rhode Island</td>
      <td>21.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Delaware</td>
      <td>18.0</td>
    </tr>
    <tr>
      <th>29</th>
      <td>New Hampshire</td>
      <td>18.0</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Maine</td>
      <td>8.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
#lowest participation rates
final.sort_values(['sat2017_participation'], ascending = False).tail(15)[['state','sat2017_participation']]

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
      <th>state</th>
      <th>sat2017_participation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>42</th>
      <td>Tennessee</td>
      <td>5.0</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Kentucky</td>
      <td>4.0</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Kansas</td>
      <td>4.0</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Louisiana</td>
      <td>4.0</td>
    </tr>
    <tr>
      <th>44</th>
      <td>Utah</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>49</th>
      <td>Wisconsin</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Missouri</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>41</th>
      <td>South Dakota</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Nebraska</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Minnesota</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Arkansas</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>50</th>
      <td>Wyoming</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>34</th>
      <td>North Dakota</td>
      <td>2.0</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Mississippi</td>
      <td>2.0</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Iowa</td>
      <td>2.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
#lowest participation rates
final.sort_values(['act2018_participation'], ascending = False).tail()[['state','act2018_participation']]

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
      <th>state</th>
      <th>act2018_participation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>38</th>
      <td>Pennsylvania</td>
      <td>20.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Delaware</td>
      <td>17.0</td>
    </tr>
    <tr>
      <th>29</th>
      <td>New Hampshire</td>
      <td>16.0</td>
    </tr>
    <tr>
      <th>39</th>
      <td>Rhode Island</td>
      <td>15.0</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Maine</td>
      <td>7.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
#lowest participation rates
final.sort_values(['sat2018_participation'], ascending = False).tail(10)[['state','sat2017_participation','sat2018_participation']]

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
      <th>state</th>
      <th>sat2017_participation</th>
      <th>sat2018_participation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>18</th>
      <td>Louisiana</td>
      <td>4.0</td>
      <td>4.0</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Kentucky</td>
      <td>4.0</td>
      <td>4.0</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Kansas</td>
      <td>4.0</td>
      <td>4.0</td>
    </tr>
    <tr>
      <th>41</th>
      <td>South Dakota</td>
      <td>3.0</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Nebraska</td>
      <td>3.0</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Mississippi</td>
      <td>2.0</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Iowa</td>
      <td>2.0</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>49</th>
      <td>Wisconsin</td>
      <td>3.0</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>50</th>
      <td>Wyoming</td>
      <td>3.0</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>34</th>
      <td>North Dakota</td>
      <td>2.0</td>
      <td>2.0</td>
    </tr>
  </tbody>
</table>
</div>



Answer: The participation in the college admission test has increased, due to various factors. Some of the contributing factors are:
1. Mandatory requirements for admission to institutes of higher learning
2. Fee waivers offered by states
3. Increased push by pushed to expand its market share in recent years by revising the test and entering into deals with numerous states and school systems to give students the exam.

The increasing number of students has impacted the state average scores of the tests themselves. This study is also another opportunity to assess the performance of the 2017 and 2018 cohorts in the ACT and SAT tests.

Ref:
1. https://en.wikipedia.org/wiki/List_of_standardized_tests_in_the_United_States#Admissions_tests
2. https://www.usnews.com/education/best-colleges/articles/2018-01-23/how-to-take-the-sat-act-for-free
3. https://www.edweek.org/ew/articles/2017/09/07/us-students-scores-inch-up-on-latest.html

Participation rate in the ACT has been steady for the two years. However, an increased number of states hjave achieved 100% participation rate for SAT as can be seen from plots (below).


```python
import matplotlib.patches as mpatches

plt.figure(figsize= (6,6))
plt.hist(final['act2017_participation'], bins = 10, color='g', alpha = 0.5)
plt.hist(final['sat2017_participation'], bins = 10, color='r', alpha = 0.5)
plt.xlabel('Participaton rates', position = (0,0), ha = 'left', color = 'grey') # (x,y)
plt.ylabel("Number of states", position = (0, 1), ha = 'right', color = 'grey')
plt.suptitle('ACT and SAT 2017', fontsize=14, fontweight='bold')
red_patch = mpatches.Patch(color='r', alpha = 0.5, label='SAT 2017')
green_patch = mpatches.Patch(color='g', alpha = 0.5, label='ACT 2017')
plt.legend(handles=[red_patch, green_patch])
;     
```




    '    '




![png](project1_code_link_files/project1_code_link_104_1.png)



```python
import matplotlib.patches as mpatches

plt.figure(figsize= (6,6))
plt.hist(final['act2018_participation'], bins = 10, color='g', alpha = 0.5)
plt.hist(final['sat2018_participation'], bins = 10, color='r', alpha = 0.5)
plt.xlabel('Participaton rates', position = (0,0), ha = 'left', color = 'grey') # (x,y)
plt.ylabel("Number of states", position = (0, 1), ha = 'right', color = 'grey')
plt.suptitle('ACT and SAT 2018', fontsize=14, fontweight='bold')
red_patch = mpatches.Patch(color='r', alpha = 0.5, label='SAT 2018')
green_patch = mpatches.Patch(color='g', alpha = 0.5, label='ACT 2018')
plt.legend(handles=[red_patch, green_patch])
;     
```




    '    '




![png](project1_code_link_files/project1_code_link_105_1.png)



```python
final.columns
```




    Index(['state', 'act2017_participation', 'act2017_eng', 'act2017_math',
           'act2017_reading', 'act2017_science', 'act2017_composite',
           'sat2017_participation', 'sat2017_evi_based_read_write', 'sat2017_math',
           'sat2017_total', 'act2018_participation', 'act2018_composite',
           'act2018_eng', 'act2018_math', 'act2018_reading', 'act2018_science',
           'sat2018_participation', 'sat2018_evi_based_read_write', 'sat2018_math',
           'sat2018_total'],
          dtype='object')




```python
composite = final[['act2017_composite', 'act2018_composite', 'sat2017_total', 'sat2018_total']]
composite.head()
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
      <th>act2017_composite</th>
      <th>act2018_composite</th>
      <th>sat2017_total</th>
      <th>sat2018_total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>19.2</td>
      <td>19.1</td>
      <td>1165.0</td>
      <td>1166.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>19.8</td>
      <td>20.8</td>
      <td>1080.0</td>
      <td>1106.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>19.7</td>
      <td>19.2</td>
      <td>1116.0</td>
      <td>1149.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>19.4</td>
      <td>19.4</td>
      <td>1208.0</td>
      <td>1169.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>22.8</td>
      <td>22.7</td>
      <td>1055.0</td>
      <td>1076.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
# states have the highest mean total/composite scores

final.sort_values(['act2017_composite'], ascending = False).head()[['state','act2017_composite']]
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
      <th>state</th>
      <th>act2017_composite</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>29</th>
      <td>New Hampshire</td>
      <td>25.5</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Massachusetts</td>
      <td>25.4</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Connecticut</td>
      <td>25.2</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Maine</td>
      <td>24.3</td>
    </tr>
    <tr>
      <th>8</th>
      <td>District of Columbia</td>
      <td>24.2</td>
    </tr>
  </tbody>
</table>
</div>




```python
# states have the highest mean total/composite scores

final.sort_values(['act2018_composite'], ascending = False).head()[['state','act2018_composite']]

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
      <th>state</th>
      <th>act2018_composite</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>6</th>
      <td>Connecticut</td>
      <td>25.6</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Massachusetts</td>
      <td>25.5</td>
    </tr>
    <tr>
      <th>29</th>
      <td>New Hampshire</td>
      <td>25.1</td>
    </tr>
    <tr>
      <th>32</th>
      <td>New York</td>
      <td>24.5</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Michigan</td>
      <td>24.4</td>
    </tr>
  </tbody>
</table>
</div>




```python
# states have the highest mean total/composite scores
final.sort_values(['sat2017_total'], ascending = False).head()[['state','sat2017_total']]
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
      <th>state</th>
      <th>sat2017_total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>23</th>
      <td>Minnesota</td>
      <td>1295.0</td>
    </tr>
    <tr>
      <th>49</th>
      <td>Wisconsin</td>
      <td>1291.0</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Iowa</td>
      <td>1275.0</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Missouri</td>
      <td>1271.0</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Kansas</td>
      <td>1260.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
# states have the highest mean total/composite scores
final.sort_values(['sat2018_total'], ascending = False).head()[['state','sat2018_total']]
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
      <th>state</th>
      <th>sat2018_total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>23</th>
      <td>Minnesota</td>
      <td>1298.0</td>
    </tr>
    <tr>
      <th>49</th>
      <td>Wisconsin</td>
      <td>1294.0</td>
    </tr>
    <tr>
      <th>34</th>
      <td>North Dakota</td>
      <td>1283.0</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Iowa</td>
      <td>1265.0</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Kansas</td>
      <td>1265.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
# states have the lowest mean total/composite scores

final.sort_values(['act2017_composite'], ascending = False).tail()[['state','act2017_composite']]

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
      <th>state</th>
      <th>act2017_composite</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>33</th>
      <td>North Carolina</td>
      <td>19.1</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Hawaii</td>
      <td>19.0</td>
    </tr>
    <tr>
      <th>40</th>
      <td>South Carolina</td>
      <td>18.7</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Mississippi</td>
      <td>18.6</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Nevada</td>
      <td>17.8</td>
    </tr>
  </tbody>
</table>
</div>




```python
# states have the lowest mean total/composite scores

final.sort_values(['act2018_composite'], ascending = False).tail()[['state','act2018_composite']]

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
      <th>state</th>
      <th>act2018_composite</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Alabama</td>
      <td>19.1</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Hawaii</td>
      <td>18.9</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Mississippi</td>
      <td>18.6</td>
    </tr>
    <tr>
      <th>40</th>
      <td>South Carolina</td>
      <td>18.3</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Nevada</td>
      <td>17.7</td>
    </tr>
  </tbody>
</table>
</div>




```python
# states have the lowest mean total/composite scores
final.sort_values(['sat2017_total'], ascending = False).tail()[['state','sat2017_total']]
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
      <th>state</th>
      <th>sat2017_total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>19</th>
      <td>Maine</td>
      <td>1012.0</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Idaho</td>
      <td>1005.0</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Michigan</td>
      <td>1005.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Delaware</td>
      <td>996.0</td>
    </tr>
    <tr>
      <th>8</th>
      <td>District of Columbia</td>
      <td>950.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
# states have the lowest mean total/composite scores
final.sort_values(['sat2018_total'], ascending = False).tail()[['state','sat2018_total']]
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
      <th>state</th>
      <th>sat2018_total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>11</th>
      <td>Hawaii</td>
      <td>1010.0</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Idaho</td>
      <td>1001.0</td>
    </tr>
    <tr>
      <th>48</th>
      <td>West Virginia</td>
      <td>999.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Delaware</td>
      <td>998.0</td>
    </tr>
    <tr>
      <th>8</th>
      <td>District of Columbia</td>
      <td>977.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Do any states with 100% participation on a given test have a rate change year-to-year?

final[(final['act2017_participation'] == 100)][['state','act2017_composite', 'act2018_composite']]
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
      <th>state</th>
      <th>act2017_composite</th>
      <th>act2018_composite</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Alabama</td>
      <td>19.2</td>
      <td>19.1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Arkansas</td>
      <td>19.4</td>
      <td>19.4</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Colorado</td>
      <td>20.8</td>
      <td>23.9</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Kentucky</td>
      <td>20.0</td>
      <td>20.2</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Louisiana</td>
      <td>19.5</td>
      <td>19.2</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Minnesota</td>
      <td>21.5</td>
      <td>21.3</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Mississippi</td>
      <td>18.6</td>
      <td>18.6</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Missouri</td>
      <td>20.4</td>
      <td>20.0</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Montana</td>
      <td>20.3</td>
      <td>20.0</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Nevada</td>
      <td>17.8</td>
      <td>17.7</td>
    </tr>
    <tr>
      <th>33</th>
      <td>North Carolina</td>
      <td>19.1</td>
      <td>19.1</td>
    </tr>
    <tr>
      <th>36</th>
      <td>Oklahoma</td>
      <td>19.4</td>
      <td>19.3</td>
    </tr>
    <tr>
      <th>40</th>
      <td>South Carolina</td>
      <td>18.7</td>
      <td>18.3</td>
    </tr>
    <tr>
      <th>42</th>
      <td>Tennessee</td>
      <td>19.8</td>
      <td>19.6</td>
    </tr>
    <tr>
      <th>44</th>
      <td>Utah</td>
      <td>20.3</td>
      <td>20.4</td>
    </tr>
    <tr>
      <th>49</th>
      <td>Wisconsin</td>
      <td>20.5</td>
      <td>20.5</td>
    </tr>
    <tr>
      <th>50</th>
      <td>Wyoming</td>
      <td>20.2</td>
      <td>20.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Do any states show have >50% participation on both tests either year?

high_participation = ((final['act2017_participation']> 50) & (final['sat2017_participation']> 50))
final[high_participation]
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
      <th>state</th>
      <th>act2017_participation</th>
      <th>act2017_eng</th>
      <th>act2017_math</th>
      <th>act2017_reading</th>
      <th>act2017_science</th>
      <th>act2017_composite</th>
      <th>sat2017_participation</th>
      <th>sat2017_evi_based_read_write</th>
      <th>sat2017_math</th>
      <th>...</th>
      <th>act2018_participation</th>
      <th>act2018_composite</th>
      <th>act2018_eng</th>
      <th>act2018_math</th>
      <th>act2018_reading</th>
      <th>act2018_science</th>
      <th>sat2018_participation</th>
      <th>sat2018_evi_based_read_write</th>
      <th>sat2018_math</th>
      <th>sat2018_total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>9</th>
      <td>Florida</td>
      <td>73.0</td>
      <td>19.0</td>
      <td>19.4</td>
      <td>21.0</td>
      <td>19.4</td>
      <td>19.8</td>
      <td>83.0</td>
      <td>520.0</td>
      <td>497.0</td>
      <td>...</td>
      <td>66.0</td>
      <td>19.9</td>
      <td>19.2</td>
      <td>19.3</td>
      <td>21.1</td>
      <td>19.5</td>
      <td>56.0</td>
      <td>550.0</td>
      <td>549.0</td>
      <td>1099.0</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Georgia</td>
      <td>55.0</td>
      <td>21.0</td>
      <td>20.9</td>
      <td>22.0</td>
      <td>21.3</td>
      <td>21.4</td>
      <td>61.0</td>
      <td>535.0</td>
      <td>515.0</td>
      <td>...</td>
      <td>53.0</td>
      <td>21.4</td>
      <td>20.9</td>
      <td>20.7</td>
      <td>21.2</td>
      <td>21.4</td>
      <td>70.0</td>
      <td>542.0</td>
      <td>522.0</td>
      <td>1064.0</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Hawaii</td>
      <td>90.0</td>
      <td>17.8</td>
      <td>19.2</td>
      <td>19.2</td>
      <td>19.3</td>
      <td>19.0</td>
      <td>55.0</td>
      <td>544.0</td>
      <td>541.0</td>
      <td>...</td>
      <td>89.0</td>
      <td>18.9</td>
      <td>18.2</td>
      <td>19.0</td>
      <td>19.1</td>
      <td>19.0</td>
      <td>56.0</td>
      <td>480.0</td>
      <td>530.0</td>
      <td>1010.0</td>
    </tr>
  </tbody>
</table>
<p>3 rows × 21 columns</p>
</div>




```python
high_participation_2 = ((final['act2017_participation']< 20) & (final['sat2017_participation']> 80))
final[high_participation_2]
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
      <th>state</th>
      <th>act2017_participation</th>
      <th>act2017_eng</th>
      <th>act2017_math</th>
      <th>act2017_reading</th>
      <th>act2017_science</th>
      <th>act2017_composite</th>
      <th>sat2017_participation</th>
      <th>sat2017_evi_based_read_write</th>
      <th>sat2017_math</th>
      <th>...</th>
      <th>act2018_participation</th>
      <th>act2018_composite</th>
      <th>act2018_eng</th>
      <th>act2018_math</th>
      <th>act2018_reading</th>
      <th>act2018_science</th>
      <th>sat2018_participation</th>
      <th>sat2018_evi_based_read_write</th>
      <th>sat2018_math</th>
      <th>sat2018_total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>7</th>
      <td>Delaware</td>
      <td>18.0</td>
      <td>24.1</td>
      <td>23.4</td>
      <td>24.8</td>
      <td>23.6</td>
      <td>24.1</td>
      <td>100.0</td>
      <td>503.0</td>
      <td>492.0</td>
      <td>...</td>
      <td>17.0</td>
      <td>23.2</td>
      <td>23.7</td>
      <td>23.1</td>
      <td>24.5</td>
      <td>23.4</td>
      <td>100.0</td>
      <td>505.0</td>
      <td>492.0</td>
      <td>998.0</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Maine</td>
      <td>8.0</td>
      <td>24.2</td>
      <td>24.0</td>
      <td>24.8</td>
      <td>23.7</td>
      <td>24.3</td>
      <td>95.0</td>
      <td>513.0</td>
      <td>499.0</td>
      <td>...</td>
      <td>7.0</td>
      <td>24.0</td>
      <td>23.8</td>
      <td>23.6</td>
      <td>24.7</td>
      <td>23.4</td>
      <td>99.0</td>
      <td>512.0</td>
      <td>501.0</td>
      <td>1013.0</td>
    </tr>
    <tr>
      <th>29</th>
      <td>New Hampshire</td>
      <td>18.0</td>
      <td>25.4</td>
      <td>25.1</td>
      <td>26.0</td>
      <td>24.9</td>
      <td>25.5</td>
      <td>96.0</td>
      <td>532.0</td>
      <td>520.0</td>
      <td>...</td>
      <td>16.0</td>
      <td>25.1</td>
      <td>25.1</td>
      <td>24.7</td>
      <td>25.6</td>
      <td>24.4</td>
      <td>96.0</td>
      <td>535.0</td>
      <td>528.0</td>
      <td>1063.0</td>
    </tr>
  </tbody>
</table>
<p>3 rows × 21 columns</p>
</div>




```python
# checking if the data distribution is Normal

for a in final.columns[1:]:
    print(a,stats.normaltest(final[a]))
```

    act2017_participation NormaltestResult(statistic=72.50510406893655, pvalue=1.8018419611696254e-16)
    act2017_eng NormaltestResult(statistic=4.945616782086351, pvalue=0.08434764489205682)
    act2017_math NormaltestResult(statistic=6.547294554392776, pvalue=0.03786805958606832)
    act2017_reading NormaltestResult(statistic=6.248639549660324, pvalue=0.04396683079879635)
    act2017_science NormaltestResult(statistic=5.501326521192349, pvalue=0.0638854744336635)
    act2017_composite NormaltestResult(statistic=6.557389886662569, pvalue=0.03767739587231253)
    sat2017_participation NormaltestResult(statistic=24.844012826931053, pvalue=4.028943345766873e-06)
    sat2017_evi_based_read_write NormaltestResult(statistic=13.81815328788405, pvalue=0.0009986795076584)
    sat2017_math NormaltestResult(statistic=5.762201767738943, pvalue=0.056072998982864684)
    sat2017_total NormaltestResult(statistic=9.607185954097002, pvalue=0.008200230814088539)
    act2018_participation NormaltestResult(statistic=142.42948808997522, pvalue=1.1798576998141957e-31)
    act2018_composite NormaltestResult(statistic=8.70683791505615, pvalue=0.012862760086159716)
    act2018_eng NormaltestResult(statistic=8.998260111683463, pvalue=0.011118664949764285)
    act2018_math NormaltestResult(statistic=9.493830792428861, pvalue=0.008678423456739134)
    act2018_reading NormaltestResult(statistic=9.408698591449367, pvalue=0.009055804952130748)
    act2018_science NormaltestResult(statistic=9.088915467210416, pvalue=0.010625933240751445)
    sat2018_participation NormaltestResult(statistic=52.62387132138218, pvalue=3.739999415853251e-12)
    sat2018_evi_based_read_write NormaltestResult(statistic=8.010167731290034, pvalue=0.01822276093099164)
    sat2018_math NormaltestResult(statistic=4.8457529089366815, pvalue=0.08866620599134843)
    sat2018_total NormaltestResult(statistic=8.459129644249382, pvalue=0.014558724804979849)


Answer: p-value is less than alpha (0.05) and hence the distribution of the following are not Normal.
act2017_math
act2017_reading
sat2017_evi_based_read_write
act2018_eng
act2018_math
act2018_reading
act2018_science
sat2018_math

For the following, since p-value is greater than alpha, there is insufficient evidence to show that the distribution is Normal.
act2017_eng
act2017_science
sat2017_math
sat2018_evi_based_read_write

The higher number of non-Normal distributions could be probable due to the increased number of students taking up the tests and hence skewing the distribution toward the lower scores.

## Data Visualisations

### Use Seaborn's heatmap with pandas `.corr()` to visualize correlations between all numeric features

Heatmaps are generally not appropriate for presentations, and should often be excluded from reports as they can be visually overwhelming. **However**, they can be extremely useful in identify relationships of potential interest (as well as identifying potential collinearity before modeling).

*example*:
```python
sns.heatmap(df.corr())
```


```python
import seaborn as sns
```


```python
plt.figure(figsize=(12, 12))


mask = np.zeros_like(final.corr())
mask[np.triu_indices_from(mask)] = True
with sns.axes_style("white"):
    sns.heatmap(final.corr(), mask=mask, vmax=0.3, square=True, annot=True)
```


![png](project1_code_link_files/project1_code_link_124_0.png)


Answer: The heatmap gives a snapshot of the correlation of various averge scores. A high correlation between individual averages shows that likely they

For example, the corellation between SAT Reading 2017 is very strong and SAT Math 2017 is 0.99. The positive value indicates that students who do well in one of them will also do well in the other.

### Defining a custom function to subplot histograms



```python
def subplot_histograms(dataframe, list_of_columns, list_of_titles, list_of_xlabels):
    nrows = int(np.ceil(len(list_of_columns)/2))
    fig, ax = plt.subplots(nrows=nrows, ncols=2, figsize=(16,12))
    ax = ax.ravel()
    for i, column in enumerate(list_of_columns):  
        sns.distplot(dataframe[column], ax=ax[i], fit=norm, bins =10, kde=True)
        #ax[i].hist(dataframe[column]),
        ax[i].set_title(list_of_titles[i]),
        ax[i].set_xlabel(list_of_xlabels[i],
        )

```


Plotting histograms for each of the following:
- Participation rates for SAT & ACT
- Math scores for SAT & ACT
- Reading/verbal scores for SAT & ACT


```python
# Participation rates for SAT & ACT

partpn_cols =['act2017_participation', 'act2018_participation',
              'sat2017_participation', 'sat2018_participation' ]
partpn_titles = ['ACT 2017', 'ACT 2018', 'SAT 2017', 'SAT 2018']
partpn_xlabels = ['% participation', '% participation', '% participation', '% participation']

# y axis shows number of states with level of participation (in %) as given in x-axis

```


```python
subplot_histograms(final, partpn_cols, partpn_titles, partpn_xlabels )
```


![png](project1_code_link_files/project1_code_link_130_0.png)


Answer: The participation rates are near normal in distribution.
ACT is supported in many states with fee waivers and about 13 states have recorded 100% participation (11 of them consistent over the two years)

On the other hand, the higher levels of participation in SAT can be seen in the histogram plots above. This could be largely due to the pushing of SAT to be the preferred test for college admissions by the relevant Board.  


```python
# Math scores for SAT & ACT
math_cols =['act2017_math', 'act2018_math',
              'sat2017_math', 'sat2018_math' ]
math_titles = ['ACT 2017 MATH', 'ACT 2018 MATH', 'SAT 2017 MATH', 'SAT 2018 MATH']
math_xlabels = ['ave score range', 'ave score range', 'ave score range', 'ave score range']
```


```python
subplot_histograms(final, math_cols, math_titles, math_xlabels )
```


![png](project1_code_link_files/project1_code_link_133_0.png)


Answer: Math scores are generally found to be left skewed, although the year-on-year movement in SAT scores distribution towards normal distribution can be noted.


```python
# Reading/verbal scores for SAT & ACT

reading_cols =['act2017_reading', 'act2018_reading',
              'sat2017_evi_based_read_write', 'sat2018_evi_based_read_write' ]
reading_titles = ['ACT 2017 READING', 'ACT 2018 READING', 'SAT 2017 READING', 'SAT 2018 READING']
reading_xlabels = ['ave score range', 'ave score range', 'ave score range', 'ave score range']
```


```python
subplot_histograms(final, reading_cols, reading_titles, reading_xlabels )
```


![png](project1_code_link_files/project1_code_link_136_0.png)


Answer: Similarly, Reading scores are generally found to be left skewed, although the year-on-year movement in SAT scores distribution towards normal distribution can be noted.

### Plotting and interpretting scatter plots

For each of the following:
- SAT vs. ACT math scores for 2017
- SAT vs. ACT verbal/reading scores for 2017
- SAT vs. ACT total/composite scores for 2017
- Total scores for SAT 2017 vs. 2018
- Composite scores for ACT 2017 vs. 2018




```python
# SAT vs. ACT math scores for 2017

sns.regplot(x="act2017_math", y="sat2017_math", data=final);
```


![png](project1_code_link_files/project1_code_link_139_0.png)



```python
# SAT vs. ACT verbal/reading scores for 2017

sns.regplot(x="act2017_reading", y="sat2017_evi_based_read_write", data=final);
```


![png](project1_code_link_files/project1_code_link_140_0.png)



```python
# SAT vs. ACT total/composite scores for 2017

sns.regplot(x="act2017_composite", y="sat2017_total", data=final);
```


![png](project1_code_link_files/project1_code_link_141_0.png)


Answer: A negative corellation between ACT and SAT topics was noted. This is probably due to participants selecting one test over another as has been observed earlier. Trend of moving from ACT to SAT as implemented  


```python
# Total scores for SAT 2017 vs. 2018

sns.regplot(x="sat2017_total", y="sat2018_total", data=final);
```


![png](project1_code_link_files/project1_code_link_143_0.png)



```python
# Composite scores for ACT 2017 vs. 2018

sns.regplot(x="act2017_composite", y="act2018_composite", data=final);
```


![png](project1_code_link_files/project1_code_link_144_0.png)




### Plotting and interpretting boxplots



```python
# column list

act2017.columns
```




    Index(['state', 'act2017_participation', 'act2017_eng', 'act2017_math',
           'act2017_reading', 'act2017_science', 'act2017_composite'],
          dtype='object')




```python
# preparing for plotting boxplot

a17_list = act2017.iloc[:,2:]
a17_list.head()
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
      <th>act2017_eng</th>
      <th>act2017_math</th>
      <th>act2017_reading</th>
      <th>act2017_science</th>
      <th>act2017_composite</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>18.9</td>
      <td>18.4</td>
      <td>19.7</td>
      <td>19.4</td>
      <td>19.2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>18.7</td>
      <td>19.8</td>
      <td>20.4</td>
      <td>19.9</td>
      <td>19.8</td>
    </tr>
    <tr>
      <th>3</th>
      <td>18.6</td>
      <td>19.8</td>
      <td>20.1</td>
      <td>19.8</td>
      <td>19.7</td>
    </tr>
    <tr>
      <th>4</th>
      <td>18.9</td>
      <td>19.0</td>
      <td>19.7</td>
      <td>19.5</td>
      <td>19.4</td>
    </tr>
    <tr>
      <th>5</th>
      <td>22.5</td>
      <td>22.7</td>
      <td>23.1</td>
      <td>22.2</td>
      <td>22.8</td>
    </tr>
  </tbody>
</table>
</div>




```python
# boxplot using seaborn

plt.figure(figsize=(8,6))
sns.boxplot(data=act2017.iloc[:,2:]);
```


![png](project1_code_link_files/project1_code_link_149_0.png)



```python
# preparing for plotting boxplot

act2018.columns
```




    Index(['state', 'act2018_participation', 'act2018_composite', 'act2018_eng',
           'act2018_math', 'act2018_reading', 'act2018_science'],
          dtype='object')




```python
# rearranging columns to get comparable images

act2018['comp'] = act2018['act2018_composite']
act2018.rename(columns = {'comp':'act2018_composite2'}, inplace=True)
act2018.head()

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
      <th>state</th>
      <th>act2018_participation</th>
      <th>act2018_composite</th>
      <th>act2018_eng</th>
      <th>act2018_math</th>
      <th>act2018_reading</th>
      <th>act2018_science</th>
      <th>act2018_composite2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Alabama</td>
      <td>100.0</td>
      <td>19.1</td>
      <td>18.9</td>
      <td>18.3</td>
      <td>19.6</td>
      <td>19.0</td>
      <td>19.1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Alaska</td>
      <td>33.0</td>
      <td>20.8</td>
      <td>19.8</td>
      <td>20.6</td>
      <td>21.6</td>
      <td>20.7</td>
      <td>20.8</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Arizona</td>
      <td>66.0</td>
      <td>19.2</td>
      <td>18.2</td>
      <td>19.4</td>
      <td>19.5</td>
      <td>19.2</td>
      <td>19.2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Arkansas</td>
      <td>100.0</td>
      <td>19.4</td>
      <td>19.1</td>
      <td>18.9</td>
      <td>19.7</td>
      <td>19.4</td>
      <td>19.4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>California</td>
      <td>27.0</td>
      <td>22.7</td>
      <td>22.5</td>
      <td>22.5</td>
      <td>23.0</td>
      <td>22.1</td>
      <td>22.7</td>
    </tr>
  </tbody>
</table>
</div>




```python
# boxplot using seaborn

plt.figure(figsize=(8,6))
sns.boxplot(data=act2018.iloc[:,3:8]);
```


![png](project1_code_link_files/project1_code_link_152_0.png)


Answer: Comparing the year-on-year boxplots for both ACT and SAT, following points are noted:

1. There are no outliers.
2. The lower median values seen reinforces the left skewed nature of the distribution


```python
# boxplot using seaborn

plt.figure(figsize=(6,8))
sns.boxplot(data=sat2017.iloc[:,2:]);
```


![png](project1_code_link_files/project1_code_link_154_0.png)



```python
# boxplot using seaborn

plt.figure(figsize=(6,8))
sns.boxplot(data=sat2018.iloc[:,2:]);
```


![png](project1_code_link_files/project1_code_link_155_0.png)


## Descriptive and Inferential Statistics

### Studying plots for Normal distribution

- Plots do not display perfectly Normal distribution.


```python
jt2017.hist(figsize=(10,10), bins=20)
plt.tight_layout()
```


![png](project1_code_link_files/project1_code_link_158_0.png)



```python
jt2018.hist(figsize=(10,10), bins=20)
plt.tight_layout()
```


![png](project1_code_link_files/project1_code_link_159_0.png)


### Limitations of Data

The available data is based on average across the state not taking into account the number of students in each. For instance, the averages could be affected /positively skewed by the performance of a few very high scoring students, especially when populations of students are small. Also comparing averages across differing number of students.

The available data is for only 2 years, hence it is hard to predict trends. However, the timing is critical as many states are relooking at the ACT and SAt and policy decisions are being made on whether these should be mandatory or optional. Also, the cost of these decisions is an important factor for the administration.

On the other hand, colleges themselves are questioning the holistic nature of tests and some are considering scrapping them totally. As of January 2018, over 1,000 colleges and universities have stopped requiring SAT or ACT scores for undergraduate applicants.

Reference:
http://bit.ly/2mUeuH0

### Statistical Evaluation of Distributions




```python
# Null hypothesis: ACT and SAT average composite scores are similar for the years 2017 and 2018

final[['act2017_composite','act2018_composite']].describe()
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
      <th>act2017_composite</th>
      <th>act2018_composite</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>51.000000</td>
      <td>51.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>21.519608</td>
      <td>21.486275</td>
    </tr>
    <tr>
      <th>std</th>
      <td>2.020695</td>
      <td>2.106278</td>
    </tr>
    <tr>
      <th>min</th>
      <td>17.800000</td>
      <td>17.700000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>19.800000</td>
      <td>19.950000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>21.400000</td>
      <td>21.300000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>23.600000</td>
      <td>23.550000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>25.500000</td>
      <td>25.600000</td>
    </tr>
  </tbody>
</table>
</div>




```python
final[['sat2017_total','sat2018_total']].describe()
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
      <th>sat2017_total</th>
      <th>sat2018_total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>51.000000</td>
      <td>51.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>1126.098039</td>
      <td>1120.019608</td>
    </tr>
    <tr>
      <th>std</th>
      <td>92.494812</td>
      <td>94.155083</td>
    </tr>
    <tr>
      <th>min</th>
      <td>950.000000</td>
      <td>977.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>1055.500000</td>
      <td>1057.500000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>1107.000000</td>
      <td>1098.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>1212.000000</td>
      <td>1204.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>1295.000000</td>
      <td>1298.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
stats.ttest_ind(final['act2017_composite'],final['act2018_composite'], equal_var=False)
```




    Ttest_indResult(statistic=0.08155560824978776, pvalue=0.9351633936862667)




```python
stats.ttest_ind(final['sat2017_total'],final['sat2018_total'], equal_var=False)
```




    Ttest_indResult(statistic=0.32888697491988567, pvalue=0.7429291116643162)



- Observation:
Null hypothesis: ACT and SAT average composite scores are similar for the years 2017 and 2018

Since the pvalues are above alpha (0.05) there is insufficient data to accept or discard the Null Hyoothesis. This supports the earlier comment that additional info is needed to assess the Null hypothesis.


## Conclusions and Recommendations

Based on your exploration of the data, what are key takeaways and recommendations? Choose one state with a lower participation rate and provide a suggestion for how the College Board might increase participation amongst graduating seniors in this state. Are there additional data you desire that would better inform your investigations?

Answer: Pennsylvania


Strategies to convince state officials that SAT should be their choice:
    - Share about past record of 2 years to show how the cohorts have done well in SAT
    - Ave SAT scores have grown along with SAT participation rates
    - Provide support to administrative faculty in organising for the test and students taking up the test
    - Conduct test on weekday to ensure high participation
    - Collect feedback from colleges / institutes of higher learning on how SAT can be made more holistic for their use


```python

```
