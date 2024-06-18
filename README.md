# Identifing-Customers-Segement

In this project, I will apply unsupervised learning techniques to identify segments of the population that form the core customer base for a mail-order sales company in Germany. These segments can then be used to direct marketing campaigns towards audiences that will have the highest expected rate of returns. The data that I will use has been provided by our partners at Bertelsmann Arvato Analytics, and represents a real-life data science task.

This notebook will help me complete this task by providing a framework within which I will perform my analysis steps. In each step of the project, you will see some text describing the subtask that I will perform, followed by one or more code cells for me to complete your work. The code cells provided in the base template will outline only the major tasks, and will usually not be enough to cover all of the minor tasks that comprise it.

It should be noted that while there will be precise guidelines on how I should handle certain tasks in the project, there will also be places where an exact specification is not provided. These are places where there may not be only one way to handle the data. In real-life tasks, there may be many valid ways to approach an analysis task. One of the most important things I will do is clearly document my approach so that other scientists can understand the decisions I've made.

At the end of most sections, there will be a Markdown cell labeled. In these cells, I will report my findings for the completed section, as well as document the decisions that you made in your approach to each subtask.

# ACKNOWLEDGE

## DATA CREDIT

UDACITY 

AZ DIRECT GmbH

# PROJECT MOTIVATION

This project will help AZ Direct focus their advert on the customer segment that will give them the highest return
This project will answer the following questions

1. What segment has the highest return?

2.What segment is over-represented?

3. What segment is under-represented?

# DATA UNDERSTANDING

The data for this project consist of two files:

- Udacity_AZDIAS_Subset.csv: demographics data for the general population of
      Germany; 891211 persons (rows) x 85 features (columns)

- Udacity_CUSTOMERS_Subset.csv: demographics data for customers of a mail-order
      company; 191652 persons (rows) x 85 features (columns)


# DATA PREPARATION
Missing Values:
The fourth column of the feature attributes summary (loaded in above as `feat_info`) documents the codes from the data dictionary that indicate missing or unknown data. While the file encodes this as a list (e.g. `[-1,0]`), this will get read in as a string object. You'll need to do a little bit of parsing to make use of it to identify and clean the data. Convert data that matches a 'missing' or 'unknown' value code into a numpy NaN value. You might want to see how much data takes on a 'missing' or 'unknown' code, and how much data is naturally missing, as a point of interest

I dropped all the columns that the missing values constitute 20%

Re-Encode Features:

Checking for missing data isn't the only way in which I can prepare a dataset for analysis. Since the unsupervised learning techniques to be used will only work on data that is encoded numerically,I need to make a few encoding changes or additional assumptions to be able to make progress. In addition, while almost all of the values in the dataset are encoded using numbers, not all of them represent numeric values. Check the third column of the feature summary (feat_info) for a summary of types of measurement.

> For numeric and interval data, these features can be kept without changes.

> Most of the variables in the dataset are ordinal in nature. While ordinal values may technically be non-linear in spacing, making the simplifying assumption that the   ordinal variables can be treated as being interval in nature (that is, kept without any changes).

> Special handling may be necessary for the remaining two variable types: categorical, and 'mixed'.

Applying Feature Scaling:

Before I apply dimensionality reduction techniques to the data, I will be performing feature scaling so that the principal component vectors are not influenced by the natural differences in scale for features. Starting from this part of the project, I'll keep an eye on the API reference page for sklearn to help me navigate to all of the classes and functions that I'll need

Performance Dimensionality Reduction

On my scaled data, I'm now ready to apply dimensionality reduction techniques. I used PCA to perform this task
# LIBRARIES USED

The following libraries were used to excute this project

> 1. Numpy

> 2. Pandas

> 3. Matplot

> 4. Seaborn

> 5. Scikit Learn

## Installations
This libraries work in latest python and they can be installed by running this code

pip install -r requirement.txt

# ANALYSIS

Considering the proportion of persons in each cluster for the general population, and the proportions for the customers. If we think the company's customer base to be universal, then the cluster assignment proportions should be fairly similar between the two. If there are only particular segments of the population that are interested in the company's products, then we should see a mismatch from one to the other. If there is a higher proportion of persons in a cluster for the customer data compared to the general population (e.g. 5% of persons are assigned to a cluster for the general population, but 15% of the customer data is closest to that cluster's centroid) then that suggests the people in that cluster to be a target audience for the company. On the other hand, the proportion of the data in a cluster being larger in the general population than the customer data (e.g. only 2% of customers closest to a population centroid that captures 6% of the data) suggests that group of persons to be outside of the target demographics.


# SUMMARY OF THE RESULTS

Cluster 2 is overrepresented in the customers data compared to general population data. Some characteristics of the group of population that are relative popular with the mail-order company:

in areas where the share of 6-10 family homes is lower (PLZ8_ANTG3= 2.4)
in Prosperous or Comfortable households (WEALTH=2.75)
in life stage of Families With School Age Children or Older Families & Mature Couples (LIFE_STAGE=3.30)
Cluster 13 is underrepresented in the customers data. Some characteristics of the segment of the population that are relatively unpopular with the company:

in areas where the share of 6-10 family homes is higher (PLZ8_ANTG3=2.44)
in Less Affluent or Poorer households (WEALTH=4.4)
in life stage of Pre-Family Couples & Singles or Young Couples With Children (LIFE_STAGE=1.98)

From the analysis we can see that cluster 13 is the over-represented cluster therefore sould be the target demograph of the mailing company 
