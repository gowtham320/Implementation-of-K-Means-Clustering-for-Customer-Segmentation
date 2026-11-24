# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the required Python libraries such as Pandas, Matplotlib, and Scikit-learn.
2. Load the Mall_Customers.csv dataset using Pandas.
3. Select Annual Income (k$) and Spending Score (1-100) as the features for customer segmentation.
4. Initialize the number of clusters as 5.
5. Apply the K-Means Clustering algorithm to group customers into different clusters.
6 Calculate the cluster centroids and assign each customer to the nearest cluster.
7. Repeat the clustering process until the cluster assignments become stable.
8. Add the cluster labels to the dataset.
9. Display the customer groups and cluster centers.
10. Visualize the clusters using a scatter plot.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: gowtham u
RegisterNumber: 212225040099


import pandas as pd
import matplotlib.pyplot as plt

from sklearn.cluster import KMeans

# Load the dataset
data = pd.read_csv("Mall_Customers.csv")

# Display the first five records
print("First five records of the dataset:")
print(data.head())

# Select features for clustering
X = data[
    [
        "Annual Income (k$)",
        "Spending Score (1-100)"
    ]
]

# Create K-Means model
kmeans = KMeans(
    n_clusters=5,
    random_state=42,
    n_init=10
)

# Train the model and assign clusters
data["Cluster"] = kmeans.fit_predict(X)

# Display cluster labels
print("\nCustomer Segmentation:")
print(
    data[
        [
            "CustomerID",
            "Annual Income (k$)",
            "Spending Score (1-100)",
            "Cluster"
        ]
    ].head(20)
)

# Display cluster centers
print("\nCluster Centers:")
print(kmeans.cluster_centers_)

# Display number of customers in each cluster
print("\nNumber of Customers in Each Cluster:")
print(data["Cluster"].value_counts().sort_index())

# Plot the clusters
plt.figure(figsize=(8, 6))

plt.scatter(
    X["Annual Income (k$)"],
    X["Spending Score (1-100)"],
    c=data["Cluster"],
    s=50
)

# Plot cluster centers
plt.scatter(
    kmeans.cluster_centers_[:, 0],
    kmeans.cluster_centers_[:, 1],
    s=200,
    marker="X",
    label="Centroids"
)

plt.xlabel("Annual Income (k$)")
plt.ylabel("Spending Score (1-100)")
plt.title("K-Means Clustering for Customer Segmentation")
plt.legend()
plt.show() 
*/
```

## Output:
<img width="498" height="406" alt="Screenshot 2026-11-24 101001" src="https://github.com/user-attachments/assets/2f5dfafb-7bfa-4189-86fc-af2045e7cef0" />

<img width="1077" height="851" alt="Screenshot 2026-11-24 101022" src="https://github.com/user-attachments/assets/dd915d69-b34a-4977-a890-5e9283f50a2e" />


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
