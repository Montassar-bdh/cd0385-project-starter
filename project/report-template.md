# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### MONTASSAR BEN DHIFALLAH

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
TODO: I observed that predictions has some negative RMSE values.We now know that if we don't set everything to be bigger than 0, Kaggle will reject the prediction.
To deal with this situation, I first counted the number of negative score predictions the predictor returned before setting all of the negative predictions to 0. 
I assign those predictions to the submission dataframe at the end.

### What was the top ranked model that performed?
TODO: the third model performed the best with a score of 0.46006 after performing feature engineering and hyperparameter tuning.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
TODO: When performed EDA, I found that 'weather' and 'season' distributions illustrated catagorical values. The other distributions are related to continuous features.
As for the additional features, I split the datetime into year, month, day and hour and deleted the original feature.

### How much better did your model preform after adding additional features and why do you think that is?
TODO: After adding additional features, the model performed better than the original one (from 1.80785 to 0.46979).

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
TODO: The model performed slightly better after changing hyper parameters. the RMSE score is reduced to 0.46006

### If you were given more time with this dataset, where do you think you would spend more time?
TODO: I will:
1. Try multiple hyperparameter tuning experiments with different combinations and values.
2. Try different feature engineering techniques such as feature scaling.


### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|time|num_boost_round|num_epochs|score|
|--|--|--|--|--|
|initial|600|default|default|1.80785|
|add_features|600|default|default|0.46979|
|hpo|600|100|10|0.46006|
|hpo2|900|120|15|0.46505|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](img/model_test_score.png)

## Summary
TODO: In this case study, the objective was to construct a regression model for predicting bike demand using historical bike sharing data. Initially, I examined the features by plotting sample rows and utilizing the describe method in pandas. Following that, I built an initial model using default parameters without extensively modifying the features. After training the model, I obtained the initial RMSE score.

The following step entailed conducting an exploratory data analysis (EDA) to assess the patterns within the features. Upon analyzing the plots, I made the decision to transform an existing numeric feature into a categorical one and incorporated new features to capture time-related information for each record. Subsequently, I trained the model, which led to a significant enhancement in the RMSE Kaggle score on the test data.

Having preprocessed the features, I made the decision to fine-tune the hyperparameters for the model algorithm. I opted for two options: GBM, a tree-based model, and a deep neural network, each with distinct hyperparameter configurations. The model got slightly better.
Afterward, I conducted a comparison of the Kaggle scores from all the trained models, and then charted these scores against the hyperparameter settings to analyze the degree of improvement or deterioration in performance.
