# EXNO2DS
# REGISTER NUMBER: 212223040141
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
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns 
df=pd.read_csv("titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/ebe3980d-5512-4de7-b9ab-1c1265fea1ea)
```
df.info()
```
![image](https://github.com/user-attachments/assets/af796119-b8e8-474e-9efc-65f4b3c87ffc)
```
df.shape
```
(891, 12)
```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/12ba23f4-6d37-4d2d-8714-529a5c549465)
```
df.shape
(891, 11)
```
# Categorical data analysis
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/ec8458bf-19c8-4176-98d2-c9160c535bbe)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/b3d0b336-da4a-4f32-a109-8aff02231056)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/8997fbde-4b62-43d6-b60d-2375d3303de7)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/04f44ee4-ee87-41c1-bd09-6156780ca32f)
```
df
```
![image](https://github.com/user-attachments/assets/9c54880f-6f0b-4296-bec0-bf55c87c4901)
```
df.Pclass.unique()
```
array([3, 1, 2], dtype=int64)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/f7e753b2-7535-4210-a299-a0add8dbd6db)
# Bivariate Analysis
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/6f589b20-54d9-4649-b73a-3f59a69eed9e)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/10b44da2-2979-4c3a-8ee0-ecd78d067b40)
```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/a08f1507-957b-46ea-92da-3746fdd97cce)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/26d2b3b9-46be-47c0-aeb5-5de98f0d3e6d)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/1a5ac861-ae7a-43e7-b85f-6298443b40e7)
# Multivariate Analysis
```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/288adffc-9afc-409e-a2af-bd39ed19dcf4)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/7abfac41-c6e6-4be7-9605-0729fccf0dd1)
# Co-relation
```
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/302e4366-f4e5-4ce6-9218-c1af0848cf8b)
```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/bfef23c4-9136-4640-97ba-39f17bcbe6d0)

# RESULT
We have performed Exploratory Data Analysis on the given data set successfully.

