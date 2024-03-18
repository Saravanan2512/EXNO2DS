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
import matplotlib.pyplot as pit
import seaborn as sns
dt=pd.read_csv("titanic.csv")
dt
```
![image](https://github.com/Saravanan2512/EXNO2DS/assets/144979117/e25531ea-5f77-4d94-bc7b-6ee40e621d73)
```
dt.info()
```
![image](https://github.com/Saravanan2512/EXNO2DS/assets/144979117/42d465ea-0a41-4a25-875b-337c944c2aaf)
```
dt.shape
```
![image](https://github.com/Saravanan2512/EXNO2DS/assets/144979117/39550dc0-9501-4a8a-8fd7-437d10c00ab5)
```
import pandas as pd
dt=pd.read_csv("titanic.csv")
dt.set_index("PassengerId",inplace=True)
print(dt.set_index)
```
![image](https://github.com/Saravanan2512/EXNO2DS/assets/144979117/9f028a22-3d77-43ba-aee7-19945d0075bc)

```
dt.nunique()
```
![image](https://github.com/Saravanan2512/EXNO2DS/assets/144979117/258d9b83-a160-44a9-b64d-e6524e9750d1)

```
dt["Survived"].value_counts()
```
![image](https://github.com/Saravanan2512/EXNO2DS/assets/144979117/e4b51073-c9d7-466d-8dec-584c950a89c0)

```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![image](https://github.com/Saravanan2512/EXNO2DS/assets/144979117/ebb41f2b-39f1-48c1-a7a2-ee05eba4d542)

```
sns.countplot(data=dt,x="Survived")
```
![image](https://github.com/Saravanan2512/EXNO2DS/assets/144979117/ed22b30c-2e23-44f6-85b5-0c67efc5992f)

```
dt
```
![image](https://github.com/Saravanan2512/EXNO2DS/assets/144979117/dd7ece90-dcdd-44c1-8481-a46e2fab3c9b)

```
import pandas as pd
dt=pd.read_csv("titanic.csv")
dt.rename(columns = {'Sex':'Gender'},inplace = True)
dt
```
![image](https://github.com/Saravanan2512/EXNO2DS/assets/144979117/66299e6a-fc4c-4d3a-b70c-e84489e7e203)

```
import seaborn as sns
dt=pd.read_csv("titanic.csv")
sns.catplot(x="Sex",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
![image](https://github.com/Saravanan2512/EXNO2DS/assets/144979117/8a5e56a6-b47f-48c4-bce4-991014bf9d77)

```
sns.catplot(x='Survived',hue="Sex",data=dt,kind="count")
```
![image](https://github.com/Saravanan2512/EXNO2DS/assets/144979117/31321763-e892-4d88-bb36-d0e7609980da)

```
dt.boxplot(column="Age",by="Survived")
```
![image](https://github.com/Saravanan2512/EXNO2DS/assets/144979117/b298567c-4930-4fa0-a658-fa4d51afa600)

```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![image](https://github.com/Saravanan2512/EXNO2DS/assets/144979117/34f11cf9-bb50-4ac0-923e-6df29c9c8bdf)

```
import matplotlib.pyplot as plt
fig, ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Sex',data=dt)
```
![image](https://github.com/Saravanan2512/EXNO2DS/assets/144979117/e09615c1-f9ac-47c6-ac88-45e6abb50801)

```
sns.catplot(data=dt,col="Survived",x="Sex",hue="Pclass",kind="count")
```
![image](https://github.com/Saravanan2512/EXNO2DS/assets/144979117/b07f59f0-1567-49cf-b71f-1d2f68314043)

```
#co-relation
import seaborn as sns
corr=dt.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/Saravanan2512/EXNO2DS/assets/144979117/41bdc448-29bf-4c8c-8976-3e76c9960089)

```
sns.pairplot(dt)
```
![image](https://github.com/Saravanan2512/EXNO2DS/assets/144979117/cf48a680-9643-4707-b650-8b97d4739057)


# RESULT
  The Code is executed Successfully
