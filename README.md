# credit_risk_analysis

## Credit Risk Analysis Overview
________________________________

The purpose of this analysis was to look over the credit risk model and determine which, if any, prediction model to use. One of the challenges of this model is that the number of good loan applicants far outweighs the bad applications. Due to this we will need to use oversampling and undersampling to determine if we could find a model that will work the best in predicting high risk applicants.


### Methods of Analysis
_______________________

To better understand what model we should use we needed to test the models to determine which, if any, would have a high enough accuracy and precision to use. 

The six models we used were:


### 1. Naive Random Oversampling: Using instances of the minority data randomly selected to fill the data population to be in line with the majority data. 

As you can see in the image we were able to create a matched sample size for both risk categories

![This is an image](https://github.com/Bren42/credit_risk_analysis/blob/main/images/naive_random_oversample.png)

Balanced Accuracy

![This is an image](https://github.com/Bren42/credit_risk_analysis/blob/main/images/naive_random_balanced_accuracy.png)

Confusion Matrix

![This is an image](https://github.com/Bren42/credit_risk_analysis/blob/main/images/naive_confusion_matrix.png)

Classification Report

![This is an image](https://github.com/Bren42/credit_risk_analysis/blob/main/images/naive_classification_report.png)

The random oversample comes out with a accuracy of 66.7 which isn't great but it still is an overall positive prediction rate. The precision for low risk is high, but the high risk precision being .01 is fairly low. Similiar to the f1 score. This model is ok, but lets see what if we can improve upon this, predicting the low risk scores with such a high accuracy is fine, but we need to see if we can get better accuracy with our high risk applicants as this leads to the largest impact on the business.


### 2. SMOTE Oversampling: In SMOTE our tools will create synthetic oversampling using the minority data. 

Balanced Accuracy

![This is an image](https://github.com/Bren42/credit_risk_analysis/blob/main/images/smote_balanced_accuracy.png)

Confusion Matrix

![This is an image](https://github.com/Bren42/credit_risk_analysis/blob/main/images/smote_cm.png)

Classification Report

![This is an image](https://github.com/Bren42/credit_risk_analysis/blob/main/images/smote_cr.png)

In our second oversampling method, SMOTE, we see the balanced accuracy is slightly changed but not enough to be of consequence. Our f1 score saw some improvement though, however it was only in the low risk category, our high risk category stayed level. If this were our only other method we would likely use this as the model, however lets see what our other prediction models return. 



### Clustered Centroids UnderSampling

Our first two models relied on oversampling to build out our predictions. In our next model we try undersampling the data to see how they compare by using clustered centroids. 

Balanced Accuracy

![This is an image](https://github.com/Bren42/credit_risk_analysis/blob/main/images/clusteredcentroid_undersample_balanced_acc.png)

Confusion Matrix

![This is an image](https://github.com/Bren42/credit_risk_analysis/blob/main/images/clustered_centroid_CM.png)

Classification Report

![This is an image](https://github.com/Bren42/credit_risk_analysis/blob/main/images/clustered_centroid_CR.png)

The first thing of concern with this model is that the balanced accuracy score has dropped to 54.4, this alone is problematic. Looking at the classification report though confirms that this trend of lower accuracy and precision carry through this model. The f1 score being 56 really shows us that this model is not the right model to use for our prediction model. 


### SMOTEENN

We have seen results of oversampling, and undersampling. However we can use SMOTEENN to both over and undersample. We did this to test outcomes, lets see what we got from this. 

Balanced Accuracy

![This is an image](https://github.com/Bren42/credit_risk_analysis/blob/main/images/smoteenn_balanced_accuracy.png)

Confusion Matrix

![This is an image](https://github.com/Bren42/credit_risk_analysis/blob/main/images/smoteenn_CM.png)

Classification Report

![This is an image](https://github.com/Bren42/credit_risk_analysis/blob/main/images/smoteen_CR.png)

Once we look at our accuracy, 65.9, we see that it is better than our undersampling, but not quite as good as our oversampling methods. Our f1 score is 76, but again our high risk category is too low in precision. 

### Random Forests
We are now moving into the bagging and boosting methods that will combine our weak learners into a strong learner. This should help our model prediction. lets see our results.

Balanced Accuracy

![This is an image](https://github.com/Bren42/credit_risk_analysis/blob/main/images/random_forest_balanced_accuracy.png)

Confusion Matrix

![This is an image](https://github.com/Bren42/credit_risk_analysis/blob/main/images/random_forest_CM.png)

Classification Report

![This is an image](https://github.com/Bren42/credit_risk_analysis/blob/main/images/random_forest_CR.png)

As we can see our accuracy score being 68.3 falls in line with our oversample methods but our precision and f1 scores go up quite a bit. High risk precision sits at .93 and our f1 is .52 in high risk and 1.0 overall. 

Also we noted the instances of most importance to the model:

![This is an image](https://github.com/Bren42/credit_risk_analysis/blob/main/images/random_forest_importances.png)

We can see that last payment amount, total recieved principal, total recieved interest, and total payment all score very highly, above 60% Whereas the remainder of categories are 22% or lower. 


### Easy Ensemble/adaboost

The last model to test is the easy ensemble/adaboost method. 

Balanced Accuracy

![This is an image](https://github.com/Bren42/credit_risk_analysis/blob/main/images/adaboost_balanced_accuracy.png)

Confusion Matrix

![This is an image](https://github.com/Bren42/credit_risk_analysis/blob/main/images/adaboost_CM.png)

Classification Report

![This is an image](https://github.com/Bren42/credit_risk_analysis/blob/main/images/adaboost_CR.png)

As we look through this data we see several areas were this method stands out. The accuracy is the highest we have seen with a 93. Our classification matrix shows a similar precision score and a really high f1 score, also 1.0. However our random forests model showed a higher f1 score in the high risk category being 52 versus this methods 16.


## Conclusion

In looking through all our methods we can see that there is value in running each one to compare which will be best for our purposes. Based solely on the data scores we have the best method to use would be the Random Forests method as it holds the highest precision, in this particular category we would want our precision to be high, though the recall rate shows we have more to work on. 

I would also look back at the data and run the samples one more time with some of the less important features removed, if the numbers still came out near their current outputs we could make the determination to use the random forest model going forward.
