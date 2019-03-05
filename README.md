# Internship-Assignment
##### Used the following steps to answer the first objective whether more practice means better performance.
##### Importing useful data:

- As the data is in multiple json files, First created a local mongodb data base and imported all the json files as collections.
- Later imported the pymongo module to jupyter notebook to interact with local database and do analysis.
- As all the collections are not required for our first objective, we only use attempts, users, and attemptdetails collections.
- Later normalized all these collections to pandas dataframe and later converted into csv files so that we don't need to import collections every time, instead we can load directly the csv files to do analysis.

##### analysis:
- As the problem statement says we should only do analysis on not abandoned tests.
- So we deleted all the observations where isabandoned equal to true.
- As most of tests taken by students are placement readiness tests, I have done analysis on placement readiness tests observations. 
- Next we have considered number of attempts as practice metric which states students who has attempted more number of tests has practiced more and vice versa.
- considered average of total Marks as performance metric which states student who got more average of total marks has better performance.
- we have used linear regression model to say whether the student performance improved with number of attempts.
- For example user 1 has taken 5 tests, and we have 5 total marks like 20, 40, 55, 65, 78 etc, so we will fit the linear regression model on these 5 tests, and based on coefficient, if coefficient is positive means performance has increased and if coefficient is negative performance has decreased.
- By using the above observation I have encoded every user with performance column whether improved or not improved.
- We got like out of 2440 students who attempted more than 2 tests, 1370 students improved and 1070 students performance is not improved.
- As now we have the performance column which can be used as explanatory or target variable. I have used logistic regression and K nearest neighbour algorithms to fit the model and predict the test variables.
- Out of both the models, we are getting best accuracy with logistic regression model of 56.8% compared to 53% of KNN.
- Though logistic regression is best model compared to knn, It is not the single best model for our dataset as its accuracy is on ly 56.8% and also the recall reate on 'not improved' class variables is very low of 0.30
- Still we can use other algorithms to improve the accuracty of prediction.
