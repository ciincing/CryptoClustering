# CryptoClustering


In this challenge, I utilized my knowledge of Python and unsupervised learning to predict whether cryptocurrencies were influenced by 24-hour or 7-day price alterations.

## Preparing Data
I prepared the data by normalizing it using the StandardScaler() module from scikit-learn based on the CSV file.
Then, I generated a DataFrame containing the scaled data and designated the "coin_id" index from the original DataFrame as the index for the new DataFrame.

## Find the Best Value for k Using the Original Scaled DataFrame
I found the best value for k using the original scaled DataFrame by employing the elbow method through these steps:
1. I created a list containing k values ranging from 1 to 11.
2. An empty list was set up to hold the inertia values.
3. Then, I executed a for loop to calculate the inertia for each potential k value.
4. A dictionary was constructed to compile data necessary for plotting the elbow curve.
5. I visualized the inertia values derived from different k values using a line chart to pinpoint the optimal k value.
6. Additionally, in my notebook, I answered the question: "What is the best value for k?"

## Cluster Cryptocurrencies with K-means Using the Original Scaled Data
I clustered the cryptocurrencies using the original scaled data with the following steps:
1. I initialized the K-means model using the best value for k.
2. The K-means model was fitted using the original scaled DataFrame.
3. I made predictions on the clusters to group the cryptocurrencies, utilizing the original scaled DataFrame.
4. Creating a duplicate of the original data, I appended a new column containing the predicted clusters.
5. To visualize the clusters, I generated a scatter plot using hvPlot with these specifications:
   - The x-axis was set as "PC1" and the y-axis as "PC2".
   - Graph points were colored based on the labels obtained from the K-means algorithm.
   - The "coin_id" column was included in the hover_cols parameter to identify each cryptocurrency represented in the data points.

## Optimize Clusters with Principal Component Analysis
I conducted a PCA on the original scaled DataFrame, reducing the features to three principal components.
Afterward, I retrieved the explained variance to gauge the information attributed to each principal component. In my notebook, I answered the question: "What is the total explained variance of the three principal components?"
Following this, I generated a new DataFrame containing the PCA data and assigned the "coin_id" index from the original DataFrame as the index for the new DataFrame.

## Cluster Cryptocurrencies with K-means Using the PCA Data
I clustered the cryptocurrencies using the PCA data with the best value for k through these steps:
1. I initialized the K-means model using the optimal k value.
2. The K-means model was trained using the PCA data.
3. Predictions were made to group the cryptocurrencies based on the PCA data.
4. I created a DataFrame copy containing the PCA data and included a new column to store the predicted clusters.
5. To visualize the clusters, I plotted a scatter graph using hvPlot with these specifications:
   - The x-axis represented "price_change_percentage_24h," and the y-axis was "price_change_percentage_7d."
   - Graph points were colored according to the K-means labels.
   - I included the "coin_id" column in the hover_cols parameter to identify each cryptocurrency in the plot.

Question: "What is the impact of using fewer features to cluster the data using K-Means?"
- Utilizing PCA data led to tighter cluster formations and increased the number of entries in both cluster 0 and cluster 1 compared to the initial analysis.
