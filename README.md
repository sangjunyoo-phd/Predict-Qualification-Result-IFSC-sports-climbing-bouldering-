# Predict Qualification Result: IFSC sports climbing (bouldering)

This is Exploratory Machine Learning Project focusing on classification method.

## Models with Logistic Classification (with Elasticnet regularization), Random Forest, Support Vector Classifier were made and evaluated

### Data Acquisition
Use a dataset in Kaggle. (Source: IFSC Sport Climbing Competition Results)

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
        Fail       0.90      0.94      0.92       250
        Pass       0.76      0.64      0.70        70
    accuracy                           0.88       320
   macro avg       0.83      0.79      0.81       320
weighted avg       0.87      0.88      0.87       320

#### Random Forest Model

              precision    recall  f1-score   support
        Fail       0.89      0.90      0.90       250
        Pass       0.64      0.61      0.63        70
    accuracy                           0.84       320
   macro avg       0.77      0.76      0.76       320
weighted avg       0.84      0.84      0.84       320

#### Support Vector Classifier Model

              precision    recall  f1-score   support
        Fail       0.88      0.95      0.92       250
        Pass       0.76      0.56      0.64        70
    accuracy                           0.87       320
   macro avg       0.82      0.75      0.78       320
weighted avg       0.86      0.87      0.86       320


## Conclusion
Regardless of model of choice, predicting failing qual is quite accurate in terms of both precision and recall. It means the negative prediction is correct in most cases and the models catch failure cases quite accurately.

Given that the accuracy is a good parameter to evaluate the overall performance, I found no significant difference between performance of Logistic model and Support Vector classification model. I would choose logistic model to predict one's qualification result because it is slightly better in performance.
