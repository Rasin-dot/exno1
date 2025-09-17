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

# Coding and Output:
```
import numpy as np
import pandas as pd
data=pd.read_csv("/content/SAMPLEIDS.csv")
data
```
# Output:
<img width="952" height="783" alt="image" src="https://github.com/user-attachments/assets/7dc36594-6073-4865-9a3f-4dcc5f3be215" />

```
data.head(4)
```

# Output:
<img width="941" height="237" alt="image" src="https://github.com/user-attachments/assets/66e476d0-3051-4399-9f21-b61c072701b1" />

```
data.tail(7)
```

# Output:
<img width="988" height="302" alt="image" src="https://github.com/user-attachments/assets/2acd5879-cd83-42ec-b509-8e6aa2135abb" />

```
data.isnull()
```

# Output:
<img width="832" height="747" alt="image" src="https://github.com/user-attachments/assets/edfc69bb-27d7-43d2-a3b1-2c7f6e518d18" />

```
data.notnull()
```

# Output:
<img width="933" height="751" alt="image" src="https://github.com/user-attachments/assets/fb50c7e1-8db0-42e4-a8b1-ab0112ba07c2" />

```
data.isnull().sum()
```

# Output:
<img width="278" height="502" alt="image" src="https://github.com/user-attachments/assets/4e574080-36f0-4be5-8c61-4fbb4b764502" />

```
data.isnull().any()
```

# Output:
<img width="335" height="497" alt="image" src="https://github.com/user-attachments/assets/58371d75-fe58-490f-8e96-255f4c7154d0" />

```
data.dropna(axis=1)
```

# Output:
<img width="573" height="746" alt="image" src="https://github.com/user-attachments/assets/73d1e5ba-044b-48a7-bff7-aa60f103085d" />

```
data.dropna(axis=0)
```

# Output:
<img width="888" height="487" alt="image" src="https://github.com/user-attachments/assets/8984fb17-5881-408c-ab84-6dd42dec88cc" />

```
data.fillna(0)
```

# Output:
<img width="940" height="758" alt="image" src="https://github.com/user-attachments/assets/7c44cd68-2431-4b39-9269-1b5d05b70b70" />

```
data.fillna(method="ffill")
```

# Output:
<img width="1427" height="790" alt="image" src="https://github.com/user-attachments/assets/2d305f9a-a852-4e9b-a306-eba85fb52f37" />

```
data.bfill()
```

# Output:
<img width="1015" height="752" alt="image" src="https://github.com/user-attachments/assets/0891062d-e507-4e8a-b4e4-dd12de1f92ae" />

```
data.fillna({'REGNO':0, 'NAME':'PRAVEEN'})
```

# Output:
<img width="1105" height="745" alt="image" src="https://github.com/user-attachments/assets/e18190a2-a5bd-4cbf-8abb-a2f55491e1e1" />

```
ir=pd.read_csv("/content/iris.csv")
ir
```
# Output:
<img width="740" height="481" alt="image" src="https://github.com/user-attachments/assets/2dcf909c-9bc5-4119-a6c7-1db2a6934b70" />

```
ir.describe()
```

# Output:
<img width="677" height="346" alt="Screenshot 2025-09-17 162429" src="https://github.com/user-attachments/assets/3d21bf3c-f885-4075-b6cd-735e28b1f824" />

```
import seaborn as sns
sns.boxplot(x="sepal_width",data=ir)
```

# Output:
<img width="667" height="547" alt="image" src="https://github.com/user-attachments/assets/d00cf8c7-7144-4e83-9ab9-bef7bcaa22d8" />

```
q1=ir.sepal_width.quantile(0.25)
q3=ir.sepal_width.quantile(0.75)
iqr=q3-q1
print(iqr)
```

# Output:
<img width="698" height="136" alt="image" src="https://github.com/user-attachments/assets/ed0999c6-2ccd-4a5d-9578-c1b48eee1028" />

```
rid=ir[((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
rid['sepal_width']
```

# Output:
<img width="851" height="287" alt="image" src="https://github.com/user-attachments/assets/298a7541-e151-4c48-b48b-0ead834e10e8" />


# Result
          <<include your Result here>>
