# EXNO:2 DS- EDA Analysis Using Pyhton
## Name: NARAMALA KUAMRTEJA
## Register Number : 212223230132
## Department : Artificial Intelligence And Data Science
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
### Colab Link:
https://colab.research.google.com/drive/12c6m3peqMZ7KdOOjM9odD_yZS-LeVWaJ?usp=sharing
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```
```
df=pd.read_csv('titanic_dataset.csv')
df
```
![image](https://github.com/user-attachments/assets/f15211a9-b346-4934-b1eb-4d87ad3e9c19)
```
df.info()
```
![image](https://github.com/user-attachments/assets/e1ec3ec9-24df-4b8f-b3d6-34132e5fecc3)
```
df.shape
```
![image](https://github.com/user-attachments/assets/00ffcda9-1a83-479c-b72f-359693b6c34e)
```
df.set_index("PassengerId",inplace=True)
df
```
![image](https://github.com/user-attachments/assets/2b2c66df-d1b4-4bdb-9843-ee8ba1162af0)
```
df.describe()
```
![image](https://github.com/user-attachments/assets/9fcda9a0-01a6-4475-afd7-69bcb1f80519)
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/39185ed2-fd24-4799-9578-3c788826cb29)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/f1d25e01-85b8-4af1-bace-77f6fe240852)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/38776bf0-1e9f-4df9-9a24-f158adda1664)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/864b1a38-c04b-4504-b17c-428927e244d1)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/614b0e3a-b7ae-45a5-bcb3-68b45dc29a0f)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/ce7969e0-c03f-472e-8e6f-c22f10a35709)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df)
```
![image](https://github.com/user-attachments/assets/2a794d8e-6c2e-42b9-8fa3-e02f04b13b97)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/a262d68c-d37c-47ca-9b64-2e5b767e002e)
```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/1a90e305-a6a1-4e2f-84f2-db5511713064)
```
sns.scatterplot(x=df['Age'],y=df['Fare'])
```
![image](https://github.com/user-attachments/assets/1205be64-cdea-4c5c-8833-c32b9a5150d1)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/e7cc46d4-d983-4dbe-882c-993630880a45)
```
sns.catplot(col="Survived",x="Gender",hue="Pclass",kind="count",data=df)
```
![image](https://github.com/user-attachments/assets/b065c59b-f8ca-4e4c-84e8-47b4f8cf3da0)
```
num=df.select_dtypes(exclude=[object])
sns.heatmap(num.corr(),annot=True)
```
![image](https://github.com/user-attachments/assets/3f00a35d-1ed4-44c6-bec4-f6fc45ad430e)
```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/377b0f66-1bc0-4bde-8aaf-e68cfb65b3a3)
# RESULT
Hence, The EDA Analysis of an given sample has been analised successfully.
