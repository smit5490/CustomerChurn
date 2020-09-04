# Understanding Customer Churn
*Note: This repository was completely updated using survival analysis techniques and used as the first project in 
Udacity's Data Scientist Nanodegree program.*
 
### Project Setup:
After creating a clean Python/Conda virtual environment all of the project's dependencies are in the requirements.txt 
file which can be installed using:

`pip install -r requirements.txt`

The Python version used was 3.8.1. All of the survival modeling was done using the [lifelines](https://lifelines.readthedocs.io/en/latest/) package.

### Motivation: 
There are two main challenges when running a subscription-based business, getting customers and retaining them. This 
project focuses on the latter by analyzing customer enrollment characteristics and their impact on churn rate for a 
subscription-based personal finance business.

### Summary of Analysis
Customers in the silver tier had the lowest churn and longest tenure of all three tiers.
Customers that were referred to the company's software versus through partnerships or were organically generated also 
experienced the longest tenure. Customers based in Canada and the Netherlands had the longest tenure amongst all 
countries.
 
Two survival models were explored to forecast enrollments and understand the impact of a customer's enrollment characteristics on 
their tenure:

**Modified Cox Proportional Hazard Model:** A modified version of the Cox Proportional Hazards model where the baseline 
hazard includes cubic spline terms. This model allows for extrapolation, but its predictions vary widely depending on 
the number of splines used (while still reporting very similar concordance indices).

**Weibull Accelerated Failure Time Model:** A parameteric survival analysis model based on the Weibull distribution.

In an effort to balance accuracy and interpretability, the Weibull model was used for forecasting.

### Data:

In the *data* folder, all data is in one flat file called *9mo_pull.csv*, which contains data for all members who 
subscribed to a personal finance SaaS exactly 9 months ago. It does not contain data for members who subscribed since 
then. In other words, each member in the dataset has the same start date. As a result, this data is considered to be 
"right censored". 

**Data Dictionary:**

*member_id* - Unique ID of the user.  
*tier* - Price tier (Silver, Gold, or Platinum).  
*country* - Member country.  
*source* - Original acquisition channel.  
*tenure* - Number of cycles billed. Min is 1. Max is 9.  
*active* - Is the subscription still active?  

### Code:
There is a single notebook in the *code* folder that contains the entire end-to-end analysis and modeling of the data set. 
There are some old notebooks in the *old notebooks* folder that explore other packages/approaches, but are not directly 
relevant the Udacity project.
