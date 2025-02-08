# Machine learning: Predicting Gender by voice

The goal of this project is to create a model that is able to accurately predict the gender of a person based off of various pre cleaned audio metrics


## Data source
https://www.kaggle.com/datasets/murtadhanajim/vocal-gender-features
## Summary
The data set that was used consists of over 16000 data points and 44 seperate variables that describe vocal patterns. After some data exploration the 44 variables were reduced to the top 11 most important features. The data was then transformed through a pipeline, which mostly functioned as a scaler since the data was already very clean. After testing a few models a logistic regression model had by far the most success predicting genders. The logistic regression model was then tested with the tests sets, which resulted in an accuracy score of 99.3%
## Feature selection methodology 
From what I could tell most of the variables within the dataset were coded in a way that only the person who originally coded the statisitics would know exactly what they mean. So instead of trying to consult an expert I focused on prioritizing selecting the features that showed the most direct correlation to the features while also removing variables that have too much correlation with that feature that was just selected. 
<img width="156" alt="image" src="https://github.com/user-attachments/assets/4040f1a3-8eec-433f-865b-f61dee15aa60" />
<img width="409" alt="image" src="https://github.com/user-attachments/assets/730be7e9-1661-4129-afeb-1488061ed95a" /> 
<img width="406" alt="image" src="https://github.com/user-attachments/assets/9927d002-44f9-4ed0-81d0-bde01ab02a9a" />

The initial threshold for feature selection was any variable that scored above a |+-0.2|. Then the remaining variables were tested for correlation with the selected variables. If a variables had a higher than a |-+0.4| with the selected variable it was removed to reduce multicollinearity. The final result was the 11 features shown to the right most matrix above.
## Pipeline and model creation
The data pipeline that was made was pretty standard. The data did not need to be transformed, because it was already extremely clean and I did not have enough domain knowledge to confidently create my own features. The only changes that were made to the data in the pipeline is that all the features were scaled using the SimpleImputer function in Sklearn
The two models that were used were logistic and lasso regression. I chose these two because they are the most standard models to use for making predictions on classifications and I felt like they would serve as a good baseline in case I needed to make adjustments.
## Conclusion
After testing each model I was able to attain an RMSE score of ~0.08 for the logistic Regression model and a RMSE score of ~0.48 on the lasso regression model. I chose to go ahead and use the logistic regression model as my model for making predictions on my testing sets. The results of those prediction were an accuracy score of 99.3% and an R2 score of 0.97
