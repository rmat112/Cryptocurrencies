# Cryptocurrencies
Unsupervised Machine Learning
## Overview of Analysis
In this project, Unsupervised machine learning is used for, how to process data, how to cluster, how to reduce your dimensions, and how to reduce the principal components using PCA. All these skills are put to use by creating an analysis for clients who are preparing to get into the cryptocurrency market.
Accountability Accounting, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies. This projects is about creating a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment.
The data we will be working with is not ideal, so it will need to be processed to fit the machine learning models. Since there is no known output for what we are looking for, we have decided to use unsupervised learning. To group the cryptocurrencies, we decided on a clustering algorithm. We will use data visualizations to share our findings.

## Tools and Resources
- Dataset: [crypto_data.csv](https://github.com/rmat112/Cryptocurrencies/blob/main/crypto_data.csv)
- Tools: Python 3.9.7, Jupyter Notebook 6.4.5

## Results
This is a link to the Jupyter Notebook [crypto_clustering.ipynb](https://github.com/rmat112/Cryptocurrencies/blob/main/crypto_clustering.ipynb). The results of analysis are presented in the following sections.

### Section 1: Preprocessing the Data
- The [crypto_data.csv](https://github.com/rmat112/Cryptocurrencies/blob/main/crypto_data.csv) dataset was used to create a pandas DataFrame. The DataFrame is preprocessed to prepare crypto_df DataFrame as illustrated
![Del1_crypto_df.png](https://github.com/rmat112/Cryptocurrencies/blob/main/images/Del1_crypto_df.png)
- A new DataFrame is created that stores all cryptocurrency names from the CoinName column and retains the index from the crypto_df DataFrame
![coinNames.png](https://github.com/rmat112/Cryptocurrencies/blob/main/images/coinNames.png)
- The get_dummies() method is used to create variables for the text features, which are then stored in a new DataFrame, X 
![Del1_get_dummies.png](https://github.com/rmat112/Cryptocurrencies/blob/main/images/Del1_get_dummies.png)
- The features from the X DataFrame have been standardized using the StandardScaler fit_transform() function
![crypto_scaled.png](https://github.com/rmat112/Cryptocurrencies/blob/main/images/crypto_scaled.png)

### Section 2: Reducing Data Dimensions Using PCA
- The PCA algorithm reduces the dimensions of the X DataFrame down to three principal components
- The pcs_df DataFrame is created and has the following three columns, PC 1, PC 2, and PC 3, and has the index from the crypto_df DataFrame
![Del2.png](https://github.com/rmat112/Cryptocurrencies/blob/main/images/Del2.png)

### Section 3: Clustering Cryptocurrencies Using K-means
The K-means algorithm is used to cluster the cryptocurrencies using the PCA data, where the following steps have been completed:
- An elbow curve is created using hvPlot to find the best value for K 
![elbow_curve.png](https://github.com/rmat112/Cryptocurrencies/blob/main/images/elbow_curve.png)
- Predictions are made on the K clusters of the cryptocurrencies’ data
![predictions.png](https://github.com/rmat112/Cryptocurrencies/blob/main/images/predictions.png)
- A new DataFrame is created with the same index as the crypto_df DataFrame and has the following columns: Algorithm, ProofType, TotalCoinsMined, TotalCoinSupply, PC 1, PC 2, PC 3, CoinName, and Class
![Del3_new_df.png](https://github.com/rmat112/Cryptocurrencies/blob/main/images/Del3_new_df.png)

### Section 4: Visualizing Cryptocurrencies Results
- The clusters are plotted using a 3D scatter plot, and each data point shows the CoinName and Algorithm on hover 
![scatter_3d.png](https://github.com/rmat112/Cryptocurrencies/blob/main/images/scatter_3d.png)
- A table with tradable cryptocurrencies is created using the hvplot.table() function
![hvplotTable.png](https://github.com/rmat112/Cryptocurrencies/blob/main/images/hvplotTable.png)
- The total number of tradable cryptocurrencies
![Del4_tradable.png](https://github.com/rmat112/Cryptocurrencies/blob/main/images/Del4_tradable.png)
- A DataFrame is created that contains the clustered_df DataFrame index, the scaled data, and the CoinName and Class columns
![plot_df.png](https://github.com/rmat112/Cryptocurrencies/blob/main/images/plot_df.png)
- A hvplot scatter plot is created where the X-axis is "TotalCoinsMined", the Y-axis is "TotalCoinSupply", the data is ordered by "Class", and it shows the CoinName when you hover over the data point 
![2Dplot.png](https://github.com/rmat112/Cryptocurrencies/blob/main/images/2Dplot.png)

