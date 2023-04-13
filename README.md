# Ex-04-Multivariate-Analysis
# AIM
To perform Multivariate EDA on the given data set.

# Explanation:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM:
## STEP 1
Import the built libraries required to perform EDA and outlier removal.

## STEP 2
Read the given csv file

## STEP 3
Convert the file into a dataframe and get information of the data.

## STEP 4
Return the objects containing counts of unique values using (value_counts()).

## STEP 5
Plot the counts in the form of Histogram or Bar Graph.

## STEP 6
Use seaborn the bar graph comparison of data can be viewed.

## STEP 7
Find the pairwise correlation of all columns in the dataframe.corr()

## STEP 8
Save the final data set into the file

# PROGRAM:
```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("/content/SuperStore.csv")
df
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
state=df.loc[:,["State","Sales"]]
state=state.groupby(by=["State"]).max().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=state.index,y="Sales",data=state)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
dep=df.loc[:,["Ship Mode","Sales"]]
dep=dep.groupby(by=["Ship Mode"]).max().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=dep.index,y="Sales",data=dep)
plt.xticks(rotation = 90)
plt.xlabel=(" SHIP MODE")
plt.ylabel=("SALES")
plt.show()
bas=df.loc[:,["Segment","Sales"]]
bas=bas.groupby(by="Segment").max().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=bas.index,y="Sales",data=bas)
plt.xticks(rotation=90)
plt.xlable=("SEGMENT")
plt.ylable=("SALES")
plt.plot()
sri=df.loc[:,["Postal Code","Sales"]]
sri=sri.groupby(by="Postal Code").sum().sort_values(by="Sales")
plt.figure(figsize=(99,20))
sns.barplot(x=sri.index,y="Sales",data=sri)
plt.xticks(rotation=90)
plt.xlable=("POSTALCODE")
plt.ylable=("SALES")
plt.plot()
sns.barplot(x=df['Sales'],y=df['Ship Mode'],hue=df['Category'])
```
# OUTPUT:
![c1](https://user-images.githubusercontent.com/118703522/231639012-ad6d02f3-75e7-4188-9d79-6853d88fc04d.png)
![c2](https://user-images.githubusercontent.com/118703522/231639075-01653f66-4ebc-4d8d-863a-0b707bf46aed.png)



