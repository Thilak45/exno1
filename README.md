# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
![image](https://github.com/Thilak45/exno1/assets/138849161/b1db36b9-87ca-41af-98ff-80165fe4f674)

```
print(df.head(7))
```
![image](https://github.com/Thilak45/exno1/assets/138849161/a21fd583-17c6-4051-98e7-94fe9fb5371c)

```
print(df.tail(2))
```
![image](https://github.com/Thilak45/exno1/assets/138849161/e15b0107-3f20-4b47-951c-97eff7b94da9)

```
df.info()
```
![image](https://github.com/Thilak45/exno1/assets/138849161/585b7073-c625-4ddf-b6f8-b61be7dd7df4)
```
print(df.describe())
```
![image](https://github.com/Thilak45/exno1/assets/138849161/27a7bb56-3138-49c4-9446-43bbbbad32f3)
```
df.isnull().sum()
```
![image](https://github.com/Thilak45/exno1/assets/138849161/8b61de6e-ded4-427e-a39d-98eec26f4de3)

```
df.nunique()
```
![image](https://github.com/Thilak45/exno1/assets/138849161/f8f8d85f-fd12-4883-9428-5f4cefb8a4e9)

```
mn=df.TOTAL.mean()
mn
```
![image](https://github.com/Thilak45/exno1/assets/138849161/a787f3f8-4edc-4de5-b443-b24e90b3ccb3)

```
df.TOTAL.fillna(mn,inplace=True)
df
```
![image](https://github.com/Thilak45/exno1/assets/138849161/86370334-5286-400d-a4d3-6b095b8a49ca)
```
min=df.M4.min()
min
```
![image](https://github.com/Thilak45/exno1/assets/138849161/49619005-d4f8-4914-b3bf-ed8a8e98d334)
```
df.M4.fillna(min,inplace=True)
df
```
![image](https://github.com/Thilak45/exno1/assets/138849161/1da2745b-dfc1-4e5a-9c75-4bb276916dc1)


![image](https://github.com/Thilak45/exno1/assets/138849161/22115c93-0e2e-4afe-b616-0f1dcb4419a0)
```
import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
![image](https://github.com/Thilak45/exno1/assets/138849161/030652b9-9f0c-4aa8-b142-1930c3864f44)
```
sns.boxplot(data=af)
```
![image](https://github.com/Thilak45/exno1/assets/138849161/0283e53a-5485-411d-bde3-3fb74ca5d652)


```
sns.scatterplot(data=af)
```
![image](https://github.com/Thilak45/exno1/assets/138849161/3a5c60b9-7828-4c42-a8a4-098b59b62b4d)
```
q1=af.quantile(0.25)
q2=af.quantile(0.50)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
low=q1-1.5*iqr
low
high=q3+1.5*iqr
high
```
![image](https://github.com/Thilak45/exno1/assets/138849161/bb01c692-ebc6-4d0a-9c64-ff9baa20ea34)
```
af=af[((af>=low)&(af<=high))]
af
```
![image](https://github.com/Thilak45/exno1/assets/138849161/9ba4bcca-3d36-4542-a50b-4346329792dd)

```
af.dropna()
```
![image](https://github.com/Thilak45/exno1/assets/138849161/2ffc40e4-c07d-42ac-8cf0-574d4ccd5e5e)
```
sns.boxplot(data=af)
```
![image](https://github.com/Thilak45/exno1/assets/138849161/670f89af-a4f3-49bc-ba24-4d43e537b074)

```
sns.scatterplot(data=af)
```
![image](https://github.com/Thilak45/exno1/assets/138849161/ff325e16-d146-4c32-88ac-1520b3695625)

```
data=[1,12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,102,105]
df=pd.DataFrame(data)
df
```
![image](https://github.com/Thilak45/exno1/assets/138849161/b4a09067-cf2f-4f47-82d7-3961945f0b38)
```
import numpy as np
from scipy import stats
z=np.abs(stats.zscore(df))
z
```
![image](https://github.com/Thilak45/exno1/assets/138849161/da9b2532-4b69-44e7-bd31-8bfb59809c15)


# Result
Thus the given program executed successfully.
