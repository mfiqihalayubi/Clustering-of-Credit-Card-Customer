![img](https://miro.medium.com/v2/resize:fit:828/format:webp/0*roEnqE5qSiUbTJkp.jpg)

<center>

<h1>Credit Card Customer Segmentation (Clustering)</h1>

---

</center>

<br />
<br />

## **Objective**
Create a machine learning model that can perform credit card customer clustering.

## **About the dataset**

This data is credit card usage information data for the last 6 months.

## **Conclusion**

1. The information retained in the feature dimension reduction is 95% with the final number of dimensions are 10. The decision to retain 95% of the information is based on the reason that the clustering results can represent the data as actual as possible and not eliminate information from features that have extreme values. As we know in the outliers handling process, 13 of the 17 features have an outlier percentage above 8%. To anticipate if at some point the model has to make predictions on a dataset that has many outliers, I decided to retain 95% of the information so that the model gets used to handling datasets like this
2. Based on the elbow and silhouette scoring methods, the chosen optimal K value is 6. Based on the elbow method, the value 6 is chosen because the decrease in inertia is not too significant or the slope is not too steep when the number of clusters is changed from 6 to 7. Based on the silhouette score method, the value of K = 6 is chosen because this value provides the most balanced datapoint distribution compared to other K values. In addition, the average silhouette score value is not too small compared to the score values ​​of other K values
3. Based on the sillhouette score test, all trialed K values produce an average score below 0.4. This indicates that the clustering process is not optimal because a small average score value means that the data point does not really fit into its own cluster. Most likely the reason why all the score values obtained are small is because there are a large number of outliers. Outliers have a distance to neighboring data points (1 cluster) that is far enough so that the divisor in the silhouette score formula will be relatively large. As a result, the average silhouette score value will be smaller.
4. From the clustering results, the population of each cluster is obtained as follows:
  A. Cluster 1: 1795 people (41.6%)
  B. Cluster 2: 560 people (13%)
  C. Cluster 3: 269 people (6.2%)  
  D. Cluster 4 : 567 people (13.61%)
  E. Cluster 5 : 469 people (10.9%)
  F. Cluster 6 : 660 people (15.3%)
5. Here is the profile of the 6 clusters :
   
  A. Cluster 1
  - Has the largest number of customers (41.6%) 
  - The average cash advance value is classified as moderate (375.16) with an average cash advance transaction that is relatively small (2 times/customer) 
  - Has a very high   risk of default with an average value of percent of full payment of 2% and more than 75% of its customers have a percent of full payment value below 20% in the past 6 months
  - Quite active in making transactions    with an average transaction of 8 times/customer and an average nominal value transacted of 429.3/customer Tenure range 10 - 12 months

  B. Cluster 2
  - Has 13% of the total number of customers
  - The average cash advance value is classified as quite large (419.68) with an average number of cash advance transactions that are relatively small (1 time/customer)
  - Has a fairly high risk of default large with an average percent of full payment of 23% in the last 6 months
  - Not very active in making purchases using credit cards with an average transaction of 5 times/customer and an average nominal transaction of 383.9/customer
  - 75% of customers have a tenure range of 11 - 12 months

  C. Cluster 3
  - Has 6.2% of customers from the total number of customers
  - The average cash advance value is relatively large (1249.94/customer) with an average number of cash advance transactions that are relatively small (3 times/customer)
  - Has a high risk of default with an average percent of full payment of 15% in the last 6 months
  - Not very active in making purchases using credit cards with an average transaction is 5 times/customer and an average nominal transaction is 399.9/customer
  - 75% of customers have a tenure range of 6 - 8 months

  D. Cluster 4
  - Has customers as much as 13.1% of the total customers
  - The average cash advance value is classified as moderate (714.71) with an average number of cash advance transactions that are relatively small (2 times/customer)
  - Has a fairly large risk of default with an average percent of full payment of 15% in the last 6 months
  - Cluster with the most active customers in making purchases using credit cards with an average transaction is 58 times/customer
  - Has the highest average purchase value (4578.03/customer) with the widest purchase value range (0 - 22000)
  - 75% of customers have a tenure range of 11 - 12 months

  E. Cluster 5
  - Has 10.9% of customers from the total customers
  - The average cash advance value is very small (42.9/customer) with an average number of cash advance transactions approaching 0/customer
  - Has a very small risk of default with an average percent of full payment is 68% in the last 6 months
  - Cluster with customers who are quite active in making purchases using credit cards with an average transaction is 19 times/customer and an average nominal transaction is 1076.18/customer
  - 75% of customers have a tenure range 9 - 12 months

  F. Cluster 6
  - Has 15.3% of customers from the total number of customers
  - Cluster with the largest average cash advance value (42024/customer) with an average number of cash advance transactions of 13 times/customer
  - Cluster with the highest risk of default with an average percent of full payment is 2% in the last 6 months
  - Cluster with customers who are not very active in making purchases using credit cards with an average transaction is 7 times/customer and an average nominal transaction is 359.19/customer
  - 75% of customers have a tenure range 11 - 12 months

## **Business Recommendation**

1. Increase the amount of FAQ data to improve the model's ability to answer specific questions related to administrative aspects.    
2. We would recommended to use stream processing methods to handle the data of cars sold on the platform so that the model can always receive updated data in real-time.

## **Room for Improvement**

1. Adding more features to the car dataset, such as user reviews, ratings, and historical sales data, can help the model provide more accurate and relevant recommendations.
2. Implementing deeper contextual understanding techniques, such as using transformer-based models like BERT.
3. Applying a feedback loop mechanism where users can provide direct feedback on the chatbot's answer quality, which can be used to continuously train and refine the model.

### [**Dataset**](https://www.kaggle.com/datasets/indraputra21/used-car-listings-in-indonesia?select=used_car.csv)
### [**Deployment Demo**](https://drive.google.com/file/d/18srgZGhkPxruex62RCXlwg3URjR7Puq8/view?usp=sharing)
### [**Tableau**](https://public.tableau.com/app/profile/ahmad.dani.rifai/viz/CarListing_17223143129200/Dashboard1?publish=yes)
### [**Hugging Face**](https://huggingface.co/spaces/vickybelario/project01)
