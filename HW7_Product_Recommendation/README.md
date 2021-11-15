# Product Recommendation
### What is product recommendatio
[Product recommendation](https://medium.com/mysuperai/ai-in-action-product-recommendations-7ada226ca437) is the process of identifying products that appeal to individual users and presenting them at an opportune moment as a way of encouraging cross-selling and upselling. For most ecommerce businesses, product recommendations have now long been an integral aspect of their operations, increasing revenue and user engagement.

![1*BsVHy3WaYajZonJ12pkd0g](https://user-images.githubusercontent.com/69904258/141753185-0c308fee-609f-4a14-ae07-3b3bc19cd545.png)
# Dataset
A survey asking whether or not the student in class has ever purchased or not an item. 
# What did I do ?
* Cleaning Data
* Model
  * The Apriori algorithm
  * Collaborative Filtering - Cosine similarity algorithm
* Conclusion of recommendation product

# Cleaning Data

<img width="1420" alt="Screen Shot 2564-11-15 at 16 15 08" src="https://user-images.githubusercontent.com/69904258/141754697-6db63227-ce26-443f-8d3c-73c4e58895ef.png">

> Item Count per User

<img width="1068" alt="Screen Shot 2564-11-15 at 16 16 39" src="https://user-images.githubusercontent.com/69904258/141755021-8c999e4e-4a36-46fb-89f2-49d5856328c1.png">

> Group data by student number 

<img width="1440" alt="Screen Shot 2564-11-15 at 16 18 57" src="https://user-images.githubusercontent.com/69904258/141755356-cb73535a-ad12-493c-af61-1743a57f93dd.png">

#  [The Apriori algorithm](https://medium.com/edureka/apriori-algorithm-d7cc648d4f1e)
Apriori algorithm is a sequence of steps to be followed to find the most frequent itemset in the given database

Antecedent (IF): This is an item/group of items that are typically found in the Itemsets or Datasets.\
Consequent (THEN): This comes along as an item with an Antecedent/group of Antecedents.

![1](https://user-images.githubusercontent.com/69904258/141758638-b2e706d2-c13d-475b-9d8a-c0155d206633.jpg)


### Definition of Lift Value
Lift : Lift indicates the strength of a rule over the random occurrence of A and B. It basically tells us the strength of any rule.
### Definition of Support Value
Support : It gives the fraction of transactions which contains item A and B. Basically Support tells us about the frequently bought items or the combination of items bought frequently.
### Definition of Confidence Value
Confidence : It tells us how often the items A and B occur together, given the number times A occurs.


> Basic Association Rules

<img width="1043" alt="Screen Shot 2564-11-15 at 16 21 38" src="https://user-images.githubusercontent.com/69904258/141756565-13b6e108-92c6-4a74-874a-72b59d2a1f2a.png">

<img width="1439" alt="Screen Shot 2564-11-15 at 16 29 22" src="https://user-images.githubusercontent.com/69904258/141756858-c3c1a507-91f5-4895-b40a-2690ee3792d6.png">

# Final Association Rules
* Set antecedents = 1
* Set consequents = 1
* Set  lift >= 1
* Set support >= 0.6
* Set confidence >= 0.7

<img width="1334" alt="Screen Shot 2564-11-15 at 16 41 47" src="https://user-images.githubusercontent.com/69904258/141758779-9e5550f1-a71c-406e-bb88-2352780fe8a3.png">

<img width="1223" alt="Screen Shot 2564-11-15 at 16 48 01" src="https://user-images.githubusercontent.com/69904258/141759797-b5d12db2-017d-404d-b7bc-48e13f4066b8.png">

# [Collaborative Filtering - Cosine similarity algorithm](https://medium.com/@toprak.mhmt/collaborative-filtering-3ceb89080ade)
Collaborative filtering is based on the fact that relationships exist between products and people’s interests. Many recommendation systems use collaborative filtering to find these relationships and to give an accurate recommendation of a product that the user might like or be interested in.

* Use users' ratings for each item as its feature vector, calculates cosine similarity values for each pair of items. We could recommend items based on item similarity.

<img width="1054" alt="Screen Shot 2564-11-15 at 16 53 13" src="https://user-images.githubusercontent.com/69904258/141760621-045b9651-2822-430e-a752-9a0156dd7c8b.png">

<img width="610" alt="Screen Shot 2564-11-15 at 16 56 28" src="https://user-images.githubusercontent.com/69904258/141761071-8018a1a6-8f38-455f-936e-8551e2e01b09.png">

# Product Recomendation 


*   If customer  already buy shoes, so should recommend bluetooth earphone and Ebook.
*   If customer  already buy online course, so should recommend Ipad case and Ebook.






