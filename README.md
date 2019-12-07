## Clustering of online shoppers with k-means and AGNEST

### Problem description and the data

In this project we consider the Online Shoppers Intention dataset (provided at UCI Machine Learning Repository). https://archive.ics.uci.edu/ml/datasets/Online+Shoppers+Purchasing+Intention+Dataset

This dataset has 18 columns and 12,330 rows. The 18 attributes include 8 categorical and 10 numerical attributes. The last attribute "Revenue" is the class label: "0" means not ending up shopping, and "1" means ending up shopping. The meaning of the other attributes are the following:

"Administrative", "Administrative Duration", "Informational", "Informational Duration", "Product Related" and "Product Related Duration" represent the number of different types of pages visited by the visitor in that session and total time spent in each of these page categories. The values of these features are derived from the URL information of the pages visited by the user and updated in real time when a user takes an action, e.g. moving from one page to another. The “Bounce Rate”, “Exit Rate” and “Page Value” features represent the metrics measured by “Google Analytics” for each page in the e-commerce site. The value of “Bounce Rate” feature for a web page refers to the percentage of visitors who enter the site from that page and then leave (“bounce”) without triggering any other requests to the analytics server during that session. The value of “Exit Rate” feature for a specific web page is calculated as for all page views to the page, the percentage that were the last in the session. The “Page Value” feature represents the average value for a web page that a user visited before completing an e-commerce transaction. 

The "Special Day" feature indicates the closeness of the site visiting time to a specific special day (e.g. Mothers Day, Valentine’s Day) in which the sessions are more likely to be finalized with transaction. The value of this attribute is determined by considering the dynamics of e-commerce such as the duration between the order date and delivery date. For example, for Valentin's day, this value takes a nonzero value between February 2 and February 12, zero before and after this date unless it is close to another special day, and its maximum value of 1 on February 8. The dataset also includes operating system, browser, region, traffic type, visitor type as returning or new visitor, a Boolean value indicating whether the date of the visit is weekend, and month of the year.

We would explore the following clustering models with k = 4 to provide insight into the dataset and report the comparison of their performances:

  1. K-means
  2. Complete-Linkage Agglomerative nesting

The last attribute "Revenue" is used for metrics only and not for the classification process.

### Program

The online_shopping_clustering.ipynb program can be executed in Jupiter notebook. The dataset online_shoppers_intention.csv should be present in the same directory as the nba_ml.ipynb code.

### Performance metrics

The metrics for the evaluation of the classification are:

Rand Index (RI https://en.wikipedia.org/wiki/Rand_index). The range of RI is between zero and one and the bigger value is considered    to be a better in terms of clustering. 

Davies-Bouldin Index (DBI https://en.wikipedia.org/wiki/Davies%E2%80%93Bouldin_index). The range of DBI is between zero and infinity and the lower value is considered to be better in terms of clustering. 

### Process

1. Importing the necessary packages
2. Loading the data and data inspection
3. Categorical variable processing
4. Data visualization/ Addressing of the null value and Outliers
5. K-means clustering
6. Computation of RI for k-means
7. Computation of DBI for k-means
8. Agglomerative Clustering (AGNEST)
9. Computation of RI for AGNEST
10. Computation of DBI for AGNEST
11. Performance comparision of various clustering techniques w.r.t. metrics

### Questions 

1. When you prepare the data for training the models, how did you deal with the categorical attributes, for the clustering models we examine here only takes numerical features?

We used mean encoding for the VisitorType and Month fields. Mean encoding is a technique that uses the target variable as the basis to generate the new encoded feature. Furthermore, we used Binarization for the Weekend and Revenue fields. Binarization is the process of transforming data features into binary numbers to make classifier algorithms more efficient. 

2. Which model is better considering their RI scores?

The range of RI is between zero and one and the bigger value is considered to be better in terms of clustering. 

  Rand index for K-Means is: 0.516
  Rand index for Agglomerative Clustering is: 0.633
  Agglomerative Clustering is better than K-Means in RI metric


3. Which model is better considering their DBI scores?

The range of DBI is between zero and infinity and the lower value is considered to be better in terms of clustering. 

  DBI for K-Means Clustering is: 0.722
  DBI for Agglomerative Clustering is: 0.759
  K_Means is better than Agglomerative Clustering in DBI metric.
  

