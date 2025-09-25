## 🕒 Project Plan (3-Hour MVP)

### 1. Exploratory Data Analysis (EDA)
- **Movies.csv**
  - Distribution of IMDb ratings
  - Scatter plot of Budget vs Revenue
  - Genre distribution
- **Users.csv**
  - Age distribution (remove outliers >100)
  - Subscription plan counts
  - Monthly spend distribution (check anomalies >200)

Key insights from Movies and Users data:
- Most movies have IMDb ratings between 5–8.
- Higher budgets generally lead to higher revenues, but with exceptions (low-budget high-revenue films).
- Adventure, War, and Action are the most common genres.
- User base is concentrated in the 20–40 age range.
- Standard and Premium are the most popular subscription plans.
- Most users spend $10–20 monthly, with a few high-value outliers.

#### Visualization Results
![EDA Results](https://github.com/tc3474-png/netflix-analytics-project/blob/main/images/eda_overview.png?raw=true)

### 2. Clustering (KMeans)
- Features: `imdb_rating`, `duration_minutes`, (`budget`, `revenue` where available)
- Apply KMeans (choose optimal K via elbow method)
- Visualize clusters with PCA scatter plot
### Clustering (KMeans)

We clustered movies using `imdb_rating`, `duration_minutes`, `production_budget`, and `box_office_revenue`.
After preprocessing (median imputation, log transform, scaling), KMeans suggested **K=2–3 clusters**.

#### Results
- **Elbow Method:** Optimal K ≈ 3  
- **Silhouette Score:** Best K ≈ 2  
- **Interpretation:**
  - Cluster 0 — Blockbusters (high budget, high revenue)
  - Cluster 1 — Low budget / low revenue
  - Cluster 2 — Mid-tier or indie films

#### Visualizations
Elbow curve:  
![Elbow Method](https://github.com/tc3474-png/netflix-analytics-project/blob/main/images/kmeans_elbow.png?raw=true)

Silhouette score:  
![Silhouette Score](https://github.com/tc3474-png/netflix-analytics-project/blob/main/images/kmeans_silhouette.png?raw=true)

Cluster visualization (PCA projection):  
![KMeans Clusters](https://github.com/tc3474-png/netflix-analytics-project/blob/main/images/kmeans_clusters.png?raw=true)

### 3. Regression
- **Linear Regression**
  - Target: `box_office_revenue`
  - Features: `production_budget`, `imdb_rating`, `duration_minutes`
- **Logistic Regression**
  - Target: High-rated (IMDb ≥ 7) vs Low-rated
  - Features: `production_budget`, `duration_minutes`
  ### Regression Results

**Linear Regression (predict revenue)**  
- Target: `box_office_revenue` (log)  
- Features: `production_budget_log`, `imdb_rating`, `duration_minutes`  
- Metrics: RMSE (USD), R² (log target)

Predicted vs Actual (USD):  
![LinReg Pred vs Actual](https://github.com/tc3474-png/netflix-analytics-project/blob/main/images/linreg_pred_vs_actual.png?raw=true)

Residuals (log space):  
![LinReg Residuals](https://github.com/tc3474-png/netflix-analytics-project/blob/main/images/linreg_residuals_hist.png?raw=true)

Standardized coefficients:  
![LinReg Coefs](https://github.com/tc3474-png/netflix-analytics-project/blob/main/images/linreg_coefficients.png?raw=true)

**Logistic Regression (high-rated? IMDb ≥ 7)**  
- Features: `production_budget_log`, `duration_minutes`  
- Metrics: precision, recall, F1, ROC-AUC, Average Precision

ROC Curve:  
![ROC](https://github.com/tc3474-png/netflix-analytics-project/blob/main/images/logreg_roc.png?raw=true)

Precision-Recall Curve:  
![PR](https://github.com/tc3474-png/netflix-analytics-project/blob/main/images/logreg_pr.png?raw=true)

Coefficients:  
![LogReg Coefs](https://github.com/tc3474-png/netflix-analytics-project/blob/main/images/logreg_coefficients.png?raw=true)

### 4. Results & Insights
- Key findings from EDA
- Clustering interpretation (e.g., blockbusters vs indie films)
- Regression coefficients and implications
