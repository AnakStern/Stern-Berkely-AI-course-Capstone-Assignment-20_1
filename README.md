# Stern-Berkely-AI-course-Capstone-Assignment-20_1
# Michael Stern Required Capstone Assignment 20.1: Initial Report and Exploratory Data Analysis (EDA)

# 1. Purpose
## This analysis aims to use machine learning models to better understand what factors
## predict the success of foreign aid projects.

#2. Data Source
## Data were used to conduct the analysis for the following scholarly journal article:
### Honig, Dan; Lall, Ranjit; Parks, Bradley, 2021, "Replication Data for: When Does Transparency Improve Institutional Performance? Evidence from 20,000 Projects in 183 Countries", https://doi.org/10.7910/DVN/JQGLHX, Harvard Dataverse, V1, UNF:6:hYiIgxQ0ejxl0wZLmeXZrQ== [fileUNF]

## The data are in the following repository (including the Codebook file containing descriptions of the variables)
### https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi%3A10.7910%2FDVN%2FJQGLHX&version=&q=&fileAccess=&fileTag=&fileSortField=&fileSortOrder=&tagPresort=true&folderPresort=true
### Note: the data are publicly available

# 3. Feature Engineering

## Target is 'six_overall_rating' -- a rating for the performance of an foreign aid project (float with range from 1 to 6)

## Deleted null values from 
Target is six_overall_rating.  Delete all null values for six_overall_rating
Explanatory variables for projects: project size, project duration, project sector 
Explanatory variables for recipient countries: existence of an Access to Information process, presence of appeals mechanism; CSO participatory environment; corruption metric; 
Explanatory variables for donors: the donor; whether the donor has an independent evaluation unit
Recode Donor into dummies
Combine project size into a single variable.  Then delete null values for this var
Recode classification (recipient country lending classification) 
Correlation heat maps
Future analysis and feature engineering
There are features which are not good candidates for the creation of binary/dummy variables because this would produce sparse matrices (e.g., wb_sector_board which has 26 distinct categories).  This suggests further analysis using classification models to see if certain features have predictive power for project performance (target).
Principal Components Analysis to reduce dimensionality if appropriate
Feature engineering or classification model to capture potential effects on the target associated with a project being funded by a certain donor (dataset has 12 distinct donors).
Modeling to assess whether combinations of different features predict project performance (e.g., does a project with a longer duration from a particular donor in a country with a relatively high level of corruption control tend to have a better performance rating?)
How to drop null values without losing useful data (i.e., maintaining a larger n) 
Coefficients on the baseline regression model were all at a small magnitude, indicating little predictive power.  This aligns with the correlation heatmap.

