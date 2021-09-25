# Let's Cluster some Credit Cards with BIRCH!
Here, I use birch clustering algorithm.

# Explain: 
In this notebook I'll try to cluster some credit cards. we go through preprocessing, choose a model and train it on our data, and then evaluate and visualize our outcomes.

# Dataset 
I used Credit Cards dataset for this project. You can download the dataset [here](https://www.kaggle.com/arjunbhasin2013/ccdata)
### A bout dataset features
* CUSTID : Identification of Credit Card holder (Categorical)
* BALANCE : Balance amount left in their account to make purchases
* BALANCEFREQUENCY : How frequently the Balance is updated, score between 0 and 1 (1 = frequently updated, 0 = not frequently updated)
* PURCHASES : Amount of purchases made from account
* ONEOFFPURCHASES : Maximum purchase amount done in one-go
* INSTALLMENTSPURCHASES : Amount of purchase done in installment
* CASHADVANCE : Cash in advance given by the user
* PURCHASESFREQUENCY : How frequently the Purchases are being made, score between 0 and 1 (1 = frequently purchased, 0 = not frequently purchased)
* ONEOFFPURCHASESFREQUENCY : How frequently Purchases are happening in one-go (1 = frequently purchased, 0 = not frequently purchased)
* PURCHASESINSTALLMENTSFREQUENCY : How frequently purchases in installments are being done (1 = frequently done, 0 = not frequently done)
* CASHADVANCEFREQUENCY : How frequently the cash in advance being paid
* CASHADVANCETRX : Number of Transactions made with "Cash in Advanced"
* PURCHASESTRX : Numbe of purchase transactions made
* CREDITLIMIT : Limit of Credit Card for user
* PAYMENTS : Amount of Payment done by user
* MINIMUM_PAYMENTS : Minimum amount of payments made by user
* PRCFULLPAYMENT : Percent of full payment paid by user
* TENURE : Tenure of credit card service for user

## Essential libraries that I used :
* numpy
* pandas
* matplotlib
* seaborn
* Scikit-learn

## Preprocessing
1) remove the outliers
2) impute missing data
3) scale the data
4) Reduce dimentions using PCA


# check for outliers
Using IQR, we can follow the below approach to find outliers:
* Calculate the first and third quartile (Q1 and Q3).
* Further, evaluate the interquartile range, IQR = Q3-Q1.
* Estimate the lower bound, the lower bound = Q1*1.5
* Estimate the upper bound, upper bound = Q3*1.5
* The data points that lie outside of the lower and the upper bound are outliers.


# Removing the outliers 
first, let's get rid of the noise. we're going to first set all outliers as 'NaN', so it will be taken care of in the next stage, where we impute the missing values.
