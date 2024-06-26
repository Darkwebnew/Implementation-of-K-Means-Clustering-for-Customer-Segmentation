# EX 08-Implementation-of-K-Means-Clustering-for-Customer-Segmentation
## DATE: 20-03-2024
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
Developed by: 
RegisterNumber:  
*/
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
### data.head():

![image](https://github.com/Darkwebnew/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/143114486/ca7a651e-b645-4088-9d99-c1b005d4ad7c)

### data.info():

![image](https://github.com/Darkwebnew/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/143114486/248de517-3a28-4c7d-8b30-b4bb206939a0)

### NULL VALUES:

![image](https://github.com/Darkwebnew/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/143114486/8645b314-2cda-469c-8531-683ce581f108)

### ELBOW GRAPH:

![image](https://github.com/Darkwebnew/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/143114486/91b79a9d-aadb-4541-ab2e-369fd19a3236)

### CLUSTER FORMATION:

![image](https://github.com/Darkwebnew/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/143114486/9cf0f18c-7ef7-4899-9be1-5be3603b8903)

### PREDICICTED VALUE:

![image](https://github.com/Darkwebnew/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/143114486/18f578dc-e981-489e-963b-1e55407fe454)

### FINAL GRAPH(D/O):

![image](https://github.com/Darkwebnew/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/143114486/6159ec39-4842-456b-af2b-7f4bc043928f)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
