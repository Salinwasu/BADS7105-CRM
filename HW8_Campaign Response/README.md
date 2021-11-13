# Campaign Response Model
The response model is a [classification model](https://analyticsindiamag.com/7-types-classification-algorithms/). The task is to classify the customers who will respond to the next marketing campaign on the basis of information collected about the customers. The first step in the predictive modeling process is to determine the objective variable to be modeled.

![1*z87SfYsRHLutMhuiE9nZ7g](https://user-images.githubusercontent.com/69904258/141609174-5f182d42-5db3-4f28-bc3f-a741ebecda1c.png)
 
 # Dataset
 1. Retail Responsse Data consisting of Customer_ID and Response
 2. Retail Transaction Data consisting of Customer_ID , Transaction date and Transactiom amount 

<img width="1377" alt="Screen Shot 2564-11-13 at 13 36 42" src="https://user-images.githubusercontent.com/69904258/141609450-1182f2ea-aac2-428d-b7c2-bf199d07f867.png">
 
 # What I do in this class ?
 * Evaluate models choosing from a combination of Models: 
   * [LogisticRegression](https://searchbusinessanalytics.techtarget.com/definition/logistic-regression) , [XGBoost](https://medium.com/sfu-cspmp/xgboost-a-deep-dive-into-boosting-f06c9c41349) and [SVM](https://medium.com/@LSchultebraucks/introduction-to-support-vector-machines-9f8161ae2fcb)
* Dataset: using some features and a selective set
* Resampling: SMOTE, SMOTE+TOMEK Links and SMOTE+ENN
 # EDA
 Overview of transaction amount
 
 <img width="1370" alt="Screen Shot 2564-11-13 at 14 23 29" src="https://user-images.githubusercontent.com/69904258/141610028-0c8a77af-8985-4ba9-b8be-853976261c29.png">

 Overview of response campaign
 
<img width="1371" alt="Screen Shot 2564-11-13 at 14 23 45" src="https://user-images.githubusercontent.com/69904258/141610040-93aa6ff3-84c5-4bce-ad8a-11c90fc4b0ca.png">

# Data Preparation 

> Create data set with CLV variables

The [Customer Lifetime Value](https://medium.com/magnimetrics/customer-lifetime-value-clv-an-essential-business-metric-a40ae14cc6e5) (CLV) shows us how much money a customer will bring to the business on average over the entire time they remain a paying client.

<img width="1380" alt="Screen Shot 2564-11-13 at 14 33 34" src="https://user-images.githubusercontent.com/69904258/141610289-410d5364-9dc5-4883-bdd8-cca76cca2441.png">

> Calculating response rate

<img width="960" alt="Screen Shot 2564-11-13 at 14 41 06" src="https://user-images.githubusercontent.com/69904258/141610512-4799107e-2a08-47f1-a302-8c9b45f87931.png">

> Plot Response distirbution

<img width="1368" alt="Screen Shot 2564-11-13 at 14 42 36" src="https://user-images.githubusercontent.com/69904258/141610549-e1424489-c8ac-4b45-a008-6afc8996b792.png">

> Merging two data sets - df_response and df_clv

<img width="1366" alt="Screen Shot 2564-11-13 at 14 46 00" src="https://user-images.githubusercontent.com/69904258/141610627-3cf9899e-c06c-4ec1-9f02-1fffb2b39938.png">

> Plot Overview of Data 

<img width="1365" alt="Screen Shot 2564-11-13 at 14 47 58" src="https://user-images.githubusercontent.com/69904258/141610693-63bbaa55-c332-4b5a-a545-7ed3527a5492.png">

<img width="1058" alt="Screen Shot 2564-11-13 at 14 50 08" src="https://user-images.githubusercontent.com/69904258/141610741-9f438906-5f06-4065-9e9b-c0fc27c1f4fe.png">

# Creating train and test dataset
> spliting dataframe into X and y

* X_clv = df_modeling_clv.drop(columns=['response','customer_id'])
   * Drop column response and customer_id for X dataframe
* y_clv = df_modeling_clv['response']
   * Use only column response for y DataFrame for Prediction 

<img width="1374" alt="Screen Shot 2564-11-13 at 14 58 40" src="https://user-images.githubusercontent.com/69904258/141611003-84ef2be9-58b0-4ef7-9df3-d6334da12bf1.png">

# Fixing imbalanced with SMOTE, SMOTE+TOMEK Links and SMOTE+ENN
### SMOTE: Synthetic Minority Oversampling Technique
* [SMOTE](https://www.analyticsvidhya.com/blog/2020/10/overcoming-class-imbalance-using-smote-techniques/) is an oversampling technique where the synthetic samples are generated for the minority class. This algorithm helps to overcome the overfitting problem posed by random oversampling. It focuses on the feature space to generate new instances with the help of interpolation between the positive instances that lie together.

![77417image1](https://user-images.githubusercontent.com/69904258/141611131-29916ebd-3445-4049-a3de-f3a999bb8223.png)
 
### Hybridization: SMOTE + Tomek Links
* SMOTE+TOMEK is such a hybrid technique that aims to clean overlapping data points for each of the classes distributed in sample space. After the oversampling is done by SMOTE, the class clusters may be invading each other’s space. As a result, the classifier model will be overfitting
* Tomek links are applied to oversampled minority class samples done by SMOTE. Thus instead of removing the observations only from the majority class, we generally remove both the class observations from the Tomek links.

### Hybridization: SMOTE + ENN
* SMOTE + ENN is another hybrid technique where more no. of observations are removed from the sample space. Here, ENN is yet another undersampling technique where the nearest neighbors of each of the majority class is estimated. If the nearest neighbors misclassify that particular instance of the majority class, then that instance gets deleted.

> The below-given picture shows how different SMOTE based resampling techniques work out to deal with imbalanced data.

![19616image7](https://user-images.githubusercontent.com/69904258/141611311-0961e186-4199-460c-89ea-3d44be87d72d.png)

### Python code for SMOTE, SMOTE + Tomek Links and SMOTE + ENN

<img width="1384" alt="Screen Shot 2564-11-13 at 15 13 05" src="https://user-images.githubusercontent.com/69904258/141611421-e68f4574-cc7c-49e1-bc2f-e5e0be6b258c.png">

# Model Performance
## Logistic regression model
It’s a classification algorithm, that is used where the response variable is categorical. The idea of Logistic Regression is to find a relationship between features and probability of particular outcome.
### Logistic regression model - SMOTE CLV

<img width="1142" alt="Screen Shot 2564-11-13 at 15 25 19" src="https://user-images.githubusercontent.com/69904258/141611727-a7ced524-0783-4a45-8196-6c54f08c20d4.png">

### Logistic regression model - SMOTETomek CLV

<img width="1140" alt="Screen Shot 2564-11-13 at 15 26 54" src="https://user-images.githubusercontent.com/69904258/141611758-5009c718-9a38-4762-9083-ef5341d111a4.png">

### Logistic regression model - SMOTEENN CLV

<img width="1141" alt="Screen Shot 2564-11-13 at 15 28 12" src="https://user-images.githubusercontent.com/69904258/141611784-11c34d0b-02a9-4f80-ba3f-81d91033ba09.png">

## XGBoost model
eXtreme Gradient Boosting (XGBoost) is a scalable and improved version of the gradient boosting algorithm (terminology alert) designed for efficacy, computational speed and model performance. It is an open-source library and a part of the Distributed Machine Learning Community. XGBoost is a perfect blend of software and hardware capabilities designed to enhance existing boosting techniques with accuracy in the shortest amount of time. 

### XGBoost model - SMOTE CLV

<img width="1365" alt="Screen Shot 2564-11-13 at 15 30 44" src="https://user-images.githubusercontent.com/69904258/141611844-6cacf9f5-65e1-4872-af24-b35e17982e79.png">

### XGBoost model - SSMOTETomek CLV

<img width="1363" alt="Screen Shot 2564-11-13 at 15 31 42" src="https://user-images.githubusercontent.com/69904258/141611890-dca9ae6c-d88f-4b81-afa9-b2538ac5d62e.png">

### XGBoost model - SMOTEENN CLV

<img width="1365" alt="Screen Shot 2564-11-13 at 15 32 34" src="https://user-images.githubusercontent.com/69904258/141611919-53fe523d-d35e-440e-9654-eaa262825300.png">

## SVM model
Support Vector Machines are supervised learning models for classification and regression problems. They can solve linear and non-linear problems and work well for many practical problems. The idea of Support Vector Machines is simple: The algorithm creates a line which separates the classes in case e.g. in a classification problem. The goal of the line is to maximizing the margin between the points on either side of the so called decision line. The benefit of this process is, that after the separation, the model can easily guess the target classes (labels) for new cases.

### SVM model - SMOTE CLV

<img width="1368" alt="Screen Shot 2564-11-13 at 15 34 48" src="https://user-images.githubusercontent.com/69904258/141611995-f48ce689-bbde-4b75-8c52-85b0a931ae4e.png">

### SVM model - SMOTETomek CLV

<img width="1364" alt="Screen Shot 2564-11-13 at 15 35 43" src="https://user-images.githubusercontent.com/69904258/141612031-d1c830cd-5001-43c4-a490-31efbc046aa3.png">

### SVM model - SMOTEENNomek CLV

<img width="1362" alt="Screen Shot 2564-11-13 at 15 38 22" src="https://user-images.githubusercontent.com/69904258/141612090-451042ad-d89c-43c2-b16f-f1f597c00b4c.png">

# What is [AUC Score](https://medium.com/analytics-vidhya/understanding-the-auc-roc-curve-cdc754d7b58a)
* AUC also called as AREA UNDER CURVE.It is used in classification analysis in order to determine which of the used models predicts the classes best. An example of its application are ROC curves. AUC ranges in value from 0 to 1
* AUC ranges in value from 0 to 1. A model whose predictions are 100% wrong has an AUC of 0 and if the predictions are 100% correct has an AUC of 1.
* Thus, Higher AUC score is Better model performance 

# In conclusion 
The best model to classify in Campaign Response Model is  SVM model - SMOTETomek CLV becuase there is high Auc score between training set and test set , and the value are closely which mean the model do not overfitting.






