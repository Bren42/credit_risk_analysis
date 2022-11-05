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




