---
title: "Engaging Senior Volunteers"
date: 2019-12-05
tags: [data analysis, seniors, volunteers, unstructured data, data visualisation]
header:
  image: "/images/project5.jpg"
excerpt: "Data Analysis, Seniors, Volunteers, Unstructured data, Data Visualisation"
mathjax: "true"
---


## Senior volunteers in Singapore - Looking back, looking ahead


## Background

Non-profit organisations are run very lean in terms of staffing and often there is not much time to reflect on work when there is loads of 'good' work to done. This project is an effort to provide a perspective of the senior volunteers the organisation engaged with and the nature of programmes done. Senior volunteers are a vital force of the agency being engaged in various ways in adding value to lives of others in the community. The multi-level analysis has answered some questions for the organisation and helped them in strategizing for the future.


## Problem statement
To look at the volunteer database and activities conducted over 4 years (2015-2018) and study patterns:

• Profile of volunteers
• What activities are these volunteers most involved in? (Comparison of numbers)
• Clustering of volunteers based on activities they are involved in / hours they volunteer
• Engagement of volunteers and suggestions for continuing their involvement


## Process

The datasets for volunteer profiles needed extensive cleaning and replacing of missing values, since much of the individual data was not available. The datasets for the activities was available in individual sheets following the years with a combined sheet for years 2015 and 2016.

A simple predictive model was designed to predict if new members were likely to continue as active members. Although the model had good scores with both validation and test data, it was found to be lacking as it primarily reliedon features of citizensip and gender, which was found to be restrictive. Also, since the volunteers were seniors, there could be a number of unrelated reasons for volunteers to no longer be active. These could range from ill-health, other commitments on their time, forgetfulness, taken up employment, travelling, caring for family members, etc.

K means clustering was used to do the clustering of volunteers


## Outcomes

### Profile of volunteer:

Membership has increased in last 3 years by over 250% and the interests of the volunteers are varied in nature.
Currently, th volunteers are largely Chinese-speaking volunteers (57%), with greater number of women (62%).
Among the 5897 volunteers who have registered since 2017, 39% have indicated that they have post secondary qualifications.
77% of volunteers continue to remain active in 2019. The average age of volunteers in 68 - 74 years

### Cluster of volunteers:

Guide_leads : regularly volunteers over 150 hours in a year, involved in senior guiding, cyberguide and administrative work (to smaller extent).
Cyber_champs: regularly volunteers over 600 hours in a year, involved in cyberguide and other administrative work.
All_rounders : regularly volunteers over 70 hours and is involved in multiple activities - senior guiding, enriching lives of seniors programe, mentally disadvantaged outreach programme and mentoring.
Volunteer_at_leisure: occasional volunteer, volunteers about 5-10 hours in a year in one or two events

'Cyber_champs' and 'Guide_leads' volunteers have been volunteering for over 10 years. 'All_rounders' and 'Volunteer_at_leisure' have bene volunteering for less than 10 years

## Recommendations

Range of activities need to increase to engage volunteers and prevent dropout - traditionally this has been about 25%
Volunteers coming with professional skills can be engaged in specialised areas of administrative and consulting work
Support other smaller Social Service Agencies who have needs for volunteers
Innovative programmes based on feedback from existing volunteers
Localised volunteering opportunities within neighbourhood may receive higher response

## Limitations

No health information available – can use to assess suitability of activities for those with impairments
Feedback from existing volunteers not included – will be useful to study how programmes can be revitalised, identify any trainings needed
Volunteer activity of individuals may not be the complete picture - members engaged in other organisations / doing volunteering on their own initiative

## To view the code developed in the project
- kindly click <a href="https://github.com/BhavNike/BhavNike.github.io/blob/master/code/project5_volunteer_activity.ipynb"> here </a> for volunteer activity details
- kindly click <a href="https://github.com/BhavNike/BhavNike.github.io/blob/master/code/project5_volunteer_profile.ipynb"> here </a> for volunteer profile
