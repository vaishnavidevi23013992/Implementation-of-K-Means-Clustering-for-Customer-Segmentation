# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Load and clean the customer data for analysis.

2. Select relevant features such as income or spending score.

3. Determine the optimal number of clusters (K) using the Elbow Method.

4. Apply the K-Means algorithm to group customers into K clusters.

5. Assign each customer to the nearest cluster based on centroids.

6. Visualize the clusters and interpret the customer segments.
 

## Program and Output:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: VAISHNAVIDEVI V
RegisterNumber:  212223040230
```
```
import pandas as pd
import matplotlib.pyplot as plt

data = pd.read_csv(r"C:\Users\admin\OneDrive\Desktop\Folders\ML\DATASET-20250226\Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
```
![image](https://github.com/user-attachments/assets/998253bc-c0b3-400a-8fcf-3eaa7822f63b)

```
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans(n_clusters=i, init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow method")
```
![image](https://github.com/user-attachments/assets/39355323-8326-4eb9-8449-f13dec34d0e9)

```
km = KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
```
![image](https://github.com/user-attachments/assets/0c6f53e4-0bda-4f5e-804b-15317b41064a)
