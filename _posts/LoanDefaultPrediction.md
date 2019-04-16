---
title: "Loan Default Prediction"
date: 2019-04-15
tags: [machine learning, data science, data modeling, numpy, pandas, matplotlib, scikit-learn]
header:
  image: "/images/loan.jpg"
excerpt: "machine learning, data science, data modeling, numpy, pandas, matplotlib, scikit-learn"
---

# Loan Default Prediction

Loan default prediction project, I will be exploring publicly available Lending Club data from Kaggle. Lending Club is a platform bringing borrowers and investors together, transforming the way people access credit. As an investor, you would want to invest in people who showed a profile of having a high probability of paying back. I will try to create a model to predict this.

Here are what the columns represent:

**credit.policy**: 1 if the customer meets the credit underwriting criteria of LendingClub.com, and 0 otherwise.
**purpose**: The purpose of the loan
**int.rate**: The interest rate of the loan
**installment**: The monthly installments owed by the borrower if the loan is funded.
**log.annual.inc**: The natural log of the self-reported annual income of the borrower.
**dti**: The debt-to-income ratio of the borrower (amount of debt divided by annual income).
**fico**: The FICO credit score of the borrower.
**days.with.cr.line**: The number of days the borrower has had a credit line.
**revol.bal**: The borrower's revolving balance (amount unpaid at the end of the credit card billing cycle).
**revol.util**: The borrower's revolving line utilization rate (the amount of the credit line used relative to total credit available).
**inq.last.6mths**: The borrower's number of inquiries by creditors in the last 6 months.
**delinq.2yrs**: The number of times the borrower had been 30+ days past due on a payment in the past 2 years.
**pub.rec**: The borrower's number of derogatory public records (bankruptcy filings, tax liens, or judgments).

## Import Libraries
Import the usual libraries for pandas, plotting, and sklearn.

Python code block:
```python
import numpy as np
import pandas as pd
import seaborn as sns
sns.set_style('whitegrid')
import matplotlib.pyplot as plt
%matplotlib inline
from sklearn.ensemble import RandomForestClassifier
from sklearn.svm import SVC
from sklearn import svm
from sklearn.linear_model import LinearRegression
from sklearn.linear_model import LogisticRegression
from sklearn.tree import DecisionTreeClassifier
from sklearn.neighbors import KNeighborsClassifier
from sklearn.metrics import confusion_matrix, classification_report
from sklearn.preprocessing import StandardScaler, LabelEncoder
from sklearn.model_selection import train_test_split
from sklearn.model_selection import cross_val_score
from sklearn.model_selection import GridSearchCV


import warnings
warnings.filterwarnings("ignore")
```

## Get the Data
Python code block:
```python
# load dataset
loan = pd.read_csv("loandata.csv")
```

Check out the info(), describe() and head() methods on loan
Python code block:
```python
loan.info()
loan.describe()
loan.head()
```

Check if there is any missing data
Python code block:
```python
loan.isnull().sum()
```

Check the size of the dataset
Python code block:
```python
loan.shape
```