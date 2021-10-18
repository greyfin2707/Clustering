# Crypto Clustering
This code is designed to cluster two hundred cryptocurrencies by time series. For this purpose, the hourly data was first uploaded using the cryptocompare Python library. It can also be used to unload daily and minute data on cryptocurrencies. In order to facilitate the unloading, a class was created, which can be used to unload this data depending on the need. It is also worth noting that the data was unloaded only by the closing price.

![image](https://user-images.githubusercontent.com/87248163/136692785-2f637507-7bf9-430e-939d-c324ad5f256d.png)


The variable names stores cryptocurrency tickers. You can remove unnecessary cryptocurrencies by simply removing tickers that are unnecessary to you. You can also add new tickers, but for that you need the data of added cryptocurrencies to be available in cryptocompare library.

![image](https://user-images.githubusercontent.com/87248163/136692809-343b5b0f-12e8-48e7-bd68-53ae61f26bfa.png)


The data was then pre-prepared for convenience (so, for example, the column 'index' was renamed to 'ticker').

The tslearn and sklearn libraries were used to cluster the time series. The methods that were used: Kmeans, DTW (Dynamic Time Warping). The number of clusters was determined using silhouette_score and distortions (their graphs were plotted for this purpose). As a result, 5 clusters were chosen for Kmeans method and 7 for DTW. 

![image](https://user-images.githubusercontent.com/87248163/136692854-62ff3506-bdd7-4ca2-92b1-6a40e9037894.png)

![image](https://user-images.githubusercontent.com/87248163/136692868-f2e7439d-35c2-4cc9-bddf-96634d1d8973.png)


For convenience, graphs of each cryptocurrency were plotted and grouped into clusters. Also the information was uploaded to csv files hour_conclusion_kmeans.csv and hour_conclusion_dtw.csv

# Conclusion:
DTW method coped better with cryptocurrency time series clustering - especially this method, in contrast to Kmeans, was able to display some cryptocurrencies with extreme graphs (for example, BTCB) in a separate cluster. 

October, 18
![image](https://user-images.githubusercontent.com/87248163/137759855-06d9898f-74ce-4cf7-8c0d-b7d1e51b53c0.png)
![image](https://user-images.githubusercontent.com/87248163/137760180-ec09cf26-eb82-40a5-8db4-9a7475a28b53.png)

October, 10
![image](https://user-images.githubusercontent.com/87248163/136692911-61886d9e-1913-4153-abd6-0778f3f0e517.png)

Despite this, some extreme data failed to cluster successfully. 

October, 10
![image](https://user-images.githubusercontent.com/87248163/136692954-c3462e0c-edf4-4577-8f05-e80cd0ef9756.png)

Anyway, both methods failed to cope 100%, but we can see the obvious patterns according to which cryptocurrencies were clustered, which gives already a good result.


