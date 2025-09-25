# 🎬 Netflix-Style Dataset Analysis & Machine Learning Project

## 📌 Introduction
This project analyzes a **Netflix-style synthetic dataset** (210K+ records across 6 interconnected tables) 
designed for **data science and machine learning practice**.  
The dataset includes realistic **data quality issues** (missing values, duplicates, outliers) 
to simulate challenges faced in real-world production environments.  

**Goals of this project:**
- Perform exploratory data analysis (EDA) on users and movies.
- Apply **KMeans clustering** for segmentation.
- Build **Linear & Logistic Regression models** for prediction tasks.
- Generate actionable insights for streaming platforms.

## 📂 Dataset Overview
The dataset contains the following tables:

- **users.csv**: demographics, subscription plans  
- **movies.csv**: metadata (genres, ratings, budget, revenue)  
- **watch_history.csv**: viewing sessions  
- **recommendation_logs.csv**: recommendation system logs  
- **search_logs.csv**: user queries  
- **reviews.csv**: user reviews with sentiment labels  

👉 All tables are connected via `user_id` and `movie_id`, enabling cross-table analysis.

## 🔍 Exploratory Data Analysis (EDA)
- **Numerical variables**: `duration_minutes`, `imdb_rating`, `production_budget`, `box_office_revenue`  
- **Categorical variables**: `genre_primary`, `language`, `country_of_origin`  
- **Visualizations**: histograms, bar charts, scatter plots, box plots  

Key questions explored:
1. Does a higher budget correlate with higher revenue?
2. Which genres achieve the highest IMDb ratings?
3. What are the viewing behavior patterns of users?


## 🤖 Machine Learning Models
### 1. Clustering (KMeans)
- Input features: `imdb_rating`, `duration_minutes`, `production_budget`, `box_office_revenue`  
- Goal: Segment movies into natural groups (e.g., **blockbusters vs indie films**).

### 2. Regression
- **Linear Regression**: Predict `box_office_revenue` using `budget + imdb_rating + duration`.  
- **Logistic Regression**: Classify movies as **high-rated vs low-rated** (IMDb threshold).  


## 📊 Results & Insights
- **Budget vs Revenue**: Strong positive correlation, with some outliers (low-budget cult hits).  
- **Genres**: Documentaries often have low budgets but relatively high IMDb ratings.  
- **User Segmentation**: Clustering reveals groups such as binge-watchers vs casual viewers.  

## 🚀 Future Work
- Build a **Recommendation System** (collaborative filtering, content-based).  
- Add **NLP sentiment analysis** using `reviews.csv`.  
- Time-series forecasting of **viewing patterns**.  

## 🛠️ Tech Stack
- **Python**: pandas, numpy, scikit-learn, seaborn, matplotlib  
- **Jupyter Notebooks** for analysis  
- **GitHub** for project documentation  

## 📈 Example Visualizations
*(To be added after analysis)*  
- Revenue vs Budget scatter plot  
- KMeans cluster visualization  
- Genre distribution bar chart  

## 📜 License
This project is licensed under the **MIT License**.  
