
##  Salient points for Project 2: Ames Housing Data and Kaggle Challenge

_Author: Sheng Jun, DSI 14_

---

### Introduction 

This README file is intended to provide an overview of the modeling process for Project 1. The scope of Project 2 involves building a regression model based on the Ames Housing Dataset. This model will predict the transactional sale price of a house in Ames City.

This project is also centered around utilizing Kaggle as a platform to practice data science. 

---

### Executive Summary
The data used for this project are the train and test dataset from Kaggle [DSI-US-6 Regression Challenge](https://www.kaggle.com/c/dsi-us-6-project-2-regression-challenge). The [data description](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt) provides the contextual information for the cell values for the columns in the dataset. 

---
### Problem Statement
Using the provided Ames housing train and test dataset, build a regression model (using 25-30 features) to predict the housing saleprice.


### Modeling & Evaluation Process
Both train and test dataset is first cleaned followed by EDA on uncovering numerical variables that are above 0.5 correlation to the target (saleprice) to identify preliminary set of predictors for building our first regression model. Thereafter, the distribution in saleprice for the various catergorical features are reviewed. Those with significant variances in the distribution are then selected for feature engineering to further build on our model. We also explored the use of interaction features to further refine the prediction accuracy of our regression model. 

Additonal features were then added onto the first model and the model evaluated (rmse, r2 and r2 adjusted) in an iterative process before proceeding to evaluation using cross-validation technique. The training dataset is spilt 80-20 (train and holdout), and 5 folds were used for cross-validation. In our case, the ridge model is the best performing among linear, lasso and ridge models. 

The same feature engineering procedures done on train dataset is then applied on the test dataset. The selected ridge model is then fitted onto the test dataset for the prediction of the saleprice. 

---

### Business Recommendations

From the review of the housing dataset, it is found that The following features add the most value to the home: `overall quality`, `exterior quality`, `ground living area square feet`, `kitchen quality`, `kitchen quality`, `garage area`, `total basement area square feet`, `basement quality`, `housing built after 1974`, `garage finish`, `fireplace quality`, `number of full bathrooms` and `masonary veneer area square feet`.

To increase the potential value of their own homes, home owners can consider either refurnishing existing housing features (described above) with better quality materials or fittings or by expanding the square feet area of their garage, basement, masonary veneer area, or increasing the number of full sized bathrooms.

From the saleprice distribution by neighborhood, housing in either Northridge Heights or StoneBrook might be a good investment (highest median saleprice and min. saleprice approx. 150_000 to max. saleprice 600_000).

The current model is not expected to generalize well if applied to predict saleprice of houses in another city. This is due to the features it has learnt that could be specific only to Ames City and not other cities. To enable the current model to generalize to other cities, additional data on variables that influence housing saleprice in other cities would need to be studied. This is to idenitfy common features that can be used for saleprice prediction across these cities as the model is redeveloped. In additon, exisitng features that are not relevant for saleprice prediction across cities would need to be droped from the regression model. 

---
