![img](https://miro.medium.com/v2/resize:fit:828/format:webp/0*roEnqE5qSiUbTJkp.jpg)

<center>

<h1>Credit Card Customer Segmentation (Clustering)</h1>

---

</center>

<br />
<br />

## **Background**
Understanding customer behavior is a basic obligation for a business entity, including credit card companies. Understanding customer behavior in the credit card business can result in more effective marketing activities, product development that is more in line with market conditions, and minimize the risk of payment failure. Understanding customer behavior can be achieved by segmenting customers based on their characteristics while using credit cards. Segmentation can be done by clustering process using machine learning model.

## **Objective**
Create a machine learning model that can perform credit card customer segmentation.

## **About the dataset**

I took the dataset from Google Cloud BigQuery. This dataset contains 4475 entries of customer historical credit card usage.

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
   
  - Cluster 1
    1. Has the largest number of customers (41.6%) 
    2. The average cash advance value is classified as moderate (375.16) with an average cash advance transaction that is relatively small (2 times/customer) 
    3. Has a very high   risk of default with an average value of percent of full payment of 2% and more than 75% of its customers have a percent of full payment value below 20% in the past 6 months
    4. Quite active in making transactions    with an average transaction of 8 times/customer and an average nominal value transacted of 429.3/customer Tenure range 10 - 12 months

  - Cluster 2
    1. Has 13% of the total number of customers
    2. The average cash advance value is classified as quite large (419.68) with an average number of cash advance transactions that are relatively small (1 time/customer)
    3. Has a fairly high risk of default large with an average percent of full payment of 23% in the last 6 months
    4. Not very active in making purchases using credit cards with an average transaction of 5 times/customer and an average nominal transaction of 383.9/customer
    5. 75% of customers have a tenure range of 11 - 12 months

  - Cluster 3
    1. Has 6.2% of customers from the total number of customers
    2. The average cash advance value is relatively large (1249.94/customer) with an average number of cash advance transactions that are relatively small (3 times/customer)
    3. Has a high risk of default with an average percent of full payment of 15% in the last 6 months
    4. Not very active in making purchases using credit cards with an average transaction is 5 times/customer and an average nominal transaction is 399.9/customer
    5. 75% of customers have a tenure range of 6 - 8 months

  - Cluster 4
    1. Has customers as much as 13.1% of the total customers
    2. The average cash advance value is classified as moderate (714.71) with an average number of cash advance transactions that are relatively small (2 times/customer)
    3. Has a fairly large risk of default with an average percent of full payment of 15% in the last 6 months
    4. Cluster with the most active customers in making purchases using credit cards with an average transaction is 58 times/customer
    5. Has the highest average purchase value (4578.03/customer) with the widest purchase value range (0 - 22000)
    6. 75% of customers have a tenure range of 11 - 12 months

  - Cluster 5
    1. Has 10.9% of customers from the total customers
    2. The average cash advance value is very small (42.9/customer) with an average number of cash advance transactions approaching 0/customer
    3. Has a very small risk of default with an average percent of full payment is 68% in the last 6 months
    4. Cluster with customers who are quite active in making purchases using credit cards with an average transaction is 19 times/customer and an average nominal transaction is 1076.18/customer
    5. 75% of customers have a tenure range 9 - 12 months

  - Cluster 6
    1. Has 15.3% of customers from the total number of customers
    2. Cluster with the largest average cash advance value (42024/customer) with an average number of cash advance transactions of 13 times/customer
    3. Cluster with the highest risk of default with an average percent of full payment is 2% in the last 6 months
    4. Cluster with customers who are not very active in making purchases using credit cards with an average transaction is 7 times/customer and an average nominal transaction is 359.19/customer
    5. 75% of customers have a tenure range 11 - 12 months

## **Business Recommendation**

1. Give penalties to customers from clusters that have an average percent of full payment value <40%. The goal is to reduce the number of customers who have a high risk of default. Penalties can be done by increasing late fees, reducing tenure for subsequent credit transactions, or reducing cash advance limits. By doing this, it is hoped that credit card holders will become more responsible in making bill payments  
2. Promotion of credit card and cash advance services needs to be improved and intensified to customers from cluster 5 because these customers have the highest percent of full payment, large average purchase value, and have the lowest average number of cash advance transactions (almost 0)
3. Reduce the credit limit on customers from cluster 6 because the average percent of full payment is very low (2% in 6 months). The main problem is that, in addition to the low average percent of payment, the majority of customers from this cluster use a risky credit service called cash advance where the company does not have the ability to know what the money is used for and when it will be returned

## **Room for Improvement**

1. Removing outliers as one of the trial options in choosing the optimal K value
2. Increase max iteration to ensure the model converges in determining the centroid
3. Try clustering models that are more robust to outliers such as DBSCAN or K-Medoids
