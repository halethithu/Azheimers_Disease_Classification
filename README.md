# Alzheimer's Disease: Data Science Approach

## Introduction
Artificial intelligence and machine learning-based approaches and applications can be used to improve healthcare solutions and reducing cost. Applying technology in healthcare can accelerate the field's progression, including increased speed of diagnosis, accuracy, and simplicity.

In this project, I will apply data science to look at Alzheimer's Disease and suggest some predictive models using for diagnosis.


## Problem Statement
- [Alhzeimer's Disease (AD)](https://www.cdc.gov/aging/aginginfo/alzheimers.htm) is a neurodegenerative disorder and is the most common cause of dementia (accounts for 60-80% of dementia cases).
- AD is one of the top 10 leading causes of death in the United States. The cost of treatment is high and [death rates](https://www.cdc.gov/nchs/data/databriefs/db116.pdf) are increasing over years.
- AD worsens over time and has no cure. Detecting AD at early stage can help in preventing it from developing and delay its onset.
- My goal in this project is to use machine learning techniques to build models that can be helpful in predicting early stage AD.

## Data
<b>Acknowledgements:</b> datasets using in this project are provided by [OASIS](https://www.oasis-brains.org/#data):

 OASIS: Longitudinal: Principal Investigators: D. Marcus, R, Buckner, J. Csernansky, J. Morris; P50 AG05681, P01 AG03991, P01 AG026276, R01 AG021910, P20 MH071616, U24 RR021382


## Plan
1. EDA using [Pandas](https://pandas.pydata.org/), [Seaborn](https://seaborn.pydata.org/) and [ydata_profiling](https://pypi.org/project/ydata-profiling/)
2. Data Cleaning using [Pandas](https://pandas.pydata.org/)
3. Create predictive models with [Pycaret 3](https://pycaret.org/) and [Scikit-learn](https://scikit-learn.org/stable/)


## Results

Score from the subset data of 350 records, only first visit for 14 Converted and moved to group of Nondememted. All others keep all records of different visits:

XGBClassifier:
F1_score: 100.00%
ACC : 100.00%
Prec: 100.00%

ExtraTreesClassifier:
F1_score: 100.00%
ACC : 100.00%
Prec: 100.00%

RandomForestClassifier:
F1_score: 100.00%
ACC : 100.00%
Prec: 100.00%

LGBMClassifier:
F1_score: 99.26%
ACC : 99.14%
Prec: 99.16%

Score from the subset of 150 records of first doctor visit, each for unique subjects, Converted --> Nondemented:

RidgeClassifier:
F1_score: 99.42%
ACC : 99.33%
Prec: 99.34%

LinearDiscriminantAnalysis:
F1_score: 99.42%
ACC : 99.33%
Prec: 99.34%

ExtraTreesClassifier:
F1_score: 99.42%
ACC : 99.33%
Prec: 99.34%

RandomForestClassifier:
F1_score: 100.00%
ACC : 100.00%
Prec: 100.00%

## Discusion

CDR is an important feature in most of predictive models. The fact that this cognitive test is easy to administer and takes less than an hour to complete, making it a practical tool for use in clinical settings. The downside of this test is it does not take into account the individual’s social, cultural, and personal circumstances, which may affect their cognitive functioning.

The bigger dataset seems to perform better based on F1 score, accuracy and precision.

Random Forest Classifier may be a good model to go with in both setting. Extra Tree and XGBoost can be alternatives. All performed well when tested again unseen data.

Even though machine learning can be very helpful in the medical fields, one of the most important risks of machine learning-based algorithms is the reliance on the probabilistic distribution and the probability of error in diagnosis and prediction.

## Notebook
1. [EDA & Data Cleansing](https://github.com/halethithu/Capstone/blob/main/Code/01_Alzheimers_Disease_EDA_and_%20DataCleansing.ipynb)
2. [Model Selections using Pycaret and Sklearn for Dataset with 350 records](https://github.com/halethithu/Capstone/blob/main/Code/03_AD_Model_Selections_350.ipynb)
3. [Model Selections using Pycaret and Sklearn for Dataset with 150 records](https://github.com/halethithu/Capstone/blob/main/Code/04_AD_Model_Selections_150.ipynb)

## Reference
[OASIS Brains](https://www.oasis-brains.org/#data)

[Pubmed - Machine Learning in Healthcare](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8822225/)

