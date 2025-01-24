# CryptoClustering

## Necessary Tools

To complete this project, ensure you have the following tools and libraries installed and set up in your environment:

1. **Python 3.7+**: Ensure you have Python installed. You can download it from [python.org](https://www.python.org/).
2. **Jupyter Notebook**: For running the provided `.ipynb` file interactively.
   - Install it via pip: `pip install notebook`
3. **Pandas**: For data manipulation and analysis.
   - Install it via pip: `pip install pandas`
4. **scikit-learn**: For clustering (K-means), normalization (StandardScaler), and PCA.
   - Install it via pip: `pip install scikit-learn`
5. **hvPlot**: For interactive visualizations and scatter plots.
   - Install it via pip: `pip install hvplot`
6. **Matplotlib**: For creating line charts for the Elbow curve.
   - Install it via pip: `pip install matplotlib`
7. **NumPy**: For numerical computations.
   - Install it via pip: `pip install numpy`
8. **Anaconda Environment (Optional)**: To create a virtual environment for managing dependencies. You can download it from [Anaconda](https://www.anaconda.com/).

### Setting Up Your Environment
1. Clone this repository to your local machine:
   ```bash
   git clone <repository_url>
   cd CryptoClustering

## Prepare the Data

1. Use the `StandardScaler()` module from scikit-learn to normalize the data from the CSV file.

2. Create a DataFrame with the scaled data.

3. Set the `coin_id` index from the original DataFrame as the index for the new scaled DataFrame.

## Find the Best Value for k Using the Scaled DataFrame

Use the elbow method to determine the best value for `k` by following these steps:

1. Create a list with the number of `k` values from 1 to 11.
2. Create an empty list to store the inertia values.
3. Create a for loop to compute the inertia for each possible value of `k`.
4. Create a dictionary with the data to plot the elbow curve.
5. Plot a line chart with all the inertia values computed with the different values of `k` to visually identify the optimal value for `k`.
6. Answer the following question in your notebook: **What is the best value for k?**

## Cluster Cryptocurrencies with K-means Using the Scaled DataFrame

Follow these steps to cluster the cryptocurrencies for the best value of `k` using the scaled DataFrame:

1. Initialize the K-means model with the best value for `k`.
2. Fit the K-means model using the scaled DataFrame.
3. Predict the clusters to group the cryptocurrencies using the scaled DataFrame.
4. Create a copy of the scaled DataFrame and add a new column with the predicted clusters.
5. Create a scatter plot using `hvPlot` as follows:
   - Set the x-axis to `"price_change_percentage_24h"` and the y-axis to `"price_change_percentage_7d"`.
   - Color the graph points based on the cluster labels found using K-means.
   - Add the `"coin_id"` column in the `hover_cols` parameter to identify the cryptocurrency represented by each data point.
  
## Optimize Clusters with Principal Component Analysis

Follow these steps to optimize the clusters using Principal Component Analysis (PCA):

1. Using the original scaled DataFrame, perform PCA to reduce the features to three principal components.
2. Retrieve the explained variance to determine how much information can be attributed to each principal component.
3. Answer the following question in your notebook: **What is the total explained variance of the three principal components?**
4. Create a new DataFrame with the scaled PCA data and set the `coin_id` index from the original DataFrame as the index for the new DataFrame.

## Find the Best Value for k Using the PCA DataFrame

Use the elbow method on the scaled PCA DataFrame to find the best value for `k` by following these steps:

1. Create a list with the number of `k` values from 1 to 11.
2. Create an empty list to store the inertia values.
3. Create a for loop to compute the inertia for each possible value of `k`.
4. Create a dictionary with the data to plot the Elbow curve.
5. Plot a line chart with a

## Cluster Cryptocurrencies with K-means Using the PCA DataFrame

Follow these steps to cluster the cryptocurrencies for the best value of `k` using the PCA DataFrame:

1. Initialize the K-means model with the best value for `k`.
2. Fit the K-means model using the scaled PCA DataFrame.
3. Predict the clusters to group the cryptocurrencies using the scaled PCA DataFrame.
4. Create a copy of the scaled PCA DataFrame and add a new column to store the predicted clusters.
5. Create a scatter plot using `hvPlot` as follows:
   - Set the x-axis to `"PC1"` and the y-axis to `"PC2"`.
   - Color the graph points based on the cluster labels found using K-means.
   - Add the `"coin_id"` column in the `hover_cols` parameter to identify the cryptocurrency represented by each data point.
6. Answer the following question in your notebook:
   - **What is the impact of using fewer features to cluster the data using K-Means?**
