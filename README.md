# Machine learning: Predicting Gender by voice

The goal of this project is to create a model that is able to accurately predict the gender of a person based off of various pre cleaned audio metrics


## Data source
https://www.kaggle.com/datasets/murtadhanajim/vocal-gender-features
## Summary
The data set that was used consists of over 16000 data points and 44 seperate variables that describe vocal patterns. After some data exploration the 44 variables were reduced to the top 12 most important features. The data was then transformed through a pipeline, which mostly functioned as a scaler since the data was already very clean. After testing a few models a logistic regression model had by far the most success predicting genders. The logistic regression model was then tested with the tests sets, which resulted in an accuracy score of 99.3%
