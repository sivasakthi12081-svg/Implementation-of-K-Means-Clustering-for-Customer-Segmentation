# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Start and load the customer dataset containing features such as age, income, and spending score.
2. Preprocess the data and choose the number of clusters (K) for grouping customers.
3. Apply the K-Means Clustering algorithm to divide the customers into K clusters based on their similarities.
4. Analyze and visualize the clusters to identify different customer segments. Stop.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Sivasakthi S
RegisterNumber:  212225240151
*/
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans
data = {
    'CustomerID': [1,2,3,4,5,6,7,8,9,10],
    'Gender': ['Male','Female','Female','Male','Female','Male','Male','Female','Female','Male'],
    'Age': [19,21,20,23,31,22,35,30,25,28],
    'Annual Income (k$)': [15,16,17,18,19,20,21,22,23,24],
    'Spending Score (1-100)': [39,81,6,77,40,76,6,94,3,72]
}

df = pd.DataFrame(data)
X = df[['Annual Income (k$)', 'Spending Score (1-100)']]
kmeans = KMeans(n_clusters=3, init='k-means++', random_state=42)
df['Cluster'] = kmeans.fit_predict(X) 
plt.figure(figsize=(8,6))
for i in range(3):
    plt.scatter(X[df['Cluster']==i]['Annual Income (k$)'],
                X[df['Cluster']==i]['Spending Score (1-100)'],
                label=f'Cluster {i+1}')
plt.scatter(kmeans.cluster_centers_[:,0], kmeans.cluster_centers_[:,1],
            s=200, c='yellow', label='Centroids', marker='X')
plt.title('Customer Segmentation (K-Means)')
plt.xlabel('Annual Income (k$)')
plt.ylabel('Spending Score (1-100)')
plt.legend()
plt.show()
print(df)


```

## Output:

<img width="1245" height="806" alt="Screenshot 2026-08-08 175632" src="https://github.com/user-attachments/assets/a7925300-6e7f-4e46-884b-4581faf4319e" />
<img width="1044" height="616" alt="Screenshot 2026-08-08 175644" src="https://github.com/user-attachments/assets/37e659e1-b351-4c13-b2a9-1f6182040695" />

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
