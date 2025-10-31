
# Mall Customer Segmentation

### An End-to-End K-Means Clustering Project

This mini-project is a data science workflow for unsupervised learning. The goal is to analyze the "Mall Customers" dataset to identify hidden segments, or clusters, of customers.

The final analysis successfully identifies 5 distinct customer personas, which a mall's marketing team could use to create targeted advertising campaigns.

## Final Result: The 5 Customer Segments

The K-Means algorithm (with K=5) successfully identified 5 distinct, data-driven clusters based on customer income and spending habits.

![Final Cluster Visualization](cluster_plot.png)


---

## Project Workflow

This project followed a 5-step unsupervised learning pipeline:

1.  **Data Loading & EDA (Exploratory Data Analysis):**
    * Loaded the `Mall_Customers.csv` dataset.
    * Inspected the data and confirmed it was 100% clean (no missing values, no duplicates).
    * Visualized the key features, discovering a clear, un-labeled pattern between `Annual Income` and `Spending Score`.

2.  **Data Preprocessing (Scaling):**
    * Since K-Means is a distance-based algorithm, the features were scaled to have the same weight.
    * Used `StandardScaler` from Scikit-learn to scale the `Annual Income` and `Spending Score` features.

3.  **Model Selection (The Elbow Method):**
    * To find the optimal number of clusters (K), the "Elbow Method" was used.
    * We ran K-Means for K=1 through K=10 and plotted the WCSS (Inertia).
    * The plot showed a clear "elbow" (point of diminishing returns) at **K=5**.

4.  **Final Model Training:**
    * The final `KMeans` model was trained on the scaled data with **n_clusters=5**.
    * The model assigned a cluster label (0-4) to each customer.

5.  **Cluster Profiling (Analysis):**
    * The cluster labels were added back to the original DataFrame.
    * A `groupby('Cluster')` analysis was performed to find the average `Age`, `Income`, and `Spending Score` for each group to build a "persona."

---

## Analysis: The 5 Customer Personas

The `groupby()` analysis revealed the following 5 distinct customer segments:


* **Cluster 0: "Standard"**
    * **Profile:** Average income (~55k), average spending (~50).
    * **Analysis:** The general, mass-market customer.

* **Cluster 1: "Target" (High Value)**
    * **Profile:** High income (~87k), high spending (~82).
    * **Analysis:** The most valuable group. Prime target for loyalty programs and premium brands.

* **Cluster 2: "Careless" (Young & Spending)**
    * **Profile:** Low income (~26k), high spending (~79).
    * **Analysis:** Young, highly responsive to sales and trends.

* **Cluster 3: "Careful" (Affluent but Frugal)**
    * **Profile:** High income (~88k), low spending (~17).
    * **Analysis:** Hard to convince. Requires marketing focused on quality and value, not impulse.

* **Cluster 4: "Sensible" (Frugal)**
    * **Profile:** Low income (~26k), low spending (~21).
    * **Analysis:** Frugal, likely only shop for necessities or heavy discounts.

---

## Technologies Used

* Python (3.12.7)
* Pandas (for data manipulation)
* Scikit-learn (for KMeans & StandardScaler)
* Matplotlib & Seaborn (for visualization)
* Jupyter Notebook

---

## How to Run This Project

1.  Clone this repository:
    ```sh
    git clone [https://github.com/](https://github.com/)mmesbahi/mall_cutomers_segmenting
.git
    ```
2.  Navigate to the project directory:
    ```sh
    cd mall_cutomers_segmenting

    ```
3.  Create and activate a virtual environment:
    ```sh
    python -m venv venv
    .\venv\Scripts\activate
    ```
4.  Install the required dependencies:
    ```sh
    pip install -r requirements.txt
    ```
5.  Launch the Jupyter Notebook:
    ```sh
    jupyter notebook clustering_notebook.ipynb
    ```
