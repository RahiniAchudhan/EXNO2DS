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
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df
```
# Output
![Screenshot 2025-03-28 081316](https://github.com/user-attachments/assets/281d2911-a4aa-436a-945c-acd15b8e9d60)

```
df.info()
```
# Output
![Screenshot 2025-03-28 081358](https://github.com/user-attachments/assets/c14f0e03-9b51-43bf-b936-0edece7bffd1)

```
df.shape
```
# Output
![Screenshot 2025-03-28 094140](https://github.com/user-attachments/assets/50be4d04-9029-4a0c-a6c0-7a9aa7aa6bb7)

```
df.set_index("PassengerId",inplace=True)
df.describe()
```
# Output
![Screenshot 2025-03-28 094219](https://github.com/user-attachments/assets/abbb1d71-5773-4c32-b6bd-9ef4fa3a6287)

```
df.nunique()
```
# Output
![Screenshot 2025-03-28 094255](https://github.com/user-attachments/assets/f1b126ed-cd0b-477c-b754-49be35b83207)

```
df["Survived"].value_counts()
```
# Output
![Screenshot 2025-03-28 094332](https://github.com/user-attachments/assets/b6f1e3f0-3d01-47f7-8db6-e18b205f2f97)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
# Output
![Screenshot 2025-03-28 094426](https://github.com/user-attachments/assets/63c7aee7-aaf8-480a-b0e8-d2b0dfb7473a)

```
sns.countplot(data=df,x="Survived")
```
# Output
![Screenshot 2025-03-28 094459](https://github.com/user-attachments/assets/0f1b8b53-7de3-48b7-bf17-5bcd3a712d7d)

```
df
```
# Output
![Screenshot 2025-03-28 094533](https://github.com/user-attachments/assets/e4ba4722-ab29-435e-84f8-075a3ddd7088)

```
df.Pclass.unique()
```
# Output
![Screenshot 2025-03-28 094605](https://github.com/user-attachments/assets/eaae6487-9cf8-4d11-a338-de184fb90339)

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
# Output
![Screenshot 2025-03-28 094636](https://github.com/user-attachments/assets/6267adc3-ce32-400e-8cb6-a5dd186e7f39)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
# Output
![Screenshot 2025-03-28 094709](https://github.com/user-attachments/assets/a3cfa550-d291-4094-83c5-d2c864b77794)

```
sns.catplot(x='Survived',hue="Gender",data=df,kind='count')
```
# Output
![Screenshot 2025-03-28 094752](https://github.com/user-attachments/assets/f5b36fdc-5987-4141-ba54-45c76ec48bcf)

```
df.boxplot(column="Age",by="Survived")
```
# Output
![Screenshot 2025-03-28 094828](https://github.com/user-attachments/assets/32cb6ab3-774c-4482-b3e9-0e358d937832)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
# Output
![Screenshot 2025-03-28 094914](https://github.com/user-attachments/assets/3f9adc14-f346-4605-9da6-2bd6ecbb57a7)

```
sns.jointplot(x="Age",y="Fare",data=df)
```
# Output
![Screenshot 2025-03-28 094948](https://github.com/user-attachments/assets/b63811de-b6a8-4e0c-a016-04b847de6fcf)

```
fig,ax1=plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=df)
```
# Output
![Screenshot 2025-03-28 095023](https://github.com/user-attachments/assets/39527055-78a7-4a48-b416-0de167809a4c)

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
# Output
![Screenshot 2025-03-28 095052](https://github.com/user-attachments/assets/4b60799d-82b6-446f-987e-4d15ad216d16)

```
numerical_df = df.select_dtypes(include=['number'])
corr = numerical_df.corr()
sns.heatmap(corr, annot=True)
```
# Output
![Screenshot 2025-03-28 095121](https://github.com/user-attachments/assets/7fc323a9-c6b8-45cf-acc6-e6a581b5e13d)

```
sns.pairplot(df)
```
# Output
![image](https://github.com/user-attachments/assets/4ed2fdd6-0f36-4e50-a9d3-e4a96027f045)


# RESULT
        Thus, the Exploratory Data Analysis on the given data set was performed successfully.
