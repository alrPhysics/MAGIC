# Classifying MC simulated Gamma Telescope Data as Signal or Background 

From the dataset [description](http://archive.ics.uci.edu/ml/datasets/MAGIC+Gamma+Telescope): <br/>
*"The simple classification accuracy is not meaningful for this data, since classifying a background event as signal is worse than classifying a signal event as background. For comparison of different classifiers an ROC curve has to be used."*

Models were therefore selected for oprimization based on their ROC curve and confusion matrix. Due to how the data is prepropcessed, classifying a background event (h) as signal (g) corresponds to a Type II error or false negative.

## Models initially analyzed:
* DecisionTreeClassifier
* LogisticRegression
* MLPClassifier
* AdaBoostClassifier
* RandomForestClassifier
* GradientBoostingClassifier

## Models selected for optimization:
In order to reduce the number of false negatives, recall was selected to be the scoring parameter.

* MLPClassifier
* RandomForestClassifier
* GradientBoostingClassifier

## Results:
* MLPClassifier was found to not be optimizable for this dataset with recall as the scoring parameter. After performing a GridSearch across multiple parameters it was found that the defaults were optimal.
* RandomForestClassifier was found to be the most responsive to tuning and was able to outperform the other selected models by both reducing its Type II errors and by having the largest area under its ROC curve.

## Additional Notes:
* May return to this project to see how well the DecisionTreeClassifier responds to tuning for this dataset.
