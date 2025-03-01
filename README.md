# **Amazon Product Recommendation System**

## **Overview**  
This project builds an **Amazon product recommendation system** using **collaborative filtering** and **matrix factorization techniques**. It utilizes **user-item interactions** from Amazon's product ratings dataset to generate personalized recommendations. The goal is to improve user experience by predicting relevant products based on past interactions.

## **Dataset**  
The dataset consists of user ratings for electronic products and contains:  
- **userId** – Unique identifier for each user  
- **productId** – Unique identifier for each product  
- **Rating** – User-provided rating for a product  
- **Timestamp** – Not used in this analysis  

To ensure computational efficiency, the dataset was filtered to include:  
- **Users who have rated at least 50 products**  
- **Products that have received at least 5 ratings**  

### **Dataset Availability**  
Since the original CSV file was too large to upload to GitHub due to size limitations, only the **first 100 rows** of the dataset have been included in this repository as a sample. If you want to work with the full dataset, please let me know, and I can share the link to the complete version via Google Drive.

## **Approach**  
The recommendation system was developed using three different techniques:  

1. **Rank-Based Recommendation** – Recommends top-rated products based on average ratings.  
2. **Collaborative Filtering** – Includes **User-User** and **Item-Item** similarity-based approaches.  
3. **Matrix Factorization (SVD)** – Uses **Singular Value Decomposition (SVD)** to capture latent user-product relationships.  

## **Technologies Used**  
- **Python**  
- **Pandas & NumPy** (Data processing)  
- **Surprise Library** (`KNNBasic`, `SVD`, `CoClustering`)  
- **Scikit-learn** (`GridSearchCV`)  
- **Matplotlib** (Data visualization)  
- **Google Colab / Jupyter Notebook**  

## **Model Evaluation Metrics**  
To assess recommendation quality, the following performance metrics were used:  
- **Precision@k** – Fraction of top-k recommended items that are relevant.  
- **Recall@k** – Fraction of relevant items successfully recommended.  
- **F1-score@k** – Harmonic mean of precision and recall.  
- **RMSE (Root Mean Squared Error)** – Measures prediction accuracy.  

## **Hyperparameter Tuning**  
To optimize model performance, **GridSearchCV** was used to tune parameters for:  
- **User-User & Item-Item Collaborative Filtering** (`KNNBasic`)  
- **Matrix Factorization** (`SVD`)  

Best hyperparameters were selected to minimize **RMSE** and improve precision and recall.

## **Results & Insights**  
- **User-User Collaborative Filtering** achieved an **F1-score of ~0.87** after tuning.  
- **Item-Item Collaborative Filtering** showed strong performance, with an **F1-score of ~0.86**.  
- **SVD-based Matrix Factorization** had the lowest **RMSE (~0.88)**, capturing latent features effectively.  
- Hyperparameter tuning significantly improved prediction accuracy compared to baseline models.  

## **How to Run the Project**  
1. **Clone this repository**:  
   ```bash
   git clone https://github.com/yourusername/amazon-recommendation-system.git
   cd amazon-recommendation-system
