# Cryptocurrencies
To Complete UnSupervised Machine Learning Models from Module 18

## Project Overview
Using unsupervised learning on how to process data, how to cluster, how to reduce your dimensions, and how to reduce the principal components using PCA, 
Create an analysis for your clients who are preparing to get into the cryptocurrency market. Create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment. The data is not ideal, so it will need to be processed to fit the machine learning models. Since there is no known output , you have to use unsupervised learning. To group the cryptocurrencies, use a clustering algorithm. You  will use data visualizations to share the findings with the board.


## Resources
- jupyter notebook, python, Machine Learning Models 

## Challenge Overview
Prerequisite:
1.  Download the crypto_clustering_starter_code.ipynb 
2.  Download the data in csv crypto_data.csv for this excercise 


## Deliverable 1:  Preprocessing the Data for PCA

Follow the instructions below and use the crypto_clustering_starter_code.ipynb file to complete Deliverable 1.

1.  Open the crypto_clustering_starter_code.ipynb file, rename it crypto_clustering.ipynb, and save it to your Cryptocurrencies GitHub folder.
2.  Read in the crypto_data.csv to the Pandas DataFrame named crypto_df.
3.  Keep all the cryptocurrencies that are being traded.
4.  Drop the IsTrading column.
5.  Remove rows that have at least one null value.
6.  Filter the crypto_df DataFrame so it only has rows where coins have been mined.
7.  Create a new DataFrame that holds only the cryptocurrency names, and use the crypto_df DataFrame index as the index for this new DataFrame.
8.  Remove the CoinName column from the crypto_df DataFrame since it's not going to be used on the clustering algorithm.
9.  Use the get_dummies() method to create variables for the two text features, Algorithm and ProofType, and store the resulting data in a new DataFrame named X.
10. Use the StandardScaler fit_transform() function to standardize the features from the X DataFrame.

## Deliverable 2:  Reducing Data Dimensions Using PCA 

Follow the instructions below and use the information in the crypto_clustering_starter_code.ipynb file to complete Deliverable 2.

1.  Continue using the crypto_clustering.ipynb file from Deliverable 1 where you’ve already performed the preprocessing steps.
2.  Using the information we’ve provided, apply PCA to reduce the dimensions to three principal components.
3.  Create a new DataFrame named pcs_df that includes the following columns, PC 1, PC 2, and PC 3, and uses the index of the crypto_df DataFrame as the index.

## Deliverable 3:  Clustering Cryptocurrencies Using K-means

Follow the instructions below and use the information in the crypto_clustering_starter_code.ipynb file to complete Deliverable 3.

1.  Continue using the crypto_clustering.ipynb file that you used in Deliverable 2 to reduce the dataset to three dimensions.
2.  Using the pcs_df DataFrame, create an elbow curve using hvPlot to find the best value for K.
3.  Use the pcs_df DataFrame to run the K-means algorithm to make predictions of the K clusters for the cryptocurrencies’ data.
4.  Create a new DataFrame named clustered_df by concatenating the crypto_df and pcs_df DataFrames on the same columns. The index should be the same as the 
    crypto_df DataFrame.
5.  Add the CoinName column that holds the names of the cryptocurrencies, which you created in Step 7 of Deliverable 1, to the clustered_df.
6.  Add another new column to the clustered_df named Class that holds the predictions, i.e., model.labels_, from Step 3.

## Deliverable 4:  Visualizing Cryptocurrencies Results 

Follow the instructions below and use the information in the crypto_clustering_starter_code.ipynb file to complete Deliverable 4.

1.  Continue using the crypto_clustering.ipynb file from Deliverable 3 where you have predicted the K clusters for the cryptocurrencies’ data.
2.  Create a 3D scatter plot using the Plotly Express scatter_3d() function to plot the three clusters from the clustered_df DataFrame.
3.  Add the CoinName and Algorithm columns to the hover_name and hover_data parameters, respectively, so each data point shows the CoinName and Algorithm on hover.
4.  Create a table with tradable cryptocurrencies using the hvplot.table() function.
5.  Print the total number of tradable cryptocurrencies in the clustered_df DataFrame.
6.  Use the MinMaxScaler().fit_transform method to scale the TotalCoinSupply and TotalCoinsMined columns between the given range of zero and one.
7.  Create a new DataFrame using the clustered_df DataFrame index that contains the scaled data you created in Step 5.
8.  Add the CoinName column from the clustered_df DataFrame to the new DataFrame.
9.  Add the Class column from the clustered_df DataFrame to the new DataFrame.
10. Create an hvplot scatter plot with x="TotalCoinsMined", y="TotalCoinSupply", and by="Class", and have it show the CoinName when you hover over the the data 
    point.
11. Save your crypto_clustering.ipynb file to your Cryptocurrencies folder.
