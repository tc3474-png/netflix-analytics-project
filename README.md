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
