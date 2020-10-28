# Linkedin Profile Classification using the About Section
Notes: Steps to open .ipynb file if GitHUB shows loading error- <br>
i. Copy link of .ipynb file (for eg- Hover on "TFIDF_kmeans_cluster.ipynb"; right click and copy link address) <br>
ii. Go to https://nbviewer.jupyter.org  <br>
iii. Paste the copied link on nbviewer platform and Click "Go" <br>
iv. The .ipynb file will get loaded without any error.
<br>
<br>

This repository describes about classifying the Linkedin Profiles based on the About Section as input (i.e giving About description from Linkedin as input it will give us output about working domain of profile). The techniqued used is an unsupervised technique, to be precised "Topic Modelling with LDA Mallet". For demo please visit this link "XXXXXXXXXXXXXXXXXXXXXX"
<br>
<br>
Various Steps undergone in the whole project are as follows- <br>
1. **Kmeans Clustering with TFIDF (check TFIDF_kmeans_cluster.ipynb):** The first idea is to decide how to classify the data. And as the data available is unlabeled, so an unsupervised technique is to be chosen for clustering. Clustering with **KMeans** in addition with **TDIFD vectorization** has been performed. It is observed that when the number of clusters are high, the clustering results overlap over each other. So in order to find out the optimum number of clusters ELBOW METHOD and SILHOUETTE METHOD have been performed. And through this methods the optimum number of clusters is found to be 4 (Visualisation result is there in .ipynb file) and this result is justified because if we set the number of clusters to be greater than 4 then it starts overlapping. <br>

We know that the input data contains profile from diverse background like (marketing, software developer, Investors, Entrepreneur, and many more) and thus clusters of four won't help our purpose. Thus decided to go with **Topic Modelling**<br>

However with the help of KMeans clustering we were able to filter out all the foreign languages (i.e input data whose languages are not english) very convincingly. Thus excluding these foreign languages we proceed to Topic Modelling.<br>  < br> 
