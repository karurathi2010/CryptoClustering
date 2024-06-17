# CryptoClustering
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
 ![3](https://github.com/karurathi2010/CryptoClustering/assets/53624041/955563ab-a877-4ad4-9be3-3d78b87d73c1)
 
*  Initialized the K-Means model using the best value for k from the plot.
*  Predicted the clusters to group the cryptocurrencies using the scaled data.
*  Added a new column to the scaled DataFrame with the predicted clusters.
*   Created a scatter plot using hvPlot by setting x value as "price_change_percentage_24h" and y value as "price_change_percentage_7d".
*   ![4](https://github.com/karurathi2010/CryptoClustering/assets/53624041/8514b57e-c50a-4ef8-a3b0-8fdd4d3f283c)

*   Next,optimized the clusters using Principal Component Analysis.
*   Created a PCA model instance and set 'n_components=3'.
*   Used the PCA model with 'fit_transform' to reduce to three principal components.
*   Created a new DataFrame with the PCA data as 'df_market_data_pca'and set the 'coinid' column as index.
*   To find the best value for 'k' using the PCA data,followed the same procedure mentioned above.
*   From the elbow curve the best value for 'k' is chosen as 4.

  ![5](https://github.com/karurathi2010/CryptoClustering/assets/53624041/85def8ee-1555-40bb-a645-3362efa3b113)

*   Using this 'k' value,initialized the K-Means model for PCA data and predicted the clusters to group the cryptocurrencies.
*   Added a new column to the pca dataframe with the predicted clusters.
*   Created a scatter plot using hvPlot by setting x="PC1" and y="PC2".

    ![6](https://github.com/karurathi2010/CryptoClustering/assets/53624041/6404f3cd-2e1e-4252-bf4c-55fed70b1bef)

*   For comparing the cluster and pca methods a composite plot is created.
  


  


