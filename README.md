
# CryptoClustering
* In this challenge,Python and unsupervised learning is used to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.
* In the provided data each row represents one cryptocurrency.
 ![1](https://github.com/karurathi2010/CryptoClustering/assets/53624041/2fcd7b69-4beb-4c32-8cca-06ab927acd42)

* Loaded the provided data into a Pandas DataFrame as 'df_market_data'.
*  Used the 'StandardScaler()' module from scikit-learn to normalize the data from the CSV file.
*  ![2](https://github.com/karurathi2010/CryptoClustering/assets/53624041/c120b310-b24d-40ba-979b-378df28684eb)

*  For finding the best valye for 'k', created a list with the number of k-values from 1 to 11.
*  Using for loop to computed the inertia with each possible value of k,and stored the values in a list as 'inertia'.
*  Created a DataFrame with the 'k' and 'inertia' values and named it as 'elbow_df'.
*  Using elbow_df ploted the line graph,and picked the best value as 4.

 ![image](https://github.com/karurathi2010/CryptoClustering/assets/53624041/716f4541-c370-420b-b91c-a9251e419362)

*  Initialized the K-Means model using the best value for k from the plot.
*  Predicted the clusters to group the cryptocurrencies using the scaled data.
*  Added a new column to the scaled DataFrame with the predicted clusters.
*   Created a scatter plot using hvPlot by setting x value as "price_change_percentage_24h" and y value as "price_change_percentage_7d".
*  ![image](https://github.com/karurathi2010/CryptoClustering/assets/53624041/9b256dda-7dcd-4b0a-9b39-caaa76b2f7e8)

*   Next,optimized the clusters using Principal Component Analysis.
*   Created a PCA model instance and set 'n_components=3'.
*   Used the PCA model with 'fit_transform' to reduce to three principal components.
*   Created a new DataFrame with the PCA data as 'df_market_data_pca'and set the 'coinid' column as index.
*   To find the best value for 'k' using the PCA data,followed the same procedure mentioned above.
*   From the elbow curve the best value for 'k' is chosen as 4.

  ![image](https://github.com/karurathi2010/CryptoClustering/assets/53624041/27130d84-2384-479c-939a-06c040253ea5)


*   Using this 'k' value,initialized the K-Means model for PCA data and predicted the clusters to group the cryptocurrencies.
*   Added a new column to the pca dataframe with the predicted clusters.
*   Created a scatter plot using hvPlot by setting x="PC1" and y="PC2".

   ![image](https://github.com/karurathi2010/CryptoClustering/assets/53624041/d33326ae-7e74-4b93-b9c7-4ea25dc4d7f6)


*   For comparing the cluster and pca methods a composite plot is created.
  
![image](https://github.com/karurathi2010/CryptoClustering/assets/53624041/9b302e70-ceb5-4a0f-a073-5a8145bd1b7f)

Using this plot a comparison report is generated with the following conclusions:

Here in the Original_Scatter_plot(with more features) the points are loosely packed.It indicates that with more features, K-Means tend to create clusters that are less compact and more spread out. This could be due to the higher dimensionality leading to more complex data relationships that K-Means struggle to fully capture without clear feature relevance. But in the case of PCA-Scatter_Plot, the points are more closely packed and some are even overlapping. It indicates that PCA reduces the dimensionality while retaining most of the data variance, which can lead to more distinct clusters when using K-Means. So, we can conclude that using fewer features results in better-defined clusters with K-Means. The closer packing and potential overlap of points indicate that K-Means can more effectively partition the data into distinct clusters when the dimensionality is reduced.



  


