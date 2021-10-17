# Neural_Network_Charity_Analysis
## Overview
From Alphabet Soup’s business team, we received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization. With our knowledge of machine learning and neural networks, we will use the features in the provided dataset to help create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup.

## Results
The target model performance was set at 75% accuracy and our model showed an accuracy of 71.84%. The original model’s accuracy was optimized through data preprocessing, trying more sophisticated models as well as allowing the learn time to run for more iterations. 

## Data Preprocessing
The target variable is labeled as “IS_SUCCESSFUL” in the data frame. This is a binary data point that represents success with a 1 and failure with a 0. As the target variable, this is the value which the model will try and predict. All other variables are considered features of the data and describe each case which is helping the model learn.

Variables which add no value to the data (such as “EIN” and “NAME”) were removed so the model wasn't cluttered with the information. When optimizing the model, many more variables were removed to increase accuracy.

Categories with low values in columns such as “APPLICATION_TYPE” and “CLASSIFICATION” were lumped into the “Other” category in order to create a clean data frame. OneHotEncoder was then implemented to split these columns apart which were then binary.

## Compiling, Training and Evaluation
To optimize the model, many different neural networks were run on a few different iterations of the data set. Removing columns the columns“CLASSIFICATION” and “APPLICATION_TYPE” had no significant effect on the model’s accuracy. One variable which did yield an improved accuracy was “ASK_AMT”, the amount of money the applicant had asked for. This variable was left out of our final model.

Adding additional layers and neurons to the model at times hurt the accuracy while at other times offered no significant improvement. This may be because of overfitting. Our original model consisted of 2 layers with 80 and 30 neurons. This was increased to a most of 3 layers with 100, 60 and 30 neurons. The highest accuracy came from using 2 layers with 80 and 40 neurons.

The activation function was also changed from relu to a sigmoid function to increase the model’s accuracy. The relu function works well with non-linear data but in this case of a binary target, the sigmoid function performed much better.

## Summary
I found that using 2 layers while using the sigmoid function worked best in this case. Large networks can overfit to the training data which makes them perform poorly on any other set of data. This is shown with the simple network of 2 layers consisting of 80 and 40 neurons. 
