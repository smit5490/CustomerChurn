# Predicting Subscription Churn

**Task**: Analyze churn rate for a subscription-based personal finance business.

Churn rate is defined as the proportion of members who cancel their subscription. A 20% churn rate can also be referred to as an 80% retention rate.

**Goal**: 

* Calculate average churn rate over the last 9 months for each price tier.
* Predict the number of currently active subscriptions that will still be active next month.
* Predict the number of currently active subscriptions that will still be active in 3 months.
* Build a separate model that predicts tenure based on price tier, source, and country.
* Provide actionable insights to the business.

**Data**:

The data is in one table called 9mo_pull.csv. It contains data for all members who subscribed to a personal finance SaaS 9 months ago. It does not contain data for members who subscribed since then. In other words, each member in the dataset has the same start date.

**Data Dictionary**:

member_id - Unique ID of the user.  
tier - Price tier (Silver, Gold, or Platinum).  
country - Member country.  
source - Original acquisition channel.  
tenure - Number of cycles billed. Min is 1. Max is 9.  
active - Is the subscription still active?  

**Scripts**:

The iPython notebook in this repository performs an exploratory analysis, an application of a decision tree and random forest model to the data, and provides some actionable insights for the business.
