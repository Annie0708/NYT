# NYT
## Project Overview
* Binary classification of New York Times articles. The model determines whether an article belongs to the most frequently shared group.
* Data from NYT <a href="https://developer.nytimes.com/docs/archive-product/1/overview" target="_blank">Archive API</a> and <a href="https://developer.nytimes.com/docs/most-popular-product/1/overview" target="_blank">Most Popular API</a>.
* EDA and visualisation of article data over years.

## Code and Resources Used
* **Python version:**  3.7.13
* **Packages:** numpy, pandas, sklearn, matplotlib, seaborn, plotly, spacy, tensorflow, wordcloud, gradio

## Data collecting
Data was taken from NYT APIs. The downloads has been performed weekly for ten weeks. The collection of data consisted of 1200 samples divided into two classes: 
* top - most shared articles on Facebook
* all - other articles; not found in Most Popular API 

## Data Cleaning and Feature Engineering
From the input set of features, the following were selected:
* section - section of NYT, i.e. Business, Sports, Technology
* byline - author of the article
* title
* abstract
* print_page
* pub_date - publication date
* type_of_material - i.e. News, Letter, Review

In order for machine learning models to be used, the data had to be processed. The changes that were made are:
* transfromation of the categorical data into numerical variables
* empty value handling
* tokenization and removing stopwords from title and abstract 

In addition 23 features were added, including the number of exclamation points in the title, the occurrence of different types of NERs, and the sentiment value of the title, etc.

## Model building
Four different algorithms were used for the project. Cross-validation with 5 folds was used to validate the model. The evaluation technique is F1-score because it takes into account both precision and sensitivity of the classifier. 
Models:
* Decision Tree Classifier 
* Random Forest Classifier
* XGBoost Classifier
* Support Vector Classifier

All models performed well in data classification. Scores of 0.66-0.78 were obtained. Each model correctly classified more than 90% of the observations belonging to the 'all' class and 66-71% of the observations belonging to the 'top' class. The model chosen for deployment was Support Vector Classifier.

## Model Deployment
In the last step, the model was deployed using Gradio. The app takes in a request with a chosen section, author, title, abstract, print page and type of material and returns information on whether an article will be placed in the top shared.
