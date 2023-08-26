# Ex-01_DS_Data_Cleansing


## AIM
To read the given data and perform data cleaning and save the cleaned data to a file. 

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. 
Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information. 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Get the information about the data
### STEP 3
Remove the null values from the data
### STEP 4
Save the Clean data to the file

# CODE 
## CODE FOR DATA SET:
```
import pandas as pd
import numpy as np
from google.colab import files
upload = files.upload()
df=pd.read_csv('Data_set.csv')
df.isnull().sum()
df.shape
df['show_name'].nunique()
df=df.dropna(subset=['show_name'])
df['aired_on'].value_counts()
df['aired_on']=df['aired_on'].fillna(df['aired_on'].mode()[0])
df['original_network']=df['original_network'].fillna(df['original_network'].mode()[0])
df['rating']=df['rating'].fillna(df['rating'].mode()[0])
df=df.dropna(subset=['current_overall_rank'])
df['watchers']=df['watchers'].fillna(df['watchers'].median())
df_reset=df.reset_index(drop=True)
df=df.drop(columns=['index','level_0'])
df
```
## CODE FOR LOAN DATA:
```
import pandas as pd
import numpy as np
from google.colab import files
uploaded=files.upload()
df=pd.read_csv('Loan_data.csv')
df.info()
df.head()
df['Gender']=df['Gender'].fillna('Female')
df.head()
df['Dependents']=df['Dependents'].fillna(method='ffill')
df.head()
df['Self_Employed']=df['Self_Employed'].fillna(df['Self_Employed'].mode()[0])
df.head()
df=df.dropna(subset=['LoanAmount'])
df.head()
df['Loan_Amount_Term']=df['Loan_Amount_Term'].fillna(df['Loan_Amount_Term'].median())
df.head()
df['Credit_History']=df['Credit_History'].fillna(df['Credit_History'].min())
df.head()
df.info()
```
## OUTPUT FOR DATA SET:
![image](https://github.com/mathes6112004/ODD2023-Datascience-Ex01/assets/119477782/d41f1400-5b6f-4dde-93b2-9e9a6f50d7af)

![image](https://github.com/mathes6112004/ODD2023-Datascience-Ex01/assets/119477782/c983e169-f97e-4fb5-9879-239c71d3d91d)

![image](https://github.com/mathes6112004/ODD2023-Datascience-Ex01/assets/119477782/ec7fe182-522c-49be-9f4a-3a81c45d8f65)

![image](https://github.com/mathes6112004/ODD2023-Datascience-Ex01/assets/119477782/165da36f-7e10-4bb5-a333-6c1dd979122a)

## OUTPUT FOR LOAN DATA:
![image](https://github.com/mathes6112004/ODD2023-Datascience-Ex01/assets/119477782/a54309af-ab9d-47e7-9115-d35f72c78758)

![image](https://github.com/mathes6112004/ODD2023-Datascience-Ex01/assets/119477782/705df792-ff8b-485e-8e00-cdc7e3a3a2a8)

![image](https://github.com/mathes6112004/ODD2023-Datascience-Ex01/assets/119477782/be14a02f-7649-4cc8-8317-ffa460ef1c68)

![image](https://github.com/mathes6112004/ODD2023-Datascience-Ex01/assets/119477782/a873bf51-28b2-47e6-9f12-f6ba92497cd3)


![image](https://github.com/mathes6112004/ODD2023-Datascience-Ex01/assets/119477782/6e52748a-a6e3-4799-be44-ae2029b13ca9)

![image](https://github.com/mathes6112004/ODD2023-Datascience-Ex01/assets/119477782/9576b04c-5456-4a98-b5ed-078bd2178bb4)

![image](https://github.com/mathes6112004/ODD2023-Datascience-Ex01/assets/119477782/0a5e915c-4e17-4f38-9e18-e2be1ae2a9b4)

![image](https://github.com/mathes6112004/ODD2023-Datascience-Ex01/assets/119477782/8efa842c-053b-4c0e-b3dc-f901e5ba97b2)

![image](https://github.com/mathes6112004/ODD2023-Datascience-Ex01/assets/119477782/5a6c445d-9e95-4c71-baf3-d6294d311b46)

## RESULT:
Thus,the given data is read,cleansed and the cleaned data is saved into the file.









