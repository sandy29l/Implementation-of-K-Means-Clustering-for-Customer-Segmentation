# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: SANTHOSH L
RegisterNumber:  212222100046

*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
  kmeans = KMeans (n_clusters = i, init ="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("no of cluster")
plt.ylabel("wcss")
plt.title("Elbow Metthod")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="pink",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="green",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="blue",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="black",label="cluster4")
plt.legend()
plt.title("Customer Segments")

```

## Output:
Dataset:

![image](https://github.com/23013753/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145634121/00d0c6ed-9a82-487d-bdb8-c9d047752753)


Dataset information:


![image](https://github.com/23013753/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145634121/3e5e1a8a-5f9c-47e0-aa50-935d9fe69027)



![image](https://github.com/23013753/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145634121/bcde8b22-aae5-4a1d-a5b5-534c6f44693d)



Elbow method graph (wcss vs each iteration):


![image](https://github.com/23013753/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145634121/672ca4c2-50b1-48b9-94e1-afa3f7cb5bd4)



Cluster represnting customer segments-graph:



![image](https://github.com/23013753/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145634121/758facd7-87aa-49bd-95b8-27a217947085)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
