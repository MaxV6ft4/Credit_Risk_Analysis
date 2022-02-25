# Credit Risk Analysis

## Overview
For this project I used six supervised machine learning techniques to train and evaluate models that predict the amount of risk of an individual defaulting on a loan payment.  The first four involved algorithms that oversampled and undersampled the data in order to determine a more accurate prediction of risk.  The final two techniques were models based on ensemble learning in order to increase their performance and reduce variance.

## Results

### RandomOversampler
- the balanced accuracy score of the resampled data using RandomOversampler was 0.64.
- the precision scores were 0.01 for high-risk loan statuses, 1.00 for low-risk ones and a total of 0.99.
- the recall scores were 0.66 for high-risk, 0.62 for low-risk and a total of 0.62.

![oversampled](https://github.com/MaxV6ft4/Credit_Risk_Analysis/blob/main/Screenshots/report1.png)

### SMOTE
- the balanced accuracy score of the resampled data using SMOTE was 0.65.
- the precision scores were 0.01 for high-risk loan statuses, 1.00 for low-risk ones and a total of 0.99.
- the recall scores were 0.61 for high-risk, 0.69 for low-risk and a total of 0.69.

![smote](https://github.com/MaxV6ft4/Credit_Risk_Analysis/blob/main/Screenshots/report2.png)

### ClusterCentroids
- the balanced accuracy score of the resampled data using the ClusterCentroids undersampler was 0.54.
- the precision scores were 0.01 for high-risk loan statuses, 1.00 for low-risk ones and a total of 0.99.
- the recall scores were 0.69 for high-risk, 0.40 for low-risk and a total of 0.40.

![CC](https://github.com/MaxV6ft4/Credit_Risk_Analysis/blob/main/Screenshots/report3.png)

### SMOTEENN
- the balanced accuracy score of the resampled data using the SMOTEENN combined resampler was 0.64.
- the precision scores were 0.01 for high-risk loan statuses, 1.00 for low-risk ones and a total of 0.99.
- the recall scores were 0.71 for high-risk, 0.57 for low-risk and a total of 0.57.

![smoteenn](https://github.com/MaxV6ft4/Credit_Risk_Analysis/blob/main/Screenshots/report4.png)

### BalancedRandomForestClassifier
- the balanced accuracy score of the data using BalancedRandomForestClassifier was 0.79.
- the precision scores were 0.03 for high-risk loan statuses, 1.00 for low-risk ones and a total of 0.99.
- the recall scores were 0.70 for high-risk, 0.87 for low-risk and a total of 0.87.

![brfc](https://github.com/MaxV6ft4/Credit_Risk_Analysis/blob/main/Screenshots/report5.png)

### EasyEnsembleClassifier
- the balanced accuracy score of the data using EasyEnsembleClassifier was 0.93.
- the precision scores were 0.09 for high-risk loan statuses, 1.00 for low-risk ones and a total of 0.99.
- the recall scores were 0.92 for high-risk, 0.94 for low-risk and a total of 0.94.

![eec](https://github.com/MaxV6ft4/Credit_Risk_Analysis/blob/main/Screenshots/report6.png)

## Summary
All six models displayed mostly different balanced accuracy, precision and recall scores.  The four algorithms used to predict risk through resampled data displayed balanced accuracy scores ranging between 0.54-0.65, precision scores all equalling 0.01 for high-risk loan statuses, 1.00 for low-risk statuses and 0.99 for the total. Recall scores ranged between 0.66-0.71 for high-risk loan statuses, and between 0.40-0.69 for both low-risk statuses and the totals.  The main determinant of a good model in these four cases is the balanced accuracy score.  The two algorithms used to predict risk through ensemble classifiers had balanced accuracy scores of 0.79 and 0.93.  Plus, their precision scores were 0.03 and 0.09 for high-risk loan statuses, both higher than the high-risk precision scores based on resampled data.  Finally, the recall scores were 0.70 and 0.92 for high-risk loans; 0.87 and 0.94 for low-risk loans, significantly higher than recall scores based on resampled data.

### Recommendations
Sensitivity/recall is more important here than precision.  It is better to determine each case of potential defaulting on a loan payment even if that includes the false negatives i.e. the ones that will default even if the model didn't predict those to do so.  If we were relying on precision here, the cases of potential defaulting would include all postives plus the false positives (those predicted to default but actually didn't), but would miss out on those that defaulted but were not predicted to do so.  Therefore, the best model to use in this case is the Easy Ensemble Classifier because it provided the highest recall scores for both high and low-risk loan statuses.  There would be very few false negatives (defaulting on a loan that wasn't predicted to do so).
