# EXNO-2-DS-EDA Analysis using Python
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
import pandas as pd

import seaborn as sns

import matplotlib.pyplot as plt

import numpy as np

dt=pd.read_csv("/content/titanic_dataset (2).csv")

dt

![image](https://github.com/user-attachments/assets/7b290194-b215-4123-8ad6-aab1850c7928)


dt.info()

![image](https://github.com/user-attachments/assets/61ba31c0-b3cb-4b8a-a295-c5ba23136954)



dt.describe()

![image](https://github.com/user-attachments/assets/4c137366-b217-49d5-80dc-b379d7991c39)


dt.shape

![image](https://github.com/user-attachments/assets/403967f2-5073-4e26-a8a3-ad4543b4b53b)


dt.nunique()

![image](https://github.com/user-attachments/assets/27f7875b-2a01-444c-b371-fbee139986ec)


dt["Survived"].value_counts()

![image](https://github.com/user-attachments/assets/a28842bd-3620-458e-8811-2ab33a2e110d)


per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)

per

![image](https://github.com/user-attachments/assets/8bd99077-a9ba-4077-b78f-41a66ed81c8b)


sns.countplot(data=dt,x="Survived")

![image](https://github.com/user-attachments/assets/fc1d6665-6afb-4f75-ab6b-d9e7e224efae)


dt

![image](https://github.com/user-attachments/assets/467556c5-e41a-4e44-a209-eb0a1e830213)


dt.Pclass.unique()

![image](https://github.com/user-attachments/assets/7b6379bb-55c6-401f-8e27-56c572a2b488)


dt.rename(columns={'Sex':'Gender'},inplace=True)

dt

![image](https://github.com/user-attachments/assets/bb4da8dc-4f74-4354-aae9-8c9eb150e7da)


sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)

![image](https://github.com/user-attachments/assets/0ea0e856-b62f-4efa-9850-8a233d80893e)


sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")

![image](https://github.com/user-attachments/assets/c13e94b7-45f7-4b57-a11c-01a361b37c62)


dt.boxplot(column="Age",by="Survived")

![image](https://github.com/user-attachments/assets/3a2ec0be-da68-43d1-8171-b038a7aff0ed)


sns.scatterplot(x=dt["Age"],y=dt["Fare"])

![image](https://github.com/user-attachments/assets/19ab4700-199d-4b08-ae87-fa07eb017df5)


sns.jointplot(x=dt["Age"],y=dt["Fare"],data=dt)

![image](https://github.com/user-attachments/assets/8bb5f56f-e21f-40bc-9443-140114ee3bcb)


fig,ax1=plt.subplots(figsize=(8,5))

pt=sns.boxplot(ax=ax1,x="Pclass",y='Age',hue='Gender',data=dt)

![image](https://github.com/user-attachments/assets/97f267b8-660c-4206-a4de-8c978a9b1dbf)



sns.catplot(data=dt,col = "Survived", x = "Gender", hue="Pclass", kind = "count")

![image](https://github.com/user-attachments/assets/bc7bb481-7ad2-433c-9a8b-09fb57880d5f)


corr = dt.drop('PassengerId', axis=1).corr(numeric_only=True)

sns.heatmap(corr, annot=True)

plt.show()
![image](https://github.com/user-attachments/assets/556858a5-389a-4459-be47-f4ba21199f8c)



sns .pairplot(dt)


![image](https://github.com/user-attachments/assets/05510784-ab78-423b-8af9-6cf1324f129c)

![image](https://github.com/user-attachments/assets/5a9b9e86-282c-4978-944c-dbcf52f5f528)


# RESULT
        Thus we performed Exploratory Data Analysis
