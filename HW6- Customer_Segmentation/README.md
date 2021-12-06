# Customer Segmentation

![Customer-segmentation](https://user-images.githubusercontent.com/69904258/144884303-9a55ba9d-bb8a-459f-a97c-b99ef10c4a5e.png)

### What is [customer segmentation](https://medium.com/@fenjiro/a-gentle-introduction-to-customer-segmentation-c5ce77a1e52b) ?
Segmentation is the fact of grouping similar elements having the same characteristics into the same segment. The resulting segments split the concerned population into groups that share the same features, and so can be handled the same way.

### What did I do ?
1. Set up [PyCaret](https://pycaret.org) 
PyCaret is an open source, low-code machine learning library in Python that allows you to go from preparing your data to deploying your model within minutes in your choice of notebook environment.

![pycaret2 3](https://user-images.githubusercontent.com/69904258/144885446-b4f059d1-4157-4146-bfd3-816cd6a04cd8.png)

### who should PyCaret ?

PyCaret is an open source library that anybody can use. In our view the ideal target audience of PyCaret is: 

* Experienced Data Scientists who want to increase productivity.
* Citizen Data Scientists who prefer a low code machine learning solution.
* Data Science Professionals who want to build rapid prototypes.
* Data Science and Machine Learning students and enthusiasts.

2. Load Data 
* The given Supermarket dataset 
<img width="1272" alt="Screen Shot 2564-12-06 at 23 39 43" src="https://user-images.githubusercontent.com/69904258/144885815-754dc8a1-f664-45ef-8715-ac27650b1345.png">

3. Generate Customer Single View

* Group transaction data by Customer Code
* Calculate ticket size 
* Find max date in the dataset
* Calculate total days of the relationship
* Calculate recency days
* Percentage of Shop on Weekday
* Percentage of Shop on DayTime
* Visulization 

## Single-purchase SKU
<img width="593" alt="Screen Shot 2564-12-06 at 23 47 19" src="https://user-images.githubusercontent.com/69904258/144887016-730cb400-243e-4dba-9bd0-473714d58aa4.png">

## Box plot of Total visit and Total spend by Total SKU
<img width="882" alt="Screen Shot 2564-12-06 at 23 48 52" src="https://user-images.githubusercontent.com/69904258/144887331-865985d6-051d-4b85-92e4-7d823573229c.png">

3. Compare model performance 

* [Elbow method](https://medium.com/@fenjiro/a-gentle-introduction-to-customer-segmentation-c5ce77a1e52b) use total within-cluster sum of square (WSS) as a function of the number of clusters, which measures how spread apart the clusters are from each other. So, K-means algorithm is run for a set of value k (e.g k ϵ [0…10]), and WWS is calculated for each k and plotted (see figure below). The number of clusters is chosen in such a way that adding a new cluster does not improve the WSS.

### Elbow plot of SC model 
<img width="566" alt="Screen Shot 2564-12-06 at 23 52 00" src="https://user-images.githubusercontent.com/69904258/144887724-d8406928-87b8-4a33-8fee-0e2019e10d69.png">

### Elbow plot of Kmodes model 
<img width="550" alt="Screen Shot 2564-12-06 at 23 53 58" src="https://user-images.githubusercontent.com/69904258/144888066-e8b4e07d-49f4-4689-9a69-0d07c6647a79.png">

### Elbow plot of Kmeans model 
<img width="538" alt="Screen Shot 2564-12-06 at 23 55 13" src="https://user-images.githubusercontent.com/69904258/144888241-0c1a0497-8bcd-435c-85ae-c35b8b96d368.png">

* Average silhouette method measures the quality of a clustering which shows how well each object lies within its cluster. A high average silhouette width indicates a good clustering.

### Silhouette plot of Kmodes 
<img width="515" alt="Screen Shot 2564-12-06 at 23 57 18" src="https://user-images.githubusercontent.com/69904258/144888554-1e59cce4-1f57-4074-9ae5-7caa67d7be7a.png">

### Silhouette plot of Kmeans
<img width="521" alt="Screen Shot 2564-12-06 at 23 58 05" src="https://user-images.githubusercontent.com/69904258/144888702-ae88a3ac-4641-400d-bf99-190eb7124e6e.png">

* PCA (Principal Component Analysis) is a statistical method that reduce dataset variables N by grouping highly correlated ones at the expense of accuracy via the creation of new variables N’called “principal components” and projecting the original dataset in the new vector space of N’ dimensions.

### 2D cluster PCA plot of SC Model
<img width="1428" alt="Screen Shot 2564-12-06 at 23 59 55" src="https://user-images.githubusercontent.com/69904258/144889002-abde210e-d6da-467c-9714-83a426b5d57b.png">

### 2D cluster PCA plot of Kmodes Model
<img width="1429" alt="Screen Shot 2564-12-07 at 00 01 33" src="https://user-images.githubusercontent.com/69904258/144889274-715822f2-35e1-4060-bc38-d702d3a0fcd9.png">

### 2D cluster PCA plot of Kmeans Model
<img width="1429" alt="Screen Shot 2564-12-07 at 00 02 41" src="https://user-images.githubusercontent.com/69904258/144889438-5500075d-92d5-496d-b55f-a7881086e3c4.png">

## The results of 2D PCA show that Kmeans is the best model for clustering 

4. K-means Model
# [K-means Model](https://medium.com/data-folks-indonesia/step-by-step-to-understanding-k-means-clustering-and-implementation-with-sklearn-b55803f519d6)
<img width="1105" alt="Screen Shot 2564-12-07 at 00 07 06" src="https://user-images.githubusercontent.com/69904258/144890093-5af98c9f-4503-4107-b7fa-52c81b6030d1.png">

* K-means clustering is a simple and elegant approach for partitioning a
data set into K distinct, non-overlapping clusters. To perform K-means
clustering, we must first specify the desired number of clusters K; then the
K-means algorithm will assign each observation to exactly one of the K
clusters
## K-means Results
## Total Distribution
<img width="1427" alt="Screen Shot 2564-12-07 at 00 12 03" src="https://user-images.githubusercontent.com/69904258/144890858-f5e0465e-374f-4330-a181-005a97712ba6.png">

## Total Spend Distribution
<img width="1417" alt="Screen Shot 2564-12-07 at 00 13 46" src="https://user-images.githubusercontent.com/69904258/144891067-df987e8e-5f88-4212-8127-661fc32e0ad1.png">

* Cluster 2 is focus group of top spender .
* Cluster 0 is second group with medium spend.
* Cluster 1 and Cluster 3 is the last group with low spend.

## Total Recency Distribution
<img width="1418" alt="Screen Shot 2564-12-07 at 00 18 06" src="https://user-images.githubusercontent.com/69904258/144891676-5854ad13-6090-43ea-ae38-83ce1ec1268a.png">

* Cluster 1 and Cluster 3 have high recency.
* Cluster 0 has medium recency.
* Cluster 2 has the lowest recency. 

## Total TicketSize Distribution
<img width="1417" alt="Screen Shot 2564-12-07 at 00 22 05" src="https://user-images.githubusercontent.com/69904258/144892191-4b52ba69-a73b-4901-86c6-873b344ebebf.png">

* Cluster 2 has the biggest ticket size.
* Others seem not different in ticket size.

## Total percentage of weekdays Distribution
<img width="1428" alt="Screen Shot 2564-12-07 at 00 24 42" src="https://user-images.githubusercontent.com/69904258/144892557-f28ce59c-2270-4cc1-83b7-66566ee24d79.png">

* There is only cluster 3 that come to shop at Weekend.

## Total percentage of shop days Distribution
<img width="1426" alt="Screen Shot 2564-12-07 at 00 26 56" src="https://user-images.githubusercontent.com/69904258/144892887-a4cb6cb7-f4e6-4558-bbe6-3da92922e374.png">

* There are only cluster 0 and cluster 2 that come on day time.

# SUMMARY 
* The cluster 0 (Blue) : 2nd Most customers, Active user, Purchasing ast small shop mainly, Not much total spent. Try to upselling with more premium products.
* The cluster 1 (Orange) : Rich customer, not much in quantity but high value and profitable, mainly non food purchasing, very active customers. Should be the customers near the shop location. They are our treasure, bind them with the premium membership with exclusive deal, offer and make sure they we can maintan them. Considerr to brach new line with the popular "non food" product
* The cluster 2 (Green) : The most in quantity customers, low ticket size and high recency. Potential the normal customer, routinely check the price competitive of our products
* The cluster 3 (Purple) - WholeSell : Not much in this customer group, highest ticket size but Recency is quite high. Potentially deal a long-term contract selling, delivery at their place and cross-selling for another potential products.

5. Evaluate K-means Model with Logistic Regression model 

![0*goBW3B8rStqWzrWZ](https://user-images.githubusercontent.com/69904258/144893860-2605f965-614d-4d26-9860-bf4ff655f20a.png)

[Logistic Regression model ](https://medium.com/data-science-group-iitr/logistic-regression-simplified-9b4efe801389)
It’s a classification algorithm, that is used where the response variable is categorical. The idea of Logistic Regression is to find a relationship between features and probability of particular outcome.
 
### Accuracy of Model
<img width="506" alt="Screen Shot 2564-12-07 at 00 34 32" src="https://user-images.githubusercontent.com/69904258/144894055-b4d61f0d-1db7-4095-8e22-fe1571153aac.png">

### Confusion Matrix
<img width="592" alt="Screen Shot 2564-12-07 at 00 35 45" src="https://user-images.githubusercontent.com/69904258/144894151-05f8280e-fe14-4328-8999-d9c375091eb0.png">

### Feature important of Model
<img width="933" alt="Screen Shot 2564-12-07 at 00 37 02" src="https://user-images.githubusercontent.com/69904258/144894325-4e133d6e-edac-4a51-9d5e-d58cc762d607.png">

### Class Report of Model
<img width="538" alt="Screen Shot 2564-12-07 at 00 38 05" src="https://user-images.githubusercontent.com/69904258/144894478-38e7a934-de54-4fdb-8b5e-0b32b3efd4a0.png">

* As the results, K-means model in clustering is suitable model for customer segmentation.













