
##  Salient points for Project 1: SAT & ACT Analysis

_Author: Sheng Jun, DSI 14_

---

### Introduction 

This README file is intended to provide an overview of the EDA steps for Project 1. The scope of Project 1 involves data cleaning, statistical analysis and inference, and data visualisations using SAT and ACT (2017 and 2018) data.

This project ties in with the modules covered over weeks 1 and 2. These range from porting of files, application of basic statistics, EDA to visualizations. 
The following sections provide a walk-through on the EDA steps taken for this project. 

---

### Executive Summary
The data used for this project are the aggregate SAT and ACT scores and participation rates from each state in the United States across the years 2017 and 2018. EDA on the provided datasets and insights from literature review are combined to identify potential factors influencing participation rates and scores in a particular State of interest. This is followed by recommendations on how the College Board may work on to improve participation rates for that State.

#### Contents
- [Datasets Provided](#data_description)
- [Problem Statement](#problem_statement)
- [Data Dictionary](#data_dict)
- [Findings](#findings)
- [Recommendations](#recommendations)

---

<a id='data_description'></a>
### Datasets Provided

For this project, the provided datasets are (in the form of .csv files): 
- 2017 SAT Scores
- 2017 ACT Scores
- 2018 SAT Scores
- 2018 ACT Scores
The source for the SAT2017 data is [here](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/), and the source for the ACT2017 data is [here](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows).

---

<a id='problem_statement'></a>
### Problem Statement
We are provided witht the following prompt:
> The new format for the SAT was released in March 2016. As an employee of the College Board - the organization that administers the SAT - you are a part of a team that tracks statewide participation and recommends where money is best spent to improve SAT participation rates. Your presentation and report should be geared toward **non-technical** executives with the College Board and you will use the provided data and outside research to make recommendations about how the College Board might work to increase the participation rate in a **state of your choice**.

With this, the problem statement is crafted: 
**"From the data provided, supported with insights from outside research,\
i) identify the factors influencing participation rates and scores in a state of interest, \
ii) make recommendations about how the College Board might work to increase the participation rate."**

---

<a id='data_dict'></a>
### Data Dictionary 
The four datasets were reviewed to uncover 
-errors in cell values,
-missing values,
-inappropriate datatypes
-irrelvant rows or columns 

From these observations, the datasets are then cleaned and combined into a common dataset (final.csv).  
The data dicitionary provides supporting description on the values in the dataframe.
In general, the last two numbers denotes the year (e.g. xxxx_18 means the data value for year 2018).
Each row in the dataset represents a participation rate and scores for a State.

|Feature|Type|Dataset|Description|
|----|----|----|----|
|**state**|*object*|ACT/SAT|Name of one of 51 states in the U.S.|
|**sat_participate_17**|*float*|SAT|Participation rate(%) for SAT 2017 (units percent to one decimal place, 1.0 means 1.0%)|
|**act_participate_17**|*float*|ACT|Participation rate(%) for ACT 2017 (units percent to one decimal place, 1.0 means 1.0%)|
||||For 'participate', the last 2 numbers denotes the year (e.g.17 means 2017 and so on)|
|**sat_evrw_17**|*float*|SAT|Evidence-Based Reading and Writing (EBRW) SAT 2017 score|
|**sat_math_17**|*float*|SAT|Math SAT 2017 score |
|**sat_total_17**|*float*|SAT|Sum of EVRW and Math scores for SAT 2017|
|**act_eng_17**|*float*|ACT|English ACT 2017 score|
|**act_math_17**|*float*|ACT|Math ACT 2017 score|
|**act_rding_17**|*float*|ACT|Reading ACT 2017 score|
|**act_science_17**|*float*|ACT|Science ACT 2017 score|
|**act_composite_17**|*float*|ACT|Average of English, Math, Reading and Science scores for ACT 2017|
||||For all scores, last 2 numbers denotes respective score for the year (e.g.17 means 2017 and so on)|


---

<a id='findings'></a>
### Findings

From the exploratory data analysis, three states stands out: **Colorado, Illinois and Rhode Island**. 
- Colorado's participation rates for SAT surged from 11% to 100%, while ACT participation dropped from 100% to 30% between 2017 and 2018. Correspondingly, there is a decrease in SAT total score, and increase in ACT composite score.
- Similar trends are observed for Illinois and Rhode Island.

- From literature research, Colorado, Illinois and Illinois partnered with the the College Board partnered to administer SAT as a mandatory test mandatory test. As part of the implementation efforts, the College Board introduced a program in 2010 (SAT school day) meant to increase access to the SAT by waivering test fees (USD64.50 with essay vs. no cost) for low-income family students. In 2016, the SAT was redesigned to to align the SAT with Common Core Standards. In general terms, the standards emphasize critical thinking and real-world problem-solving skills as opposed to rote memorization, which should better prepare students for College and their careers.


---

<a id='recommendations'></a>
### Recommendations

The SAT participation rates are generally consistent between 2017 and 2018. Similar observation applies for ACT as well. SAT has a small cluster of states with high participation rates, and another cluster with 50-70% participation rates. ACT has a large cluster of states with high participation. For participation rates and scores, they are negatively correlated. Low particiation rates means the students participating in the tests tend to be better performing ones.

Generally, the states with significant increase in SAT participations between 2017 and 2018 have prior participation rates around the 9-11% range. The national average score is 1020 in 2016 then. This could soften the ground further for the three states to adopt mandatory SAT test in 2017.

The College Board could consider focusing on states with i) similar participation rates for the coming year (i.e. 2018 participation rates for 2019 efforts), and total scores close to the national average. Moving forwards, one potential candidate is **Montana**, with its 2018 participation rates 10% and mean SAT total score 1198. The national average SAT score for 2018 is 1060. 

Understandably, transition from ACT to SAT is not an easy decision, with high stakes involved for students and families. Parents of the students would not concerned regarding whether their children can adjust to the new SAT test format and requirements. As part of the outreach effort, the College Board could consider working with the State's educational board to create materials to ease student's transition from ACT to SAT. 
Also, the College Board should review and implement initiatives to lower the entry barrier for students from low-income households. Some potential solutions include scholarships and SAT program day.

**On the presentation materials, there would be a range of potential State candidates which the College Board may chose to focus on among the team members. After deliberation, the team chose to converge on South Dakota.**

---
