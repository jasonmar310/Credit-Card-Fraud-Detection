Topic:
Detection for fraud credit card transactions
The propose of this project is to train and test the model to with different classifiers to examine the accuracy and performance each of them.

Used Dataset:
https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

Cited:
Andrea Dal Pozzolo, Olivier Caelen, Reid A. Johnson and Gianluca Bontempi. Calibrating Probability with Undersampling for Unbalanced Classification. In Symposium on Computational Intelligence and Data Mining (CIDM), IEEE, 2015

Instructions of running the code:
1.	Upload the dataset ‘creditcard.csv’ into the workspace. (Huge dataset would take some time)
2.	Run each section in. ipynb file from the top to bottom.
3.	Note that some of the results may take about 1 minutes to complete.
Summary:
	First, we explore the dataset, and check the missing values, duplicated rows as well. 
The second step, we are standardizing the chosen features ‘Amount’ and ‘Time’. The change only occurred in axis values; the shapes of distribution remain the same.
	We are conducting three classification algorithms to get the accuracy one by one. ROC curve can examine the TPR an FPR inside our model. (Decision Tree in this case)
 
 
 
 
However, in an imbalance dataset, accuracy is not enough to prove our models’ efficiency. So, in the next step, we are going to conduct the voting ensemble, checking its f1 and recall score.
	In our ensemble model, we chose DT, LR, and NB as our parameters. The max_depth is 5, since we don’t want the model being overfitting. 
 
Then we conducted the features selection to drop the features did not meet our threshold as 0.1. After rerunning the model, we have a better f1 score than original f1 score.
 
The last step is to ensemble the model by using the VotingClassifier(). We chose the best max_depth, 6, as our hyperparameter.
 
The depth 6 has the highest f1 score in filtered f1, 0.8328.
	In our ensemble model, the voting ensemble and its enhanced version didn’t own the higher f1 and recall score than the filtered version, max_depth = 6 above.
 
	Note that: In enhanced version, we added two more DT classifiers with depth = 5 and 7.
	To sum up, our voting ensemble model didn’t work best with the dataset. The features filtered model has the best output than other models.
