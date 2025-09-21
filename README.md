### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 18/09/2025
### AIM: To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
### Description:
<div align= "justify">Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, 
  application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. 
  This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, 
  or services to meet the specific needs and preferences of each cluster.</div>
  
### Procedure:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.

### Program 1:

```python

import pandas as pd
df=pd.read_csv('clustervisitor.csv')
cluster={"Young":df['Age']<=30,"Middle":((df['Age']>30) & (df['Age']<=50)),"Old":df['Age']>50}
print(cluster)
count=[]
for g,c in cluster.items():
  visitor=df[c]
  count.append(len(visitor))
  print(f'Visitors in {g} group')
  print(visitor)
  print(count)
    
# Define age group labels and plot a bar chart
import matplotlib.pyplot as plt
plt.bar(cluster.keys(),count,data=df)
plt.xlabel('Age Group')
plt.ylabel('Number of Visitors')
plt.show()
```
### Output:

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/8411816e-2c84-4563-b7a1-8b03aa2b94c2" />


----

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/bf469e89-a403-4104-a781-221b73cb6c70" />

### Program 2:

```python
kmeans = KMeans(n_clusters=3, random_state=42)
df['Cluster'] = kmeans.fit_predict(df[['Age']])
print(df)
plt.scatter(df['User_ID'], df['Age'], c=df['Cluster'])
plt.xlabel('User_ID')
plt.ylabel('Age')
plt.title('K-Means')
plt.show()
```

### Output:

<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/0ecafe87-7e15-4206-8138-98d75c35b817" />

----


<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/3ab52a4e-77ec-4923-94d8-ccabbf2f1740" />





### Result:
The implement Cluster and Visitor Segmentation for Navigation patterns in Python is execute successfully
