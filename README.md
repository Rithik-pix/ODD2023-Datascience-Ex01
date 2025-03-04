
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

# CODE and OUTPUT
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
![image](https://github.com/user-attachments/assets/1867c6e2-c6f6-436a-88e6-ddc331853201)
```
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/65209ca6-e57a-4e55-9362-dee0ba591e12)

```
df.isnull().any()
```
![image](https://github.com/user-attachments/assets/2cc0b362-ed2d-4918-a4b9-501f1709cad2)

```
df.dropna(axis=0)
```
![image](https://github.com/user-attachments/assets/68c7ecdb-500b-431e-8835-80cddeb144f4)

```
df.dropna(axis=1)
```
![image](https://github.com/user-attachments/assets/38c4baa0-0a2d-4ca5-9d5e-dad4d0eb4091)

```
df.fillna(0)
```
![image](https://github.com/user-attachments/assets/6b6d6c7d-9761-4dc9-b677-c3fa5df43303)

```
df.fillna(method="ffill")
```
![image](https://github.com/user-attachments/assets/c1768feb-6186-4d8f-9dd6-49dba9f74210)

```
df.fillna(method="bfill")
```
![image](https://github.com/user-attachments/assets/69fe18db-2037-41c0-bfb5-1ba020a34aa4)

```
df.fillna({'GENDER':'MALE','NAME':'SRI','ADDRESS':'POONAMALEE','M1':98,'M2':87,'M3':76,'M4':92,'TOTAL':305,'AVG':89.999999})
```
![image](https://github.com/user-attachments/assets/e684a7a5-c830-4c06-b590-5b053d2dbb26)

```
import pandas as pd
ir=pd.read_csv('iris.csv')
ir
```
![image](https://github.com/user-attachments/assets/e85fe3fd-a0de-4a46-99d5-2e891fd4499a)

```
import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)
```
![image](https://github.com/user-attachments/assets/6b1c45f7-e93c-48b0-a515-290163f558e0)

```
Q1=ir.sepal_width.quantile(0.25)
Q3=ir.sepal_width.quantile(0.75)
iqr=Q3-Q1
print(iqr)
```
![image](https://github.com/user-attachments/assets/16d4780c-168f-4dc3-9e2a-35612814bdf7)

```
rid=ir[((ir.sepal_width<(Q1-1.5*iqr))|(ir.sepal_width>(Q3+1.5*iqr)))]
rid['sepal_width']
```
![image](https://github.com/user-attachments/assets/74453609-f2bf-4840-b416-3a26eaf6c93f)

```
delid=ir[~((ir.sepal_width<(Q1-1.5*iqr))|(ir.sepal_width>(Q3+1.5*iqr)))]
delid
```
![image](https://github.com/user-attachments/assets/84ef5b7d-61f1-477c-9488-5b4bcd42fa4d)

```
sns.boxplot(x='sepal_width',data=delid)
```
![image](https://github.com/user-attachments/assets/c5d9e96f-6aaf-4c36-8077-fe73cc8e67aa)

```
import matplotlib.pyplot as plt
 import pandas as pd
 import numpy as np
 import scipy.stats as stats
 dataset=pd.read_csv("heights.csv")
 dataset
```
![image](https://github.com/user-attachments/assets/cd294518-b5da-4e4c-99e1-853065c050ff)

```
 df = pd.read_csv("heights.csv")
 q1 = df['height'].quantile(0.25)
 q2 = df['height'].quantile(0.5)
 q3 = df['height'].quantile(0.75)
 iqr = q3-q1
 iqr
```

![image](https://github.com/user-attachments/assets/60c29af5-1476-4f32-8556-2598e89184a4)

```
 z = np.abs(stats.zscore(df['height']))
 z
```
![image](https://github.com/user-attachments/assets/caefaf85-5855-49f8-91ab-a411e10e13e1)

```
 df1 = df[z<3]
 df1
```
![image](https://github.com/user-attachments/assets/af4b0a71-6a0f-4d30-b86b-8b08ca256f82)


RESULT

Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method










