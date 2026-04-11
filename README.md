# Grocery Receipt Lifestyle Clustering

##  Overview

This project explores customer shopping behavior using grocery order data. Instead of treating all customers the same, we try to **group users into meaningful lifestyle segments** based on how they shop — how often they order, what they buy, and their shopping patterns.

The goal is simple:
 To Understand *different types of shoppers* using data.

---

## Dataset

The project uses multiple CSV files containing:

* Orders data (when users placed orders)
* Product-level purchase details
* Product categories (aisles & departments)

These datasets are merged to create a **complete view of user behavior**.

---

## Workflow

### 1. Data Loading & Merging

We combine multiple datasets into one unified dataframe so each row reflects:

* User
* Order details
* Product information

---

### 2. Data Cleaning

* Missing values handled (e.g., `days_since_prior_order`)
* Filtered out inactive users
 Only users with **at least 5 orders** are considered to ensure meaningful patterns

---

### 3. Exploratory Data Analysis (EDA)

We analyze:

* Order timings (hour of day, day of week)
* Shopping frequency
* General behavior trends

This step helps confirm that **users actually behave differently**, which makes clustering useful.

---

### 4. Feature Engineering (Core of the Project)

We create **16 behavioral features per user**, including:

* Total number of orders
* Average order time
* Shopping frequency
* Basket size
* Diversity of products
* Reordering behavior

These features represent each user numerically.

---

### 5. Feature Scaling

We standardize the features so that:

* No single feature dominates due to scale
* All features contribute fairly to clustering

---

### 6. Dimensionality Reduction (UMAP)

We reduce data from **16 dimensions → 2 dimensions** using UMAP.

Why?

* Makes clustering easier
* Helps visualize user groups

---

### 7. Clustering (HDBSCAN)

We use HDBSCAN because:

* It automatically finds the number of clusters
* Handles noise (outliers) well
* Works great with complex, real-world data

Output:

* Each user is assigned a cluster
* Some users may be labeled as noise (-1)

---

### 8. Visualization

* Scatter plot of clusters (in 2D space)
* Heatmaps to understand cluster characteristics

---

### 9. Cluster Interpretation

Each cluster is labeled based on behavior patterns, for example:

* **Power Shoppers** → frequent orders, large baskets
* **Weekly Routine Shoppers** → consistent weekly behavior
* **Rare Explorers** → infrequent but varied purchases

These labels make results easy to understand and actionable.

---

### 10. Evaluation

We use **Silhouette Score** to measure clustering quality:

* Higher score = better separation between clusters

---

## Key Insights

* Customers have **distinct shopping lifestyles**
* Not all users behave uniformly
* Behavioral clustering can help in:

  * Personalized recommendations
  * Marketing strategies
  * Inventory planning

---

## Tech Stack

* Python
* Pandas, NumPy
* Matplotlib, Seaborn
* Scikit-learn
* UMAP
* HDBSCAN

---

## Conclusion

This project shows how raw transaction data can be transformed into **meaningful customer segments**.

Instead of guessing customer behavior, we let the data reveal patterns — leading to smarter, data-driven decisions.

---

## Future Improvements

* Add more behavioral features
* Try different clustering methods (K-Means, DBSCAN)
* Deploy as a recommendation system
* Integrate real-time data

---

## Final Note

This is not just a clustering project — it's about **understanding human behavior through data**.
