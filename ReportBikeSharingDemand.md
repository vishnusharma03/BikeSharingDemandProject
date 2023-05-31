# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Vishnu Prabhat Sharma

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
Upon my first submission, I encountered with error that said "Kaggle not found". So, I pip installed kaggle, however prior to this I did find some difficulty in evaluating the number of negative values but I did figured it out before submitting my results & rest of code had no error.

### What was the top ranked model that performed?
My top ranked model was the "WeightedEnsemble_L3" which has a score of 0.64 with a set of parameters named "hyperparameters4" in the jupyter notebook.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
EDA found the relationship of all the features with respect to data so we got an overview of underlying trends & patterns in the data.
For adding additional features, I did take a hint from the notebook which suggested me to split datetime to separate columns & train the model again.

### How much better did your model preform after adding additional features and why do you think that is?
After adding additional features it went to a score of 0.67 from 1.80 which was score of initial training. So, it did perform better.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
The method I first uesd to optimize hyperparameters was random search which did not perform so well & score of "root_mean_squared_error" shoots up to 1.80 again.
So I used autogulon library again to set a range of hyperparameters which results in a score of 0.64 which is slightly better than the step of adding more features & training it.

### If you were given more time with this dataset, where do you think you would spend more time?
I would spend more time to tune hyperparameters by exploring different methods of tuning them. 

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
model	time	hyperparameters	eval_metric	score
0	initial	600	default	default	1.81
1	add_features	600	default	default	0.67
2	hpo	  500	multimodal	mean_absolute_percentage_error	0.72
3	hpo1	500	hyperparameters_0	root_mean_squared_error	0.80
4	hpo2	600	hyperparameters	root_mean_squared_error	1.95
5	hpo3	800	hyperparametes3	root_mean_squared_error	0.74
6	hpo4	600	hyperpatameters4	root_mean_squared_error	0.64

### Create a line plot showing the top model score for the three (or more) training runs during the project.
![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.
![model_test_score.png](img/model_test_score.png)

## Summary
In conclusion, I would say the project taught me the importance of feature engineering & hyperparameter tuning. But most important lesson I learnt is machine learning it iterative process, I need to reiterate many times for a desirable model & I can't expect it to perform best in first run.
