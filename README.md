# Stern-Berkeley-AI-course-Capstone-Assignment-20_1
# Michael Stern Required Capstone Assignment 20.1: Initial Report and Exploratory Data Analysis (EDA)

# 1. Purpose
## This analysis aims to use machine learning models to better understand what factors
## predict the success of foreign aid projects.

# 2. Data Source
## Data were used to conduct the analysis for the following scholarly journal article:
### Honig, Dan; Lall, Ranjit; Parks, Bradley, 2021, "Replication Data for: When Does Transparency Improve Institutional Performance? Evidence from 20,000 Projects in 183 Countries", https://doi.org/10.7910/DVN/JQGLHX, Harvard Dataverse, V1, UNF:6:hYiIgxQ0ejxl0wZLmeXZrQ== [fileUNF]

## The data are in the following repository (including the Codebook file containing descriptions of the variables)
### https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi%3A10.7910%2FDVN%2FJQGLHX&version=&q=&fileAccess=&fileTag=&fileSortField=&fileSortOrder=&tagPresort=true&folderPresort=true
### Note: the data are publicly available

Dataset n = 21788 with 93 features (columns)

# 3. Feature Engineering and Data Exploration

## a. Feature Engineering
### Target is 'six_overall_rating' -- a rating for the performance of an foreign aid project (float with range from 1 to 6; 6 is highest performance)
### Deleted null values from target 
### Dropped features containing lagged variables created by the authors of the paper cited above
### Created dummy columns using the 'classification' feature (World Bank recipient country lending classification)
### Dropped a set of features containing information that overlapped significantly with other features

## b. Plots
## Correlation heatmap showed no significant correlations of any non-categorical feature with the target.
## Box plot suggests a small positive relationship between project performance and countries that have both a Freedom of Information (FOI) law and a mechanism to appeal a denied FOI request.
## Project performance ratings skewed towards higher values (mean = 4.2)

# 4. Basline Model
## Ran a linear regression using numeric features other than those which represent a non-ordinal category
## Key finding: all regression coefficients were small, suggesting none of the features predicts the target strongly. 

# 5. Considerations for Future analysis and Feature Engineering
## a. There are features which are not good candidates for the creation of binary/dummy variables because this would produce sparse matrices (e.g., wb_sector_board which has 26 distinct categories).  This suggests further analysis using classification models to see if certain features have predictive power for project performance (target).
## b. Principal Components Analysis to reduce dimensionality if appropriate
## c. Feature engineering or classification model to capture potential effects on the target associated with a project being funded by a certain donor (dataset has 12 distinct donors).  For example, do foreign aid projects funded by Japan tend to be associated with higher performance ratings? 
## d. Modeling to assess whether combinations of different features predict project performance (e.g., does a project with a longer duration from a particular donor in a country with a relatively high level of corruption control tend to have a better performance rating?)
## e. How to drop or account for null values without losing useful data (i.e., maintaining a larger n) 

Coefficients on the baseline regression model were all at a small magnitude, indicating little predictive power.  This aligns with the correlation heatmap.

