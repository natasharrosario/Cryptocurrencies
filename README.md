# Cryptocurrencies
#### *Cryptos analysis using unsupervised machine learning and Python*

## Overview

The purpose of this project was to analyze a dataset from many alternative cryptocurrencies to spot trends that make a firm or person want to invest in them. The problem with cryptos is that the most common ones, like bitcoin or ethereum, are becoming unaffordable for the common public. That being said, I will be using *unsupervised machine learning* to see if we can spot any trends that result in opportunities of these altcoins. 

## Results
First, I had to preprocess and transform the data so that unsupervised machine learning could work. This included dropping null values, using only tradaeble and mined cryptocurrencies, numerically encoding categorical columns using the `pandas.get_dummies` method, and scaling the data using the `StandardScaler()` method as well. 

Moreover, I proceeded with the Principal Component Analysis (PCA) to reduce the 98 scaled columns I had, to only 3 principal components. 

<img width="283" alt="Screen Shot 2023-02-09 at 3 51 15 PM" src="https://user-images.githubusercontent.com/113553238/217936566-03c70f1c-0405-4d35-8859-d79afa1a8437.png">


Then, to see how many clusters (k) I could divide the cryptos in, I created an elbow curve. 

<img width="801" alt="Screen Shot 2023-02-09 at 3 51 27 PM" src="https://user-images.githubusercontent.com/113553238/217936623-2cbe8567-ae1b-49b2-8daa-e4668bf1a500.png">


As it can be seen, the optimal result was 4 clusters. So, I then proceeded with the KMeans analysis to fit the pca dataframe and predict the clustering. The product was this `clustered_df` with a 'Class' column that showed the predictions to which group it belonged to. 

<img width="799" alt="Screen Shot 2023-02-09 at 3 51 35 PM" src="https://user-images.githubusercontent.com/113553238/217936678-89ac1f20-f86b-42fa-bdb5-76c1b92a2a62.png">


And last but not least, I came up with some visualizations to better understand the results. 

<img width="736" alt="Screen Shot 2023-02-09 at 3 51 49 PM" src="https://user-images.githubusercontent.com/113553238/217936764-2a8d591e-d027-4040-9526-6f0024ce4ddb.png">


This first one was a 3D scatter plot which located each clustered crypto in relation to the 3 principal components created on the PCA. As it is seen, there are 3 major groups and one outlier. 

<img width="740" alt="Screen Shot 2023-02-09 at 3 52 00 PM" src="https://user-images.githubusercontent.com/113553238/217936815-bf34aacf-ad67-4cf6-af2c-3072c984a5ec.png">


Similarly, when trying to graph the clustered cryptos by total supply and mined coins, we can observe two outliers. The first one with a lot of supply and a lot of mined coins (BitTorrent Crypto) and another one with a lot of supply but not too many coins mined (TurtleCoin). 


## Summary

The job of unsupervised machine learning is to discover patterns or groups of data when there is no known output. That being said, this analysis was successful at grouping cryptocurrencies into 4 groups. If we were to create a crypto investment portfolio we would need to further analyze the clusters. Nevertheless, we have a good start point where we can see that the most profitable and known cryptos are somewhat in the 2 groups that have less supply and mined coins in comparison to others. These cryptos are Bitcoin and Ethereum. Nevertheless, we should keep up with the innovations of technology where new altcoins are being created with very interesting value propositions.
