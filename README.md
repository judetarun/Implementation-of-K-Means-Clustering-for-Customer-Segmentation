# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
# 1. Load and preprocess data: Import data, inspect it, and handle missing values if any.

# 2. Determine optimal clusters: Use the Elbow Method to identify the number of clusters by plotting WCSS against cluster numbers.

# 3. Fit the K-Means model: Apply K-Means with the chosen number of clusters to the selected features.

# 4. Assign cluster labels to each data point.

# 5. Plot data points in a scatter plot, color-coded by cluster assignments for interpretation..


## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: JUDE TARUN
RegisterNumber:  212224040144
*/
```
```

import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("C:\\Users\\admin\\Downloads\\Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wess=[]
for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wess.append(kmeans.inertia_)
plt.plot(range(1,11),wess);
plt.xlabel("no of clusters")
plt.ylabel("wess")
plt.title("elbow method")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred=km.predict(data.iloc[:,3:])
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Score"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Score"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Score"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Score"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Score"],c="red",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```
## Output:
<img width="596" height="208" alt="image" src="https://github.com/user-attachments/assets/1164e8d8-701b-4bf1-9301-501dfecaa37d" />
<img width="598" height="453" alt="image" src="https://github.com/user-attachments/assets/15c8f331-b8b9-402e-9ce1-c8f7fe02a9ef" />
<img width="866" height="777" alt="image" src="https://github.com/user-attachments/assets/9492086a-a7fe-476f-a98d-aea8167a28da" />




## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
