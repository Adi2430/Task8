# Task8

Step 1: Load Libraries and Dataset
In the first step, I imported the necessary libraries to work with data and perform K-Means clustering:
Pandas for loading and manipulating the dataset.
Matplotlib for plotting visualizations.
KMeans from Scikit-learn for clustering the data.
Silhouette Score for evaluating the clustering results.
LabelEncoder from Scikit-learn to encode the categorical Gender feature into numerical values.
PCA (Principal Component Analysis) for optional dimensionality reduction and better visualization.
I then loaded the dataset using pd.read_csv(), displayed the first few rows with head(), and printed the column names to get an understanding of the dataset structure.

Step 2: Preprocess the Data
Next, I performed some preprocessing steps on the dataset:
I dropped the CustomerID column because it was not useful for the clustering task. The CustomerID is an identifier and doesn’t contribute to identifying patterns or clusters.
I used Label Encoding to convert the categorical Gender column into numerical values (Male = 1, Female = 0), as machine learning algorithms like K-Means require numerical input for processing.
After these transformations, I printed the cleaned dataset to ensure everything was correctly preprocessed and ready for clustering.

Step 3: Elbow Method to Find Optimal K
To determine the optimal number of clusters (K) for the K-Means algorithm, I used the Elbow Method:
I calculated the Sum of Squared Errors (SSE), also known as inertia, for different values of K (from 1 to 10).
The KMeans model was fitted on the dataset using each value of K, and I plotted the SSE against K to visually identify the "elbow point."
The "elbow" on the graph indicates the point where increasing K further doesn’t significantly improve the SSE. This helped me select an appropriate number of clusters.

Step 4: Fit KMeans with Optimal K
After identifying the optimal K using the elbow method, I fitted the K-Means algorithm with that number of clusters (in this case, I assumed K=5 based on the elbow plot):
I used KMeans(n_clusters=5) and applied it to the data with features Annual Income (k$) and Spending Score (1-100).
The fit_predict() method of the KMeans model was used to perform clustering and assign a cluster label to each data point.
I then added the cluster labels as a new column, Cluster, to the dataset for further analysis.

Step 5: Visualize Clusters (2D Plot)
Once the clustering was performed, I visualized the clusters in a 2D scatter plot to better understand how the data was segmented:
The Annual Income (k$) and Spending Score (1-100) were plotted on the x and y axes, respectively.
Each data point was color-coded according to its assigned cluster.
I also added the cluster centroids (the central points of each cluster) using red "X" markers to visually show where the centers of the clusters are located.
This step helped to see how well the algorithm grouped the customers into distinct segments based on income and spending score.

Step 6: Evaluate Clustering Using Silhouette Score
To evaluate how well the clustering performed, I calculated the Silhouette Score:
The Silhouette Score provides a measure of how similar data points are to their own cluster compared to other clusters.
A higher Silhouette Score indicates that the clusters are well-separated, and the data points are appropriately grouped.
I used the silhouette_score() function to compute this value and printed it to assess the quality of the clustering.

Step 7: Reduce Dimensions with PCA (for Visualization)
Finally, I performed PCA (Principal Component Analysis) as an optional step to reduce the dimensionality of the data for better visualization:
PCA is typically used to reduce high-dimensional data into two or three dimensions, making it easier to visualize.
In this case, I used PCA to reduce the two features (Annual Income (k$) and Spending Score (1-100)) to 2 principal components.
The reduced data was plotted in a scatter plot, with clusters color-coded, giving a clearer visual of how the data points are grouped.

