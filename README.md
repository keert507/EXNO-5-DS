# EXNO-5-DS-DATA VISUALIZATION USING MATPLOT LIBRARY

# Aim:
  To Perform Data Visualization using matplot python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:

# Import necessary libraries

```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
from scipy.interpolate import make_interp_spline
```
<img width="630" height="145" alt="image" src="https://github.com/user-attachments/assets/a0e4b2f7-2206-432c-adb7-3a4a740d05de" />

# LINE GRAPH

```
x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]

plt.figure(figsize=(7, 5))
plt.plot(x, y, label="Line 1", color='blue', marker='o')
plt.xlabel("X Axis")
plt.ylabel("Y Axis")
plt.title("Simple Line Graph")
plt.legend()
plt.grid(True)
plt.show()
```
<img width="919" height="943" alt="image" src="https://github.com/user-attachments/assets/23ed1ba4-5cd4-4297-90a0-e132f30a2303" />

# MULTIPLE LINES ON SAME GRAPH

```
x1 = [1, 2, 3]
y1 = [2, 4, 1]
x2 = [1, 2, 3]
y2 = [4, 1, 3]

plt.figure(figsize=(7, 5))
plt.plot(x1, y1, label='Line 1', color='r', marker='o')
plt.plot(x2, y2, label='Line 2', color='b', marker='s')
plt.xlabel('x-axis')
plt.ylabel('y-axis')
plt.title('Two Lines on Same Graph')
plt.legend()
plt.grid(True)
plt.show()
```
<img width="890" height="990" alt="image" src="https://github.com/user-attachments/assets/7ecfb9ff-cbd7-49cb-b501-4c72580fb23c" />

# FILL BETWEEN LINE GRAPH

```
x_values = [0, 1, 2, 3, 4, 5]
y_values = [0, 1, 4, 9, 16, 25]

plt.figure(figsize=(7, 5))
plt.plot(x_values, y_values, color='orange', label='y = x²')
plt.fill_between(x_values, y_values, color='yellow', alpha=0.3)
plt.xlabel("X Axis")
plt.ylabel("Y Axis")
plt.title("Line Graph with Fill Between")
plt.legend()
plt.show()
```
<img width="847" height="918" alt="image" src="https://github.com/user-attachments/assets/1b0f8391-dcba-4108-b217-723d72fd8b26" />

# INTERPOLATION USING CUBIC SPLINE

```
x = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
y = np.array([2, 4, 5, 7, 8, 8, 9, 10, 11, 12])
```
<img width="582" height="97" alt="image" src="https://github.com/user-attachments/assets/3dc1a2be-67d6-4e80-b577-2aa752c0a6e5" />

# Cubic spline interpolation

```
x_new = np.linspace(x.min(), x.max(), 300)
spl = make_interp_spline(x, y, k=3)
y_smooth = spl(x_new)

plt.figure(figsize=(7, 5))
plt.plot(x_new, y_smooth, color='purple', label='Cubic Spline Interpolation')
plt.scatter(x, y, color='black', label='Original Data')
plt.xlabel("X Axis")
plt.ylabel("Y Axis")
plt.title("Cubic Spline Interpolation")
plt.legend()
plt.grid(True)
plt.show()
```
<img width="865" height="957" alt="image" src="https://github.com/user-attachments/assets/55c028f7-e7b4-43b9-b688-4eb1ee4fb4ad" />

# BAR GRAPH

```
values = [5, 6, 3, 7, 2]
names = ["A", "B", "C", "D", "E"]

plt.figure(figsize=(7, 5))
plt.bar(names, values, color=['red', 'green', 'blue', 'purple', 'orange'])
plt.xlabel("Names")
plt.ylabel("Values")
plt.title("Simple Bar Graph")
plt.show()
```
<img width="828" height="876" alt="image" src="https://github.com/user-attachments/assets/11f07f54-5d2f-498c-aa62-6db8122e37d4" />

# STACKED BAR GRAPH USING SEABORN DATASET

```
df = sns.load_dataset("tips")
avg_total_bill = df.groupby('day')['total_bill'].mean()
avg_tip = df.groupby('day')['tip'].mean()

plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
plt.show()
```
<img width="859" height="930" alt="image" src="https://github.com/user-attachments/assets/9cc6f5c9-ef38-44d4-a368-f84061bb09d9" />

# SCATTER PLOTS
# Basic scatter:

```
x_values=[0,1,2,3,4,5]
y_values=[0,1,4,9,16,25]
plt.figure(figsize=(7,5))
plt.scatter(x_values,y_values,color='red')
plt.xlabel("X Axis")
plt.ylabel("Y Axis")
plt.title("Basic Scatter Plot")
plt.show()
```
<img width="976" height="956" alt="image" src="https://github.com/user-attachments/assets/a8e71a3e-baf0-4a55-b29c-a738f515a3e0" />

# Custom scatter with labels:

```
x = [1,2,3,4,5,6,7,8,9,10]
y = [2,4,5,7,6,8,9,11,12,12]

plt.figure(figsize=(7, 5))
plt.scatter(x, y, label="stars", color="green", marker="*", s=100)
plt.xlabel("X Axis")
plt.ylabel("Y Axis")
plt.title("Scatter Plot with Stars")
plt.legend()
plt.grid(True)
plt.show()
```
<img width="962" height="1023" alt="image" src="https://github.com/user-attachments/assets/0b251a55-eb31-47f1-b1ec-d3c6b6b5cb0c" />

# PIE CHART

```
activities = ['eat', 'sleep', 'work', 'play']
slices = [3, 7, 8, 6]
colors = ['r', 'y', 'g', 'b']

plt.figure(figsize=(6, 6))
plt.pie(slices, labels=activities, colors=colors, startangle=90, shadow=True, autopct='%1.1f%%')
plt.title("Daily Activities")
plt.show()
```
<img width="1172" height="979" alt="image" src="https://github.com/user-attachments/assets/5473cb82-8063-405c-9673-032be85cda6e" />

# Result:
  To Perform Data Visualization using matplot python library for the given datas has executed successfully

# Summary:

In this experiment, we explored various data visualization techniques using the Matplotlib library in Python. We created different types of charts, including line graphs, bar charts, scatter plots, pie charts, and filled line plots. These visualizations helped us understand how to represent data effectively for better analysis and interpretation. We also used interpolation with cubic splines to create smooth curves and learned how to combine multiple datasets in a single plot. Overall, this experiment demonstrated the importance of visualization in making data more meaningful, easier to understand, and visually appealing for decision-making and communication.
