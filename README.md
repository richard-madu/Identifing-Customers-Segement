# Identifing-Customers-Segement

In this project, I will apply unsupervised learning techniques to identify segments of the population that form the core customer base for a mail-order sales company in Germany. These segments can then be used to direct marketing campaigns towards audiences that will have the highest expected rate of returns. The data that I will use has been provided by our partners at Bertelsmann Arvato Analytics, and represents a real-life data science task.

This notebook will help me complete this task by providing a framework within which I will perform my analysis steps. In each step of the project, you will see some text describing the subtask that I will perform, followed by one or more code cells for me to complete your work. The code cells provided in the base template will outline only the major tasks, and will usually not be enough to cover all of the minor tasks that comprise it.

It should be noted that while there will be precise guidelines on how I should handle certain tasks in the project, there will also be places where an exact specification is not provided. These are places where there may not be only one way to handle the data. In real-life tasks, there may be many valid ways to approach an analysis task. One of the most important things I will do is clearly document my approach so that other scientists can understand the decisions I've made.

At the end of most sections, there will be a Markdown cell labeled. In these cells, I will report my findings for the completed section, as well as document the decisions that you made in your approach to each subtask.

# ACKNOWLEDGE

## DATA CREDIT

UDACITY 
AZDIAS

# PROJECT MOTIVATION

This project will help AZDIAS focus their advert on the customer segment that will give them the highest return
This project will answer the following questions

1. What segment has the highest return?

2.

# DATA UNDERSTANDING

There are three data sets in this project

listings.csv
calendar.csv
reviews.csv

# DATA PREPARATION

Dealing with incorrect data type: The price column and the date column in the calendar were strings. I created a function to convert the price variable to float.

def float_price(x):

‘’’
input: dollar value with string dtype
output: value in float
‘’’
if type(x)==str:
x=x[1:].replace(“,” , ””)
x=float(x)
return x


This function takes the variable and removes the dollar sign and the comma sign then converts the remaining characters to float.

For the date column, I used the PD.to_datetime function to convert it to a DateTime type.

Dealing with missing variables: Missing variables were handled differently depending on the need of the analysis. For some cases I used zeros to fill the nan values other times I filled them with the mean of the column.

Dealing with categorical variables: For categorical variables, I created a dummy variable

# LIBRARIES USED

The following libraries were used to excute this project

> 1. Numpy

> 2. Pandas

> 3. Matplot

> 4. Seaborn

> 5. Scikit Learn

> 6. WordCloud

## Installations
This libraries work in latest python and they can be installed by running this code

pip install -r requirement.txt

# FILE DESCRIPTION

> Airbnb.ipynb: Notebook containing the data analysis

> calendar.csv: csv file containing bookings

> listings.csv: CSV file containing information about listings

> reviewa.csv: CSV file containing reviews

# SUMMARY OF THE RESULTS

Cluster 2 is overrepresented in the customers data compared to general population data. Some characteristics of the group of population that are relative popular with the mail-order company:

in areas where the share of 6-10 family homes is lower (PLZ8_ANTG3= 2.4)
in Prosperous or Comfortable households (WEALTH=2.75)
in life stage of Families With School Age Children or Older Families & Mature Couples (LIFE_STAGE=3.30)
Cluster 13 is underrepresented in the customers data. Some characteristics of the segment of the population that are relatively unpopular with the company:

in areas where the share of 6-10 family homes is higher (PLZ8_ANTG3=2.44)
in Less Affluent or Poorer households (WEALTH=4.4)
in life stage of Pre-Family Couples & Singles or Young Couples With Children (LIFE_STAGE=1.98)
