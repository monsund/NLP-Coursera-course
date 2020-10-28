# Linkedin Profile Classification using KMEANS, LDA, TFIDF
***Notes: Steps to open .ipynb file if GitHUB shows loading error- <br>
i. Copy link of .ipynb file (for eg- Hover on "TFIDF_kmeans_cluster.ipynb"; right click and copy link address) <br>
ii. Go to https://nbviewer.jupyter.org  <br>
iii. Paste the copied link on nbviewer platform and Click "Go" <br>
iv. The .ipynb file will get loaded without any error.***
<br>
<br>

This repository describes about classifying the Linkedin Profiles based on the About Section as input (i.e giving About description from Linkedin as input it will give us output about working domain of profile). The techniqued used is an unsupervised technique, to be precised "Topic Modelling with LDA Mallet". For demo please visit this link "XXXXXXXXXXXXXXXXXXXXXX"
<br>
<br>
Various Steps undergone in the whole project are as follows- <br>
1. **Kmeans Clustering with TFIDF (check TFIDF_kmeans_cluster.ipynb):** The first idea is to decide how to classify the data. And as the data available is unlabeled, so an unsupervised technique is to be chosen for clustering. Clustering with **KMeans** in addition with **TDIFD vectorization** has been performed. It is observed that when the number of clusters are high, the clustering results overlap over each other. So in order to find out the optimum number of clusters **ELBOW METHOD** and **SILHOUETTE METHOD** have been performed. And through this methods the optimum number of clusters is found to be 4 (Visualisation result is there in .ipynb file) and this result is justified because if we set the number of clusters to be greater than 4 then it starts overlapping. <br>

We know that the input data contains profile from diverse background like (marketing, software developer, Investors, Entrepreneur, and many more) and thus clusters of four won't help our purpose. Thus decided to go with **Topic Modelling**<br>

However with the help of KMeans clustering we were able to filter out all the foreign languages (i.e input data whose languages are not english) very convincingly. Thus excluding these foreign languages we proceed to Topic Modelling. <br> <br> 


2. **Topic Modelling with LDA MALLET**: This is done in two steps- <br>
i. Creation of dictionary for LDA Mallet Model (for code check **_gensim_LDA_corpus_creation.ipynb file_**): Basic data cleaning like removing stopwords and punctuation have been performe. In addition low frequency words are removed from the dictionary.<br>

ii. Clustering of Data with LDA Mallet Model (for code check **_gensim_LDA_Mallet.ipynb file_**): a) For finding optimum nuber of topics **Coherence Score** have been calculated with varying topic numbers and thus from analysis the optimum topic number chosen is 18. <br>
b) We have got quite a good result which can be seen on **pyLDAvis Visualization**. From the Visualization chart it is observed that topics related to software, data, marketing, startup(entrepreneur), business, investment, etc have been segregated beautifully. <br>

Our next steps is to use the result of topic modelling and build a statistical model out of it. This data from Topic Modelling will be used as labelled data for statistical modelling. <br><br>


3. **Data Preparation for Statistical Classification Model** (for code check **data_prep_for_statistical_classification.ipynb**): Out of 18 topics which resulted from Topic Modelling, **Nine major topics** has been chosen for statistical classification. From each of these nine topics we have taken only those data with high probability of being in that particular topic. For more details please check **.ipynb file**. <br>

The topic number output from **Topic Modelling** are used as labels for each category<br><br>


4. **Classification with RandomForest and TFIDF vectorizer** (for code check **random_forest_classification.ipynb** ):  The classification results shows 86% accuracy, 86% recall and 87% precesion.<br>

But for the final output, instead of showing one discreet category it is represented as a mixed of all the topics with respect to their probability. This is because for example a profile with software background may be also be good at data science, product managment, etc. Thus the results is shown in probability of falling into these categories.


