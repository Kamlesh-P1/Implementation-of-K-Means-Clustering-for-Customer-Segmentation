# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1.Load and preprocess data: Import data, inspect it, and handle missing values if any.

2.Determine optimal clusters: Use the Elbow Method to identify the number of clusters by plotting WCSS against cluster numbers.

3.Fit the K-Means model: Apply K-Means with the chosen number of clusters to the selected features.

4.Assign cluster labels to each data point.

5.Plot data points in a scatter plot, color-coded by cluster assignments for interpretation.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: KAMLESH P
RegisterNumber:  212225240067

import pandas as pd
import matplotlib.pyplot as plt


data = pd.read_csv(r"C:\Users\Admin\Mall_Customers.csv")

print(data.head())
print(data.info())
print(data.isnull())
print(data.isnull().sum())

from sklearn.cluster import KMeans

wcss = []
for i in range(1, 11):
    kmeans = KMeans(n_clusters=i, init="k-means++", random_state=42, n_init=10)
    kmeans.fit(data.iloc[:, 3:])
    wcss.append(kmeans.inertia_)

plt.figure()
plt.plot(range(1, 11), wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
plt.show()


km = KMeans(n_clusters=5, random_state=42, n_init=10)
km.fit(data.iloc[:, 3:])
y_pred = km.predict(data.iloc[:, 3:])
print(y_pred)

data["cluster"] = y_pred


df0 = data[data["cluster"] == 0]
df1 = data[data["cluster"] == 1]
df2 = data[data["cluster"] == 2]
df3 = data[data["cluster"] == 3]
df4 = data[data["cluster"] == 4]


plt.figure()
plt.scatter(df0["Annual Income (k$)"], df0["Spending Score (1-100)"], c="black",  label="cluster0")
plt.scatter(df1["Annual Income (k$)"], df1["Spending Score (1-100)"], c="cyan",   label="cluster1")
plt.scatter(df2["Annual Income (k$)"], df2["Spending Score (1-100)"], c="yellow", label="cluster2")
plt.scatter(df3["Annual Income (k$)"], df3["Spending Score (1-100)"], c="blue",   label="cluster3")
plt.scatter(df4["Annual Income (k$)"], df4["Spending Score (1-100)"], c="green",  label="cluster4")
plt.legend()
plt.title("Customer Segments")
plt.show()

*/
```

## Output:

<img width="901" height="670" alt="image" src="https://github.com/user-attachments/assets/31a5838b-bb79-43ed-bb54-e8faaf447abc" />

<img width="906" height="700" alt="image" src="https://github.com/user-attachments/assets/8ac78abe-6250-491d-afa9-b494a2ddd6b3" />

<img width="875" height="697" alt="image" src="https://github.com/user-attachments/assets/375c172d-0497-49c3-9b2a-c9e37583a096" />

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
