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
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
print(df)
![Screenshot 2024-09-07 063459](https://github.com/user-attachments/assets/f2c88a24-6cc8-41b9-98d4-6cfda95cbf39)

df.info()

![Screenshot 2024-09-07 063627](https://github.com/user-attachments/assets/00dbe0d4-625a-496e-bcdf-354396908c8b)

df.shape

![Screenshot 2024-09-07 063711](https://github.com/user-attachments/assets/f19d4116-663f-416e-91b7-f00fd5f3eb17)
df.nunique()

![Screenshot 2024-09-07 063750](https://github.com/user-attachments/assets/aae1d7bc-dd32-44a2-99d7-b5d2b732473e)

df["Survived"].value_counts()
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per

![Screenshot 2024-09-07 063851](https://github.com/user-attachments/assets/bc737d9a-91b4-4f11-80d0-46bdacbc1ec2)

sns.countplot(data=df,x='Survived')
df.Pclass.unique()

![Screenshot 2024-09-07 063936](https://github.com/user-attachments/assets/afdadbc0-deb9-4b0d-9376-ba7988fa8eba)

df.rename(columns={'Sex':'Gender'},inplace=True)
df

![Screenshot 2024-09-07 064031](https://github.com/user-attachments/assets/5cddff36-9970-4b00-b9fb-bd8c1352ee05)

sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)

![Screenshot 2024-09-07 064115](https://github.com/user-attachments/assets/9d2e0e14-eef9-4bfc-9602-4764215ba787)

sns.catplot(x='Survived',hue="Gender",data=df,kind="count")

![Screenshot 2024-09-07 065621](https://github.com/user-attachments/assets/0a1d66ec-36be-4003-92e9-2e86e0802ab7)

df.boxplot(column="Age",by="Survived")
![Screenshot 2024-09-07 065712](https://github.com/user-attachments/assets/c2d0b9fd-075c-414a-a50e-04098ed2541b)

sns.scatterplot(x=df["Age"],y=df["Fare"])
![Screenshot 2024-09-07 065801](https://github.com/user-attachments/assets/4026618d-3b74-49e2-943f-94129e136e0a)

sns.jointplot(x=df["Age"],y=df["Fare"],data=df)
![Screenshot 2024-09-07 065859](https://github.com/user-attachments/assets/7020f300-7307-4474-8c17-5230430c1c24)

fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)

![Screenshot 2024-09-07 065939](https://github.com/user-attachments/assets/b005c94e-3cb0-4f2b-a760-a2a5389d2781)
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")

![Screenshot 2024-09-07 070028](https://github.com/user-attachments/assets/431ce6a7-cd73-4174-81cb-77cf41316a31)

corr=df.corr()
sns.heatmap(corr,annot=True)
![Screenshot 2024-09-07 070129](https://github.com/user-attachments/assets/dc08eb57-5fee-4109-8c22-2bd9b7eff5e4)

sns.pairplot(df)

![Screenshot 2024-09-07 070234](https://github.com/user-attachments/assets/52b13abf-2077-42d8-936a-fbd2bf8ea600)


# RESULT
Thus,Data Analyzing of the given dataset was successful.
