# Airbnb Twitter Sentiment Analysis

 Brands are typically defined by the services they provide. With the use of social media to communicate the successes and failures of brands, data scientists are taking advantage of this unstructured data to help companies like Airbnb continue to build and improve their brand through social campaigning, customer service and online marketing. 
 
 This project had the goal of using the Twitter API to collect data on the hashtag *airbnb* and use this data to build a classifier model that can predict whether the tweet is positive, neutral or negative. The best model was found to be a support vector machine which was evaluated using cross-validation accuracy and the f1 score.
 
 ## Collecting Data

* 2,499 tweets with the hashtag *airbnb* were collected using the Twitter API and saved as JSON

## Data Processing

* The JSON file was converted to a dataframe

* Sentiments were applied for each tweet using the Python library TextBlob

* Tweets with polarity = 0 were classified as neutral, tweets with polarity > 0 were classified as positive and tweets < 0 were classified as negative

## Exploratory Data Analysis

* The heatmap of the number of tweets indicates overall an even number of tweets across each day however, there was a spike during the afternoon of 11 and 12 August. Could this have been due to reports circulating about a possible IPO?
<img src="https://github.com/aidenaslam/Airbnb-Twitter-Sentiment-Analysis/blob/master/03_Date_Time_Heatmap.png" width="580" height="310" />

* The wordcloud indicates a variety of terms relevant to Airbnb and most of the words show a positive reaction to the service provided by Airbnb. Some of the negative words displayed relate to safety and refund policies so perhaps these are areas too look into further to improve customer service. 
<img src="https://github.com/aidenaslam/Airbnb-Twitter-Sentiment-Analysis/blob/master/05_Wordcloud_.png" width="580" height="550" />

## Data Preparation for Modelling

* Only the tweet and its label were kept from the original dataset - the remaining features were removed as they provided no relevant information to the task 

* Count vectorisation and term frequency–inverse document frequency (TFIDF) were implemented to transform text data to numerical data

* The dataset was split using the holdout method with a ratio of 70:30 between training and testing

## Modelling

* The baseline model was logistic regression

* The considered models to beat the baseline were: support vector machine (SVM), random forest and naive Bayes.

* Each model was evaluated using 10-fold stratified cross-validation

* As shown below, the SVM performed the best and thus was selected to be evaluated on the testing dataset.
<img src="https://github.com/aidenaslam/Airbnb-Twitter-Sentiment-Analysis/blob/master/04_CV_Models.png" width="450" height="400" />


## Evaluation

* The classification report for the SVM on the testing data shows an accuracy of 83%. Furthermore, the f1 score for each class is above 80% except for negative tweets. This was due to less tweets classified as negative. 
<img src="https://github.com/aidenaslam/Airbnb-Twitter-Sentiment-Analysis/blob/master/07_classification_report.PNG" width="400" height="200" />


## Limitations and Future Work

* Whilst the aim of this project was to practice using the Twitter API and processing unstructured data, each tweet was classified as neutral, negative or positive based on a strict criteria on polarity. Future work would involve using a more sophisticated method to label each tweet. 

* Furthermore, more exploratory data analysis would be useful to understand the tweets in more detail. However, by scaling up the amount of data, the results from this project can very easily be applied to help improve Airbnb's service offfering. 

* The focus of this project was not on the modelling - thus in the future, differenty types of models would be considered, including clustering and neural networks. Furthermore, a grid search or randomised search would be used to optimise models. 
