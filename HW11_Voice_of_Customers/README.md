# Voice of Customers

![feedback_news_3](https://user-images.githubusercontent.com/69904258/143453127-4cba27a7-778f-4ef1-9dff-6fda2b38dfe3.png)


It is dealing with Text clustering which is a process that involves Natural Language Processing (NLP) and the use of a clustering algorithm. This method of finding groups in unstructured texts can be applied in many different segments, such as feedback analysis, research segmentation, etc.

## Dataset
Customers reviews from Wongnai 

<img width="1041" alt="Screen Shot 2564-11-25 at 20 11 10" src="https://user-images.githubusercontent.com/69904258/143447670-85941af8-5fd7-4700-958c-681f89e241ea.png">


## What did I do ?
* Use [PyThaiNLP](https://github.com/PyThaiNLP/pythainlp)
  * PyThaiNLP is a Python package for text processing and linguistic analysis, similar to NLTK with focus on Thai language.
* Document clustering using KMean
  * k = 3 
 
* Document clustering using [Agglomorative Clustering](https://medium.com/analytics-vidhya/hierarchical-clustering-agglomerative-f6906d440981) with euclidean
  * Hierarchical Clustering is separating the data into different groups from the hierarchy of clusters based on some measure of similarity.
  * Agglomerative Clustering is also known as bottom-up approach. 
In this approach we take all data points as clusters and start merging it based on the distance between clusters. This will be done until we form one big cluster.

#  Document clustering using KMean
### Step of KMean in clustering
1. Run kmeans with no. of clusters you see fit the most
2. Merge all reviews of each cluster into one big sentence 
3. Create regex compiler for removal of a character you don't want
4. Create regex compiler for removal of any emoji
5. Create regex compiler for removal of digit
6. Create regex compiler for removal of white space
7. Create regex compiler for removal of .
8. Create regex compiler for removal of \
9. Define a function to tokenize a sentence into words - you can define words you want to remove as well as new words for tokenization
10. Clean and tokenize sentences. count the occurences of each word
11. Results of tokenization
12. Show top keywords of each cluster

<img width="480" alt="Screen Shot 2564-11-25 at 20 16 55" src="https://user-images.githubusercontent.com/69904258/143451592-0a931ab9-18e9-447f-85e7-5f3796342693.png">


# Result

<img width="887" alt="Screen Shot 2564-11-25 at 20 36 59" src="https://user-images.githubusercontent.com/69904258/143451292-a6ec0441-1107-4d0c-b1e5-b048aa7d943d.png">

## Document clustering using KMeans

Use k = 3

Top_N_words = 10

Engine = multi_cut 
  * Multi cut – Thai word segmentation with maximum matching. The original source code is from Korakot Chaovavanich.


1. First group ( Bubble tea lover)
* Dealing with beverage
* Review about  beverage in type of tea and smoothie
2.  Secound group ( Restaurant )
* Dealing with Restaurant 
* Review about location , good taste and branch of restaurant
3.   Last group (Cofee lover)
* Dealing with Cofee lover
* Review about cofee shop , location and atmosphere

# Document clustering using Agglomorative Clustering

### Step of Agglomorative Clustering
Algorithm of Agglomerative Clustering
1. Make each data point as a single-point cluster. 
2. Take the two closest distance clusters by single linkage method and make them one clusters.
3. Repeat step 2 until there is only one cluster. 
4. Create a Dendrogram to visualize the history of groupings.
5. Find optimal number of clusters from Dendrogram.

# Result

<img width="804" alt="Screen Shot 2564-11-25 at 20 41 38" src="https://user-images.githubusercontent.com/69904258/143451960-04242c76-e4d4-4974-a4bf-b1a1783d6775.png">

##  Document clustering using Agglomorative Clustering

Affinity= euclidean 

Compute_full_tree = auto

Linkage = ward

n_clusters = 5


1.   First group (Cofee lover)
* Dealing with Cofee lover
* Review about cofee and taste  
2.  Secound group ( Restaurant )
* Dealing with Restaurant 
* Review about good taste and menu
3. Last group ( Bubble tea lover)
* Dealing with Bullble tea 
* Review about  beverage in type of tea 

