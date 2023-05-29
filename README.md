# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE
import pandas as pd

import seaborn as sns

import matplotlib.pyplot as plt

df = sns.load_dataset("tips")

df.head()

df.isnull().sum()

plt.figure(figsize=(5,5))

plt.title("Data with Outliers")

df.boxplot()

plt.show()

plt.figure(figsize=(5,5))

cols = ['size','tip','total_bill']

Q1 = df[cols].quantile(0.25)

Q3 = df[cols].quantile(0.75)

IQR = Q3 - Q1

df = df[~((df[cols] < (Q1 - 1.5 * IQR)) |(df[cols] > (Q3 + 1.5 * IQR))).any(axis=1)]

plt.title("Dataset after removing outliers")

df.boxplot()

plt.show()

sns.barplot(x=df['day'], y=df['total_bill'])

plt.title("Highest Total Bill Amount by day")

plt.show()

sns.boxplot(x=df['smoker'], y=df['tip'],hue=df['smoker'])

plt.title("Average Tip Amount given by smokers and non-smokers")

plt.show()

df["tip_percent"] = df["tip"] / df["total_bill"]

sns.barplot(x=df['size'],y=df['tip_percent'],data=df)

plt.title("Tip Percentage by Dining Party Size")

plt.show()

sns.barplot(x=df['sex'], y=df['tip'])

plt.title("Highest tips based on gender")

plt.show()

sns.barplot(x=df['day'],y=df['total_bill'])

plt.title("Total bill amount by day of the week")

plt.show()

sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")

plt.title("Distribution of Total Bill Amounts by Time of Day")

plt.show()

sns.barplotdata=df,(x=df['size'],y=df['total_bill'])

plt.title("Average Total Bill Amount by Dining Party Size")

plt.show()

sns.violinplot(x="day", y="tip", data=df)

plt.title("Tip Amount by Day of Week")

plt.show()

sns.barplot(x="time", y="tip", data=df)

plt.title("Tip Amount by Time of Day")

plt.show()

sns.scatterplot(x="total_bill", y="tip", data=df)

plt.title("Correlation between Tip Amount and Total Bill Amount")

plt.show()

# OUPUT
![image](https://github.com/illakiya02/Ex-08-Data-Visualization_1/assets/112244898/afae2d31-eb48-4be9-8fae-bb4d71e2f03f)

![image](https://github.com/illakiya02/Ex-08-Data-Visualization_1/assets/112244898/7f6869a0-e034-474d-b9bc-061c78941202)

![image](https://github.com/illakiya02/Ex-08-Data-Visualization_1/assets/112244898/daea961e-aef8-4243-aed3-a2a16a2f3ecb)

![image](https://github.com/illakiya02/Ex-08-Data-Visualization_1/assets/112244898/8f42fbe0-810d-4faf-ae4e-585ed11a716f)

![image](https://github.com/illakiya02/Ex-08-Data-Visualization_1/assets/112244898/56d67a3c-2a79-4434-aff1-4d174fd47fe8)

![image](https://github.com/illakiya02/Ex-08-Data-Visualization_1/assets/112244898/5cea892f-3ef1-46e5-b15b-f847a650d1e5)

![image](https://github.com/illakiya02/Ex-08-Data-Visualization_1/assets/112244898/395ad309-9542-4f7e-aa26-6a5cd20b0fc3)

![image](https://github.com/illakiya02/Ex-08-Data-Visualization_1/assets/112244898/a957e93f-6b9e-454c-9ffa-29c91fdcdefc)

![image](https://github.com/illakiya02/Ex-08-Data-Visualization_1/assets/112244898/b631ecc5-357b-40c1-b53a-d79ee812c1b9)

![image](https://github.com/illakiya02/Ex-08-Data-Visualization_1/assets/112244898/ba8025c3-30be-48cc-bfa9-597dce0841f6)

![image](https://github.com/illakiya02/Ex-08-Data-Visualization_1/assets/112244898/0c941588-6f90-43b7-914b-329428982e52)

![image](https://github.com/illakiya02/Ex-08-Data-Visualization_1/assets/112244898/6a612810-a88b-4e59-984b-6f360fcfc6e6)

![image](https://github.com/illakiya02/Ex-08-Data-Visualization_1/assets/112244898/40b32e57-3584-47e1-b424-82ed3de5cc1f)

![image](https://github.com/illakiya02/Ex-08-Data-Visualization_1/assets/112244898/5cf5f66f-bc9b-4ee0-a061-e19689925683)

![image](https://github.com/illakiya02/Ex-08-Data-Visualization_1/assets/112244898/de44274e-5c94-4ecd-8ebe-c3cb78419329)

![image](https://github.com/illakiya02/Ex-08-Data-Visualization_1/assets/112244898/391ae85b-558e-423b-92f7-6f153fedc635)

![image](https://github.com/illakiya02/Ex-08-Data-Visualization_1/assets/112244898/ff8d74ce-6fa8-4089-9239-7bc71b4514ee)

![image](https://github.com/illakiya02/Ex-08-Data-Visualization_1/assets/112244898/b2e248be-5d9a-4b96-8ff2-c1e9cd2b0f21)

![image](https://github.com/illakiya02/Ex-08-Data-Visualization_1/assets/112244898/693eb018-6a59-4245-b17f-c79d1afda514)

![image](https://github.com/illakiya02/Ex-08-Data-Visualization_1/assets/112244898/b408f594-bdfd-4191-97d5-da163b9a2b75)

