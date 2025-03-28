# Movie Recommendation System

## Project Overview

This repository contains the implementation of a **Movie Recommendation System** aimed at enhancing content streaming services. The project leverages machine learning models trained on the **MovieLens** dataset to provide personalized movie recommendations based on user reviews.

## Dataset

The system utilizes two datasets from **MovieLens**:

1. **Small Dataset** (100k reviews)

   - 600 users
   - 9000 movies
   - Reviews span from 1995 - 2023
   - Each review contains:
     - An anonymized user ID
     - A movie ID
     - A rating on a 5-star scale (half-star increments)

2. **Large Dataset** (33M reviews)

   - 330,975 users
   - 86,537 movies

## Models and Methodologies

### **Model 1: Small Dataset (100k Reviews)**

#### **Baseline Model**

- Algorithm: **Singular Value Decomposition (SVD)** using `surprise` library.
- Parameters: Default
- Performance Metrics:
  - RMSE: **0.88**
  - FCP: **0.65**

#### **Hyperparameter Tuning**

- Optimized Parameters:
  - `n_factors`: 200
  - `n_epochs`: 150
  - `regParam`: 0.1
- Performance Improvement:
  - RMSE: **0.85**
  - FCP: **0.68**

#### **Visualization**

- **t-SNE Clustering** to visualize movies with similar rating patterns.

### **Model 2: Large Dataset (33M Reviews)**

#### **Processing & Training**

- Tools: **Databricks, PySpark**

#### **Baseline Model**

- Algorithm: **Alternating Least Squares (ALS)**
- Parameters: Default
- Performance Metrics:
  - RMSE: **3.5**

#### **Hyperparameter Tuning**

- Performed cross-validation on a small subset to determine optimal parameters:
  - `alpha`: 0.5
  - `maxIter`: 10
  - `rank`: 15
  - `regParam`: 0.3
- **Final Model Performance**
  - RMSE: **0.91**
  - FCP: **0.55**

## Next Steps

- Further **hyperparameter tuning** to improve the **FCP** score for the large dataset.
- Investigate and analyze **clustering patterns** in the data.
