# Assignment for data science intern

## Task: 
I have to develop a machine learning model which will classify whether the customer will subscribe the term deposit or not.

### Data: 
The data was from UCI data repository website and data contained the information about the customer such as marital status, education background, age, loan etc and target column had yes or no values for all the customers.

### Approach:
1. First I did the exploratory data analysis and found that there were a few continuous features such as duration, employment price index, previous which were showing a good statistical significance with target columns. I measured statistical significance with p-values.

2. During EDA, I also found that there were very few values in target column which had "yes". So, I thought to do oversampling of minor values using 'SMOTE'.

3. Then I checked whether null values were in the data or not and then did the categorical encoding using pandas dummies.

4. After that, I splitted the data into training and validation set using stratifiedkfold and made a baseline model using logistic regression. The accuracy score was about 85%.

5. I used stratified k fold to ensure that all folds have same ratio of 'yes' and 'no' values.

6. Now, I decided to move bagging algorithms and trained a few models using the following algorithms:
   a. Decision tree classifier: accuracy score is 0.7387588618044091
   b. Random forest classifier: accuracy score is 0.857264251723803
   
7. Finally, I went for boosting algorithm and I used lightgbm. I did the hyperparameter tuning using sklearn bayesian optimization and train the algorithm. acccuracy score was around 88.5%.

8. Now, I decided to do feature selection by checking the feature importance given by lightgbm and dropped 5 features which were not good in gain for the model and my accuracy went to 88.76%.

9. Finally, I tried oversampling using SMOTE but it didn't gave any significant risr in accuracy so, I dropped the idea.

### What could be done:
Due to lack of time couldn't to the feature engineering and also do much of exploratory data analysis.

## Business Use of the model:
My model had around 89% percent accuracy for classifying between whether the customer will take the term deposit or not. Now, Suppose if a company want to sent messages to its customers for their new plan so, If they will use my model then it will predict with 89% percent
accuracy whether the particular customer will take that plan or not and in this way they can remove remove those customer from their list about which model predicted 'no'. 

My model is also significant to company because if there is a customer of which they have predict whether he/she will take the offer then random guessing has 50% chance whereas my model has around 89% chance to be correct which is good figure.

By using my model the company would be able to keep only those customers which has chance of accepting the offer which results in decrease in the amount required for the messages as unwanted customers won't recieve the calls and we are maximising the number of useful customers.
