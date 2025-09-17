# EX.NO: 2 DS
## AIM:
To perform Exploratory Data Analysis on the given data set.
      
## EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
## ALGORITHM:
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
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
<img width="1752" height="585" alt="image" src="https://github.com/user-attachments/assets/55d864e7-88a9-4f48-b608-225b95539d3e" />

```
df.info()
```
<img width="1330" height="570" alt="image" src="https://github.com/user-attachments/assets/5584e86e-a9a0-4564-89ab-b7374c7a227d" />

```
df.describe()
```
<img width="1186" height="405" alt="image" src="https://github.com/user-attachments/assets/41bae79a-84dc-4913-a7ba-2c4ee3c109de" />

```
df.dtypes
```
<img width="716" height="587" alt="image" src="https://github.com/user-attachments/assets/0d3821dd-266b-4dce-a85c-6e5265af1611" />

```
df.shape
```
<img width="233" height="61" alt="image" src="https://github.com/user-attachments/assets/657a466f-66db-491e-8963-f4dd20fd440f" />

```
df['Age'].value_counts()
```
<img width="535" height="671" alt="image" src="https://github.com/user-attachments/assets/217c9146-4b0f-46f2-8c2c-b847c967dfa2" />

```
df.nunique()
```
<img width="580" height="606" alt="image" src="https://github.com/user-attachments/assets/1e3a0a41-20ce-4c45-b99a-e3b6629d9648" />

```
sns.countplot(data=df,x='Survived')
```
<img width="953" height="719" alt="image" src="https://github.com/user-attachments/assets/e3b29bfb-b34a-401f-a80e-0d5f9dd5d595" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
<img width="1752" height="543" alt="image" src="https://github.com/user-attachments/assets/78348d92-78af-41a2-ac98-d6572095f9c1" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df)
```
<img width="1606" height="802" alt="image" src="https://github.com/user-attachments/assets/92f5766a-90fb-4f2e-bf3f-4d05825b0c20" />

```
df.boxplot(column="Age",by="Survived")
```
<img width="925" height="781" alt="image" src="https://github.com/user-attachments/assets/624bfe1f-c2ef-4a28-b698-35b98e73c7cc" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
<img width="1017" height="753" alt="image" src="https://github.com/user-attachments/assets/bd65b16b-70fc-43fe-8dd3-2c1e28d9b8da" />

```
plt=sns.boxplot(x="Pclass",y="Age",hue="Gender",data=df)
```
<img width="946" height="673" alt="image" src="https://github.com/user-attachments/assets/a6e91fb9-33e4-4efd-b2bb-ba5225430f2c" />

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
<img width="1641" height="804" alt="image" src="https://github.com/user-attachments/assets/b603bef5-c95e-46fe-87a9-a9b20b49372d" />

```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
<img width="1115" height="806" alt="image" src="https://github.com/user-attachments/assets/a59d2867-a48f-4eb6-b6ec-f3630cfa3c9f" />


## RESULT
Thus, the outputs verifies that the data set has been applied the EDA process and methods.
