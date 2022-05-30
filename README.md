# NYT
## Project Overview
* Binary classification of New York Times articles. The model determines whether an article belongs to the most frequently displayed group based on author, newspaper section, title and abstract.
* Data from NYT <a href="https://developer.nytimes.com/docs/archive-product/1/overview" target="_blank">Archive API</a> and <a href="https://developer.nytimes.com/docs/most-popular-product/1/overview" target="_blank">Most Popular API</a>.
* EDA and visualisation of article data over years.

## Code and Resources Used
* **Python version:**  3.7.13
* **Packages:** numpy, pandas, sklearn, matplotlib, seaborn, plotly, spacy, tensorflow, requests, json, wordcloud, gradio

## Data collecting
Data was taken from NYT APIs. The downloads has been performed weekly for **XXXXXXX** months. The collection of data consisted of **XXX** samples with **CCC** attributes:
*

## Data Cleaning and Feature Engineering
From the input set of features, the following were selected:
* section - section of NYT, i.e. Business, Sports, Technology
* byline - author of the article
* title
* abstract

In addition, further attributes were introduced:
*
*

In order for machine learning models to be used, the data had to be processed. The changes that were made are:
* aa
* transfromation of the categorical data into dummy variables

## Exploratory Data Analysis

## Model building
*the data was split into train and test sets with test size of 20%.
Three different algorithms were used for the project. The evaluation technique is Mean Absolute Error as it is pretty easy to interpret with regressors.
Models:
Lasso Regression - Baseline for the model.
Random Forest - the algorithm works fairly good with high-dimensional data. As the data was mostly categorical it turns out to be a good fit.
Support Vector Regression - the dataset size is pretty low, so we are free to use this algorithm.

## Model Evaluation

## Model Deployment
In the last step, the model was deployed using Gradio. The app takes in a request with a chosen section, author, title and abstract and returns information on whether an article will be placed in the top viewed.
