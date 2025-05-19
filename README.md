# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import dataset and print head,info of the dataset  
2.check for null values   
3.Import kmeans and fit it to the dataset    
4.Plot the graph using elbow method    
5.Print the predicted array    
6.Plot the customer segments    

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by:JEGATHEESWARI R
RegisterNumber:  212223230092
*/
```
```

import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("/content/Mall_Customers (1).csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss=[]
for i in range(1,11):
   kmeans=KMeans(n_clusters=i,init="k-means++")
   kmeans.fit(data.iloc[:,3:])
   wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No_of_Clusters")
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
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segment")
```
## Output:
### 1.DATA.HEAD():
![image](https://github.com/user-attachments/assets/3384b510-be72-493d-afb4-578fc0d1cc83)



### 2.DATA.INF0():
![image](https://github.com/user-attachments/assets/89a66abd-c59f-41b4-8965-cc0a7106d714)


### 3.PLOT USING ELBOW METHOD:
![image](https://github.com/user-attachments/assets/d6032ed8-2f2e-4ab4-8d1d-7bf4e4f4faa6)


### 4.CUSTOMER SEGMENT:

![image](https://github.com/user-attachments/assets/fbd31525-474c-431f-b5c2-9f3542d102e1)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
