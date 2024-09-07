# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

df=pd.read_csv("/content/titanic_dataset.csv")
print(df)
```
![Screenshot 2024-03-15 094409](https://github.com/Vanitha-SM/EXNO2DS/assets/119557985/d068afbe-1818-483d-b7f5-4d6f3fde42c8)

```
df.info()
```
![Screenshot 2024-03-15 094457](https://github.com/Vanitha-SM/EXNO2DS/assets/119557985/5cd24cf1-5ebe-4037-99f9-634c1d15ceac)

```
df.shape
```
![Screenshot 2024-03-15 094625](https://github.com/Vanitha-SM/EXNO2DS/assets/119557985/aeb29c85-fb55-4ddc-a4d3-1062e43d44c0)

```
df.nunique()
```
![Screenshot 2024-03-15 094708](https://github.com/Vanitha-SM/EXNO2DS/assets/119557985/0851cc7a-aa10-450d-a7a3-703de236c564)

```
df["Survived"].value_counts()
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![Screenshot 2024-03-15 095023](https://github.com/Vanitha-SM/EXNO2DS/assets/119557985/cc1261e3-4a01-48a4-a08d-ddac63b1f660)

```
sns.countplot(data=df,x='Survived')
df.Pclass.unique()
```
![image](https://github.com/Vanitha-SM/EXNO2DS/assets/119557985/c52edcf3-dfb6-44be-aee2-d93b54b9679c)

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/Vanitha-SM/EXNO2DS/assets/119557985/11acd9c7-4683-4ca8-a589-4f044cebe7e0)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/Vanitha-SM/EXNO2DS/assets/119557985/9bcab15a-a8aa-47ca-8763-26cb318df40e)

```
sns.catplot(x='Survived',hue="Gender",data=df,kind="count")
```

![image](https://github.com/Vanitha-SM/EXNO2DS/assets/119557985/e8987583-06b3-4b3d-9089-097dc078e957)

```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/Vanitha-SM/EXNO2DS/assets/119557985/b3ad2f91-20d2-4980-8e56-9b0358337451)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/Vanitha-SM/EXNO2DS/assets/119557985/06690dc7-a353-44d7-9f3e-975880daa2a4)

```
sns.jointplot(x=df["Age"],y=df["Fare"],data=df)
```

![image](https://github.com/Vanitha-SM/EXNO2DS/assets/119557985/1a818b6e-dbc1-48e4-b388-6edb554f37cb)

```
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/Vanitha-SM/EXNO2DS/assets/119557985/8097795f-1c6d-4ed7-9f15-14b1f52c678a)

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/Vanitha-SM/EXNO2DS/assets/119557985/4f75e816-c891-4f7d-b499-c615781c6b15)

```
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/Vanitha-SM/EXNO2DS/assets/119557985/824aa31e-c281-41a9-a839-9a5ab78b90d0)

```
sns.pairplot(df)
```
![image](https://github.com/Vanitha-SM/EXNO2DS/assets/119557985/85698857-6e10-4a2c-932d-1f43fa72671e)

![image](https://github.com/Vanitha-SM/EXNO2DS/assets/119557985/605ceb6d-007d-45f3-8c14-6de3d2ebe60d)


# RESULT
Thus,Data Analyzing of the given dataset was successful.
