
##  Executive Summary for Project 3: Web APIs & Classification

_Author: Sheng Jun, DSI 14_

---

### Introduction 

This README file provides the executive summary and findings on web scraping using reddit's API and the comparison of two classification models' (Bayes Classifier and Logistic Regression) performance in identifying which subreddit a given post is from. 

---

**Jupyter Notebook Organization**

Notebooks are arranged via following system: *1st digit . 2 digit . 3 digit*

- 1st digit: Project number

- 2nd digit: 

  - **Web scraping** (data collection) and **save to csv file** : **0** , 
  - **Rest of data science process** : **1**

- 3rd digit:  

  - **First** notebook: **1** 
- **Second** notebook : **2**, and so on.
  
  For example,
  
  - notebook 3.0.1 represents the first note book on Project 3, data collection
  - notebook 3.1.1 represents the first notebook on Project 3, data cleaning, EDA, modeling and evaluation

---

### Executive Summary
**<u>Context.</u>** The Google Business strategy team is trying to develop the strategic vision for its next-gen IoT products. An important component of the Design thinking process is understanding the User's latent needs. Among the channels to solicit User needs, the team has also identified reddit as a potential information resource to harness insights on User needs. The Google Home products and the Google pixel are the two subreddits that the team will be focusing on. The team would want to extract the reddit posts and classify them according to their sources (Google Home or Google pixel) before proceeding with further analyses. Prioritization on correct classification of Google Home posts as google home devices holds the greater proportion of Google IoT devices.

**<u>Problem Statement.</u>** Manually trawling through the reddit posts to identify which post the subreddit came from is untenable, as the team has other project tasks on hand. Outsourcing this piece of work to other departments or interns is not favored due to potential of human error and sensitivity of the work. 

**<u>Proposed Solution.</u>** The team decided to utilize Natural Language Processing (NLP) and machine learning to help classify the extracted posts. The automation workflow would help alleviate workload thereby freeing up time for the team for high-value tasks. The model could also be re-purposed to classify other reddit posts, when the team moves to derive insights on User needs on competitors' products. 

The team prioritization is on correct classification of Google Home posts as google home devices holds the greater proportion of Google IoT devices. In this regard, we would want to pick the model with highest True Positive Rate (sensitivity), for as much correct classification of the google home posts as possible.

**<u>Findings.</u>**

Two types of classifiers were used: Logistic Regression and Naïve Bayes. 

To improve generalizability of the model, certain words that help with distinct classification are to be removed. These are (`First set words`): [`google`, `home`, `google home`, `nest`, `mini`, `hub` `pixel` and `buds`]. `nest`, `mini`, `hub` `pixel` and `buds` are added for good measure. Another set of words (`Second set words`) with following two characteristics:

- significant overlaps (smallest difference in word count occurrence in both classes)
- occur frequently are to be removed.

Summary of the model performance:

| Metrics         | LogReg_1 | LogReg_2 | NB_1   | NB_2   |
| --------------- | -------- | -------- | ------ | ------ |
| **accuracy**    | 0.9308   | 0.9308   | 0.9423 | 0.9423 |
| **specificity** | 0.9297   | 0.9297   | 0.9062 | 0.9062 |
| **sensitivity** | 0.9318   | 0.9318   | 0.9773 | 0.9773 |
| **roc_auc**     | 0.9910   | 0.9910   | 0.9924 | 0.9924 |

In general, we see there is insignificant effect of removal of the common overlapping words on performance of the Logistic Regression model and the Naïve Bayes model. 

The team's prioritization is on correct classification of Google Home posts as google home devices holds the greater proportion of Google IoT devices. In this regard, we would want to pick the model with highest True Positive Rate (sensitivity), for as much correct classification of the google home posts as possible. Considering the models with highest roc_auc, and highest sensitivity (lowest false positives (Type I error)), we pick the first Naïve Bayes model (NB_1) as the production model.

**<u>Recommendations and Way Forward.</u>**

For the classification of googlehome and googlepixel reddit posts, the first Naïve Bayes model emerged as the one with highest sensitivity score and roc_auc score on the validate set. Further evaluation using the whole train data set and test set indicates the model is not overfitted on the whole train dataset, since the test accuracy is higher than accuracy from the whole train set. With a sensitivity of approx.. 95% on the test set, the production model is assessed to be adequate for deployment. 

Potential enhancements to the model could be implemented post-deployment by removing the words identified to attribute to false classifications, however, care should be exercised to prevent model from shifting away from the current sweet spot and ending up with increased false positives, or losing its generalizability. It is also recommended to re-assess the list of words that have been removed should it be redeployed to classify rival's product reddit posts (e.g. Apple Iphone, Amazon Alexa).

---

