### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 
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

### Program:
```python
# Visitor segmentation based on characteristics
# read the data
import pandas as pd
df=pd.read_csv('clustervisitor.csv')

# Perform segmentation based on characteristics (e.g., age groups)
cluster={"Young":df['Age']<=30,"Middle":((df['Age']>30) & (df['Age']<=50)),"Old":df['Age']>50}
print(cluster)

```
### Output:

<img width="286" height="247" alt="image" src="https://github.com/user-attachments/assets/c61fffc4-c2d1-4834-a4f4-f266a70fd7db" />


### Visualization:
```python
# Create a list to store counts of visitors in each age group

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


<img width="363" height="563" alt="image" src="https://github.com/user-attachments/assets/5aa464db-a5b9-456f-9345-229551bacff8" />





<img width="499" height="366" alt="image" src="https://github.com/user-attachments/assets/1f2442d4-0650-411a-a049-74f23a8c1758" />




### Result:
