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

### 3. Regression
- **Linear Regression**
  - Target: `box_office_revenue`
  - Features: `production_budget`, `imdb_rating`, `duration_minutes`
- **Logistic Regression**
  - Target: High-rated (IMDb ≥ 7) vs Low-rated
  - Features: `production_budget`, `duration_minutes`

### 4. Results & Insights
- Key findings from EDA
- Clustering interpretation (e.g., blockbusters vs indie films)
- Regression coefficients and implications
