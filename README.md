# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages using import statement.
2. Read the given csv file using read_csv() method and print the number of contents to be displayed
using df.head().
3. Import KMeans and use for loop to cluster the data.
4. Predict the cluster and plot data graphs.
5. Print the outputs and end the program.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: HEMAPRASAD N
RegisterNumber:  212222040054
*/
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers (1).csv")
data.head()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss=[]
for i in range(1,11):
kmeans=KMeans(n_clusters=i,init="k-means++")
kmeans.fit(data.iloc[:,3:])
wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No.of clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred=km.predict(data.iloc[:,3:])
y_pred
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="clu
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="c
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cl
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="c
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label=
plt.legend()
plt.title("Customer Segments")
```


## Output:
![K Means Clustering for Customer Segmentation](sam.png)
![280471348-dea6dcb5-ffab-4bd7-8ec7-ada3d814cc88](https://github.com/Hemaprasad-N/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/135933397/b7c9bde4-3a55-422f-969b-e60af024f668)
![280471384-ddc425e2-3c89-421b-b465-cf7e649ccbd7](https://github.com/Hemaprasad-N/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/135933397/2f4f70c4-ae4b-4cd0-9511-8f01ad330506)
![280471419-4c510013-61d2-4e3d-94e9-d4a869286c8c](https://github.com/Hemaprasad-N/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/135933397/d6a08b65-14df-4cbb-89a4-d520b35145e1)
![280471466-85fec3ce-99b3-4a75-9966-2be7dd3e038e](https://github.com/Hemaprasad-N/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/135933397/04105863-8394-4d23-9828-cf4ba80ea8db)
![280471488-0eaee223-1403-4944-b2e3-fda11158c92e](https://github.com/Hemaprasad-N/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/135933397/6fdcc94c-5db4-4993-946b-7bf8b6113dcd)
![280471514-ae364a9e-447f-4e6b-b07e-f993ab531768](https://github.com/Hemaprasad-N/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/135933397/3b01c6ef-204d-473f-9283-a7d1492dd0b7)
![280471539-df0df64b-eb7b-4853-b926-c3bb9d78d08f](https://github.com/Hemaprasad-N/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/135933397/a60378aa-7e1a-42ee-af72-7d50fa37ddde)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
