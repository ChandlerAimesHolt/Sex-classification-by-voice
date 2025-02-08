# Machine learning: Predicting Gender by voice

The goal of this project is to create a model that is able to accurately predict the gender of a person based off of various pre cleaned audio metrics


## Data source
https://www.kaggle.com/datasets/murtadhanajim/vocal-gender-features
## Summary
The data set that was used consists of over 16000 data points and 44 seperate variables that describe vocal patterns. After some data exploration the 44 variables were reduced to the top 12 most important features. The data was then transformed through a pipeline, which mostly functioned as a scaler since the data was already very clean. After testing a few models a logistic regression model had by far the most success predicting genders. The logistic regression model was then tested with the tests sets, which resulted in an accuracy score of 99.3%
## Feature selection methodology 
From what I could tell most of the variables within the dataset were coded in a way that only the person who originally coded the statisitics would know exactly what they mean. So instead of trying to consult an expert I focused on prioritizing selecting the features that showed the most direct correlation to the features while also removing variables that have too much correlation with that feature that was just selected. 
<img width="156" alt="image" src="https://github.com/user-attachments/assets/4040f1a3-8eec-433f-865b-f61dee15aa60" /> <img width="409" alt="image" src="https://github.com/user-attachments/assets/730be7e9-1661-4129-afeb-1488061ed95a" />  The initial threshold for feature selection was any variable that scored above a |+-0.2|. Then the remaining variables were tested for correlation with the selected variables. If a variables had a higher than a |-+0.4| with the selected variable it was removed to reduce multicollinearity.

