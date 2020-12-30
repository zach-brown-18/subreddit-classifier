# ![](https://fitsmallbusiness.com/wp-content/uploads/2017/12/Reddit_Logo-300x300.png)

# How much data do you need?
---

Data acquisition and maintenence can be costly. How much money has your BI team spent acquiring and managing its data over the past year?  

In the age of the data culture, you need a way to evaluate the cost/benefit of gathering new data for your machine learning projects. An accurate analysis of this problem will save your department costs, which frees up money for new projects, reach goals, or hiring new employees.  

Fortunately, there is an emerging role that does this in a nutshell: The data scientist. Equip your BI team with a data scientist who can determine exactly how much data is necessary for a project.  

This demonstration walks through the process a data scientist may take to determine exactly how much data is necessary for a project. Specifically, we will answer the question: How much does the accuracy of a classification model improve as more training data is added?  

By the end of this demonstration you will understand how pragmatic the hiring of a data scientist is. Data piles up on our doorstep and, as a company, you will drown unless you have the right eyes and mind to know what to do with it. Hire a data scientist for your company now and thrive in this data culture of the 21st century.

---

# Demonstration
**Modeling Goal**  
Classify reddit posts correctly as originating from either the r/oceans subreddit or the r/diving subreddit.  
*Metric:* Accuracy  

**Overall Goal**  
Determine by how much does the accuracy of a classification model improve as more training data is added?  

**Data**  
Reddit's Pushshift API  
Gathered data from subreddits: Oceans | Diving  

*Three sets of data with the following posts:*  
Small: 3000  
Medium: 5300  
Large: 7491  

Medium dataset has 77% more posts than the small dataset.  
Large dataset has 150% more posts than the small dataset.  

**Data Cleaning and Feature Engineering**  
1. Remove words that have no contribution to the model’s predictive power.
    * Including placeholders
2. Engineer post length and title length features
3. Engineer sentiment snalysis features

**Modeling**  
*Models:* Logistic Regression, Multinomial Naive Bayes, Gaussian Naive Bayes  
Gridsearch for best hyperparameters
 * CountVectorizer
 * TfidfTransformer
 * max_features
 * ngram_range
 * stop_words
 * alpha

# Findings
As the amount of training data increases, the classification model's accuracy sees diminishing returns. Both the logistic regression and Naive Bayes models demonstrated a similar, if not identical, increase in accuracy as the dataset size increased. As such I only evaluate the logistic regression model below.  

Increase in model accuracy  
--> For each 1% increase in datapool size, the model's accuracy score increases by:  

small -> medium = 0.00039  
small -> large = 0.00026  
medium -> large = 0.00023  

