# Alzheimer's Disease: Data Science Approach

## Introduction
Artificial intelligence and machine learning-based approaches and applications can be used to improve healthcare solutions and reducing cost. Applying technology in healthcare can accelerate the field's progression, including increased speed of diagnosis, accuracy, and simplicity.

In this project, I will apply data science to look at Alzheimer's Disease and suggest some predictive models using for diagnosis.


## Problem Statement
- [Alhzeimer's Disease (AD)](https://www.cdc.gov/aging/aginginfo/alzheimers.htm) is a neurodegenerative disorder and is the most common cause of dementia (accounts for 60-80% of dementia cases).
- AD is one of the top 10 leading causes of death in the United States. The cost of treatment is high and [death rates](https://www.cdc.gov/nchs/data/databriefs/db116.pdf) are increasing over years. AD worsens over time and has no cure. Detecting AD at early stage can help in preventing it from developing and delay its onset.
- My goal in this project is to use machine learning techniques to build models that can be helpful in predicting early stage AD.

## Data

[OASIS-2: Longitudinal MRI Data in Nondemented and Demented Older Adults](https://www.oasis-brains.org/#data).

<b>Acknowledgements:</b> datasets using in this project are provided by [OASIS](https://www.oasis-brains.org/#data):

 OASIS: Longitudinal: Principal Investigators: D. Marcus, R, Buckner, J. Csernansky, J. Morris; P50 AG05681, P01 AG03991, P01 AG026276, R01 AG021910, P20 MH071616, U24 RR021382


## Plan
1. EDA using [Pandas](https://pandas.pydata.org/), [Seaborn](https://seaborn.pydata.org/) and [ydata_profiling](https://pypi.org/project/ydata-profiling/)
2. Data Cleaning using [Pandas](https://pandas.pydata.org/)
3. Create predictive models with [Pycaret 3](https://pycaret.org/) and [Scikit-learn](https://scikit-learn.org/stable/)


## Results

Score from the subset data of 350 records, only first visit for 14 Converted and moved to group of Nondememted. All others keep all records of different visits:

<u>XGBClassifier:</u>
F1_score: 100.00%
ACC : 100.00%
Prec: 100.00%

<u>ExtraTreesClassifier:</u>
F1_score: 100.00%
ACC : 100.00%
Prec: 100.00%

<u>RandomForestClassifier:</u>
F1_score: 100.00%
ACC : 100.00%
Prec: 100.00%

<u>LGBMClassifier:</u>
F1_score: 99.19%
ACC : 99.05%
Prec: 99.07%


<u>LinearDiscriminantAnalysis:</u>
F1_score: 99.19%
ACC : 99.05%
Prec: 99.07%


<u>RidgeClassifier:</u>
F1_score: 99.19%
ACC : 99.05%
Prec: 99.07%

## Discusion

Extra Tree, XGboost: take only one feature (CDR) as the most important and perform very well. The fact that this cognitive test is easy to administer and takes less than an hour to complete, making it a practical tool for use in clinical settings. The downside of this test is it does not take into account the individual’s social, cultural, and personal circumstances, which may affect their cognitive functioning. Therefore, even though those model hit a very high score with all F1, accuracy and precision, this maybe because CDR score have a very high corellation with the Group outcomes.


LDA, Random Forest and LighGBM: consider more features when perform the prediction (nWBV, MMSE). Regardless a little bit lower scores, I personally think those models will give us more reasonable prediction since it can balance the downside of CDR test. We know that features like age, gender can also effect the brain volume. Also, subject's education level or socialeconomic status can also have different approach to the cognitive tests.

LDA will be my model of choice to experiment further.

This subset has some repeated records (2-5 for each patients) with the same background information (Socialeconomic Status, Education, Gender), only different in age may cause some kind of colinearity.

Even though machine learning can be very helpful in the medical fields, one of the most important risks of machine learning-based algorithms is the reliance on the probabilistic distribution and the probability of error in diagnosis and prediction.


## Notebook and Videos
1. EDA & Data Cleansing:

[Notebook](https://github.com/halethithu/Azheimers_Disease_Classification/blob/main/Code/01_AD_EDA_Cleasing.ipynb)

[Video](https://youtu.be/l5ks1honFrk)

2. Model Selections using Pycaret and Sklearn:

[Notebook](https://github.com/halethithu/Azheimers_Disease_Classification/blob/main/Code/03_AD_Model_Selections_350.ipynb)

[Video](https://youtu.be/x-ylU24QtPI)

## Reference
[OASIS Brains](https://www.oasis-brains.org/#data)

[Pubmed - Machine Learning in Healthcare](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8822225/)

