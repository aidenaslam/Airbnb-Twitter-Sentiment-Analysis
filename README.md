# Airbnb Twitter Sentiment Analysis

 Brands are typically defined by the services they provide. With the use of social media to communicate the successes and failures of brands, data scientists are taking advantage of this unstructured data to help companies like Airbnb continue to build and improve their brand through social campaigning, customer service and online marketing. 
 
 This project had the goal of using the Twitter API to collect data on the hashtag airbnb and use this data to build a classifier model that can predict whether the tweet is positive, neutral or negative. The best model was found to be a support vector machine which was evaluated using cross-validation accuracy and the f1 score.
 
 ## Collecting Data

* 2,499 tweets with the hashtag *airbnb* were collected using the Twitter API and saved as JSON

## Data Processing

* Sentiments were aplied for each tweet using the Python library TextBlob

* Tweets with polarity = 0 were classified as neutral, tweets with polarity > 0 were classified as positive and tweets < 0 were classified as negative

## Exploratory Data Analysis

* The heatmap of the number of tweets indicates overall an even number of tweets across each day however, there was a spike during 11 and 12 August



## Data Preparation for Modelling

* 

## Modelling

* 


## Evaluation

* 


## Limitations and Future Work

* 
