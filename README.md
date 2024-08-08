![img](https://www.google.com/url?sa=i&url=https%3A%2F%2Fgordonkwokch.medium.com%2Fexploring-customer-behavior-a-data-analysis-of-credit-card-dataset-aa3d407a079d&psig=AOvVaw00vfAAriniZSBNiZS8rvfM&ust=1723189239983000&source=images&cd=vfe&opi=89978449&ved=0CBEQjRxqFwoTCOjU8Kzy5IcDFQAAAAAdAAAAABAE)

<center>

<h1>AutoBuddy</h1>

### **Credit Card Customer Segmentation (Clustering)**

---

</center>

<br />
<br />

## **Objective**
Create a machine learning model that can perform credit card customer clustering.

## **About the dataset**

This data is credit card usage information data for the last 6 months.

## **Conclusion**

1. The information retained in the feature dimension reduction is 95% with the final number of dimensions being 10. The decision to retain 95% of the information is based on the reason that the clustering results can represent the data as actual as possible and not eliminate information from features that have extreme values. As we know in the outliers handling process, 13 of the 17 features have an outlier percentage above 8%. To anticipate if at some point the model has to make predictions on a dataset that has many outliers, I decided to retain 95% of the information so that the model gets used to handling datasets like this.

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
