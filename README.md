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
df=pd.read_csv("/content/titanic_dataset (1).csv")
print(df)
```

![image](https://github.com/user-attachments/assets/4bfec1f6-b57f-4508-89da-fa6500080c71)

```
df.info()
df.shape
```

![image](https://github.com/user-attachments/assets/36838c96-dd0c-414d-a5de-20190caed955)

```
df.set_index("PassengerId",inplace=True)
df.describe()
```

![image](https://github.com/user-attachments/assets/936c9c74-3452-42f6-87c0-00c770faf519)

```
df.nunique()
df["Survived"].value_counts()
```

![image](https://github.com/user-attachments/assets/9f7d456f-7374-4592-9328-8048c3f362a2)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
```

![image](https://github.com/user-attachments/assets/bf53ce9d-c8fe-4187-bbda-dd78c7d00c7b)

```
import seaborn as sns 
sns.countplot(data=df,x="Survived")
```

![image](https://github.com/user-attachments/assets/d0a9f3fb-ada8-4ac1-986e-858029c8ed52)

```
df
df.Pclass.unique()
```

![image](https://github.com/user-attachments/assets/e3080cc6-1ddd-42c1-8631-cc4be491ad06)

```
sns.countplot(data=df,x='Survived')
df.Pclass.unique()
```

![image](https://github.com/user-attachments/assets/2fed4034-e766-4f4f-8e45-243b1460f4b7)

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

![image](https://github.com/user-attachments/assets/b3de43c7-b01d-4e0e-9123-f7bcd72bade5)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```

![image](https://github.com/user-attachments/assets/d904c12a-677a-43bf-b39f-d02021391416)

```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```

![image](https://github.com/user-attachments/assets/04884721-261a-4788-bc5e-dda613adc42a)

```
df.boxplot(column="Age",by="Survived")
```

![image](https://github.com/user-attachments/assets/03624bbf-75fe-490f-a62b-204b42aa4508)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

![image](https://github.com/user-attachments/assets/44c7fecc-7e8d-4712-aa55-18a045784df9)

```
sns.jointplot(x="Age",y="Fare",data=df)
```

![image](https://github.com/user-attachments/assets/8be023e8-0a34-469a-8b4d-d5d20afd0a24)

```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```

![image](https://github.com/user-attachments/assets/4751e2db-4df2-4f05-bae2-fa706f873671)

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

![image](https://github.com/user-attachments/assets/632c008a-9ab5-4190-95b1-c926407b4422)

```
numeric_df=df.select_dtypes(include=np.number)
corr=numeric_df.corr()
sns.heatmap(corr,annot=True)
```

![image](https://github.com/user-attachments/assets/c276c406-e452-4505-be52-ea264a52e17d)


```
sns.pairplot(df)
```

![image](https://github.com/user-attachments/assets/32653a0e-3716-4307-8bda-fe46fcaba853)

# RESULT 
Thus,Data Analyzing of the given dataset was successful.
