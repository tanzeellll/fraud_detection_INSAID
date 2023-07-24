# fraud_detection_INSAID
This case requires trainees to develop a model for predicting fraudulent transactions for a financial company and use insights from the model to develop an actionable plan. Data for the case is available in CSV format having 6362620 rows and 10 columns.

Candidates can use whatever method they wish to develop their machine learning model. 
Following usual model development procedures, the model would be estimated on the 
calibration data and tested on the validation data. This case requires both statistical analysis and 
creativity/judgment. We recommend you spend time on both fine-tuning and interpreting the 
results of your machine learning model.

1. Data cleaning including missing values, outliers and multi-collinearity.
_No missing values/nanvalues
_The range for bank balance and transaction amount varies but unfortunately we cannot determine clear outliers and we have fraud cases for transaction as high as 10000000
_Very high multi-collinearity is observed among the following columns oldbalanceOrg, newbalanceOrig, oldbalanceDest	newbalanceDest, with VIF value as high as 500
_Final comment on data cleaning - Was fairly easy as the no of columns associated with the dataset was less

2. Describe your fraud detection model in elaboration.
_The idea was to train multiple models and then choose the best performing model
_To head into the modelling phase, decision tree was the most favaourable as it it is not prone to different scales in data thus no normalization or standardization was required
_It is even not sensitive to imbalance, which is the biggest problem with this dataset
_After training the dcision tree, random forest and the logistic regression model we have concluded thst the tree and random forest models are at par
_i would still prefer the decision tree as we had to undersample the data to train the random forest model


3. How did you select variables to be included in the model?
_Selecting variable to be included was rather easy due the less no of feature columns
_Excluded the 2 IDs and other than this rest all were included, it would be a no brainer to not include these for the tree based models
_unfortunately a few need to be excluded due to the high multi-collinearity but this would result in massive reduction in no of independent features

4. Demonstrate the performance of the model by using best set of tools.
_

### Decision Tree Classifier 
##### Model performance for train set 
Accuracy: 1.0000 </br>
F1 Score: 1.0000 </br>
Precision: 1.0000 </br>
Recall: 1.0000 </br>

##### Model performance for test set 
Accuracy: 0.9997 </br>
F1 Score: 0.9997 </br>
Precision: 0.9028 </br>
Recall: 0.8768
</br>
</br>

### Random Forest Classifier
##### Model performance for train set
Accuracy: 0.9919</br>
F1 Score: 0.9950</br>
Precision: 0.1383</br>
Recall: 1.0000</br>

##### Model performance for test set
Accuracy: 0.9918</br>
F1 Score: 0.9949</br>
Precision: 0.1361</br>
Recall: 1.0000</br>

### Logistic Regression Classifier
##### Model performance for train set
Accuracy: 0.4549</br>
F1 Score: 0.6240</br>
Precision: 0.0019</br>
Recall: 0.8027</br>

##### Model performance for test set
Accuracy: 0.4544</br>
F1 Score: 0.6235</br>
Precision: 0.0019</br>
Recall: 0.8127</br>



5. What are the key factors that predict fraudulent customer?
_Most of the fraudulent transactions are of CASH_OUT or TRANSFER type
_Most of the fraudulent transactions amount is between 125k and 1.5 mil
_Most of the fraudulent transactions have an amount newbalanceOrig of 0.0
_Most of the fraudulent transactions have amount oldbalanceDest of 0.0


6. Do these factors make sense? If yes, How? If not, How not?
_Yes these factors do make sense
_These give us insights into the kind of transactions we need to monitor better

7. What kind of prevention should be adopted while company update its infrastructure?
_Robust Authentication: Implement multi-factor authentication (MFA) to ensure that only authorized individuals can access sensitive systems and data. MFA typically involves a combination of passwords, biometrics, tokens, or one-time passcodes.
_Data Governance: Implement a comprehensive data governance framework that outlines policies, procedures, and responsibilities related to data management, including data analysis. This framework ensures that data is handled securely, ethically, and in accordance with established standards
_Secure Data Transfer: During the infrastructure update, ensure that transactional data remains secure during transit between systems or during data transfers. Use secure protocols and encryption methods to protect data integrity and confidentiality
_Access Control and Authentication: Implement robust access control mechanisms to restrict access to sensitive transactional data. Enforce strong authentication protocols, such as multi-factor authentication, to ensure that only authorized personnel can access the data and systems involved in fraud analysis

8. Assuming these actions have been implemented, how would you determine if they work?
_Rduction in the no of fraudulent transactions will be a KPI for the implementation of above

