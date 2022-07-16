# Predict Qualification Result: IFSC sports climbing (bouldering)

This is Exploratory Machine Learning Project focusing on classification method.

## Models with Logistic Classification (with Elasticnet regularization), Random Forest, Support Vector Classifier were made and evaluated

### Data Acquisition
Use a dataset in Kaggle. (Source: IFSC Sport Climbing Competition Results)

### Scoring system
Bouldering is scored using a combination of tops and zones to determine rank. Athletes each get four minutes to reach the top of four boulders (three in the final), with the number of attempts influencing their final score. The aim is to top the boulder in as few attempts as possible.

Results are in the format Tz__. T corresponds to top, which means the climber reached the top hold and finished the problem. z corresponds to zone, which means the climber reached the zone hold and partially finished the problem. The numbers before each correspond to how many tops or zones were reached, and numbers after signify how many attempts were taken.

Example: 2T4z58 means that the climber had 2 tops, 4 zones, and took 5 total attempts to get the tops, and 8 total attempts to reach the zones.

Qualification: Sometimes there are multiple groups for qualifications, and when that is the case the results will be split to indicate which qualification group the climber was in.

### Feature Engineering

Narrow down our interst to adult competition only.

Merge Qualification, Qual1, and Qual2 columns together for the reason mentioned above.

Re-frame the string score data to numeric variables and check the correlation to the passing Qual.

### Train / Test models
Perform various classification methods: Logistic Regression, Tree-based mehtod, and Support Vector Classifier.

### Evalutation of the model
Consider accuracy and f1 score: Generally good score to evaluate the model.

Recall/Precision: Missing pass/fail Qual is not critical


## Model Evaluation and Conclusion

#### Logistic Regression Model
              precision    recall  f1-score   support

        Fail       0.87      0.95      0.91       235
        Pass       0.81      0.61      0.70        85
    accuracy                           0.86       320
   macro avg       0.84      0.78      0.80       320
weighted avg       0.86      0.86      0.85       320


#### Random Forest Model
              precision    recall  f1-score   support

        Fail       0.88      0.90      0.89       235
        Pass       0.71      0.66      0.68        85
    accuracy                           0.84       320
   macro avg       0.79      0.78      0.79       320
weighted avg       0.83      0.84      0.84       320


#### Support Vector Classifier Model
              precision    recall  f1-score   support

        Fail       0.85      0.97      0.91       235
        Pass       0.87      0.54      0.67        85
    accuracy                           0.86       320
   macro avg       0.86      0.76      0.79       320
weighted avg       0.86      0.86      0.84       320

## Conclusion
Regardless of model of choice, predicting failing qual is quite accurate in terms of both precision and recall. It means the negative prediction is correct in most cases and the models catch failure cases quite accurately.

Given that the accuracy is a good parameter to evaluate the overall performance, I found no significant difference between performance of Logistic model and Support Vector classification model. I would choose logistic model to predict one's qualification result because it is slightly better in performance.
