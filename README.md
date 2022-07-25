# Predict Qualification Result: IFSC sports climbing (bouldering)

This is Exploratory Machine Learning Project focusing on classification method.

### Data Acquisition
Use a dataset in Kaggle. (Source: IFSC Sport Climbing Competition Results)

### Scoring system
Bouldering is scored using a combination of tops and zones to determine rank. Athletes each get four minutes to reach the top of four boulders (three in the final), with the number of attempts influencing their final score. The aim is to top the boulder in as few attempts as possible.

Results are in the format Tz__. T corresponds to top, which means the climber reached the top hold and finished the problem. z corresponds to zone, which means the climber reached the zone hold and partially finished the problem. The numbers before each correspond to how many tops or zones were reached, and numbers after signify how many attempts were taken.

Example: 2T4z58 means that the climber had 2 tops, 4 zones, and took 5 total attempts to get the tops, and 8 total attempts to reach the zones.

Qualification: Sometimes there are multiple groups for qualifications, and when that is the case the results will be split to indicate which qualification group the climber was in.

### Exploratory Data Analytics
Check list
* Passing rate (Pass Qual/total)
* Correlation to qualification result
* Distribution of each feature
* Presence of outliers: Deal with it at feature engineering step
Features
* Top score
* Zone score
* Top attempts
* Zone attempts

### EDA Conclusion
* Outliers from passing qual consistently detected: There are some players who passed qualification with 0 and 1 top scores.
* Overall features are positively correlated with passing qualification.

### Feature Engineering
* Remove those who passed qualification with 0 and 1 top scores
* Remove outliers detected from EDA
* Other features to consider: top attempts - top and zone attempts - zone might also be relevant. Check this possibility.

### Feature Engineering Conclusion
* About 2% of entriees were removed
* Attempt - score: (top) no significance (zone) negatively correlated

## Model Evaluation and Conclusion

#### Logistic Regression Model

              precision    recall  f1-score   support
           0       0.78      0.82      0.80       118
           1       0.79      0.74      0.76       106
    accuracy                           0.78       224

![image](https://user-images.githubusercontent.com/109259233/180701267-8d8ae20b-1500-4a65-bbea-d0c1196b8fb8.png)


#### Random Forest Model
              precision    recall  f1-score   support
           0       0.73      0.72      0.73       118
           1       0.69      0.71      0.70       106
    accuracy                           0.71       224

![image](https://user-images.githubusercontent.com/109259233/180701278-0de629ec-e39a-4af1-a650-7d90517f9d02.png)


#### Support Vector Classifier Model
              precision    recall  f1-score   support

           0       0.76      0.83      0.79       118
           1       0.79      0.71      0.75       106
    accuracy                           0.77       224

![image](https://user-images.githubusercontent.com/109259233/180701299-772f9f17-acac-48ba-9ca2-a15e4802cc0c.png)


## Conclusion
* Logistic Regression model performed marginally better than Support Vector Classifier and Random Forest. It will predict the results with ~ 80% accuracy.
* The "top", "zone" are the most two stongest features to predict the Qualification results. Top attempts - Top and Zone attempts - Zone are more relavant features than just "attempts"

	Importance
top	0.695939
zone	0.413409
top attempts	0.045850
zone attempts	0.000000
attempts-zone	-0.068389
attempts-top	-0.087810
