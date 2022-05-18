# EX-05-Feature-Generation
## AIM
To read the given data and perform Feature Generation process and save the data to a file.

## Explanation
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.

## ALGORITHM
STEP 1
Read the given Data

STEP 2
Clean the Data Set using Data Cleaning Process

STEP 3
Apply Feature Generation techniques to all the feature of the data set

STEP 4
Save the data to the file

## CODE:

Developed By: MOTHESH.M
Register No: 212221230066
Dataset 1 - Data.csv

## Code:
```
import pandas as pd
df=pd.read_csv("data.csv")
df
from sklearn.preprocessing import LabelEncoder, OrdinalEncoder
oe=OrdinalEncoder()
oe.fit_transform(df[["Ord_1"]])
temp=['Cold','Warm','Hot','Very Hot']
enc=OrdinalEncoder(categories=[temp])
enc
enc.fit_transform(df[['Ord_1']])
df1=df.copy()
df1["Ord_1"]=enc.fit_transform(df[["Ord_1"]])
df1
oe1=OrdinalEncoder()
oe.fit_transform(df[["Ord_2"]])
studies=['High School','Diploma','Bachelors','Masters','PhD']
enc1=OrdinalEncoder(categories=[studies])
enc1
enc1.fit_transform(df[['Ord_2']])
df2=df1.copy()
df2["Ord_2"]=enc1.fit_transform(df[["Ord_2"]])
df2
pip install category_encoders
from category_encoders import BinaryEncoder
be=BinaryEncoder()
newdata=be.fit_transform(df2["bin_1"])
newdata
df3=df2.copy()
df3["bin_1"]=be.fit_transform(df[["bin_1"]])
df3
be1=BinaryEncoder()
newdata2=be1.fit_transform(df3['bin_2'])
newdata2
df4=df3.copy()
df4["bin_2"]=be1.fit_transform(df[["bin_2"]])
df4
from sklearn.preprocessing import OneHotEncoder
ohe=OneHotEncoder(sparse=False)
ohe.fit_transform(df4[['City']])
num=ohe.fit_transform(df4[['City']])
num
df4
from sklearn.preprocessing import LabelEncoder, OrdinalEncoder
le=LabelEncoder()
le.fit_transform(df4[['City']])
df5=df4.copy()
df5["City"]=le.fit_transform(df4[['City']])
df5

from sklearn.preprocessing import MinMaxScaler
scaler=MinMaxScaler()
df6=pd.DataFrame(scaler.fit_transform(df5),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df6

from sklearn.preprocessing import StandardScaler
Stdscaler=StandardScaler()
df7=pd.DataFrame(Stdscaler.fit_transform(df5),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df7

from sklearn.preprocessing import MaxAbsScaler
maxabsscaler=MaxAbsScaler()
df8=pd.DataFrame(maxabsscaler.fit_transform(df5),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df8

from sklearn.preprocessing import RobustScaler
rscaler = RobustScaler()
df9=pd.DataFrame(rscaler.fit_transform(df5),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df9
```
## OUTPUT:
### DataFrame(data.csv):
![a1](https://user-images.githubusercontent.com/94170892/169093089-09497e94-d22a-47b4-897e-e804d1f437d5.png)
![a2](https://user-images.githubusercontent.com/94170892/169093108-f260e865-c32b-4fdc-8a71-96b36916d58a.png)
![a3](https://user-images.githubusercontent.com/94170892/169093134-79b56491-46af-4f29-8d23-1dab7a7b39f7.png)
![a4](https://user-images.githubusercontent.com/94170892/169093170-cf6122ef-93f7-4317-ad60-673f97e80889.png)

### Applying Ordinal Encoding Method in column- Ord_2::
![a5](https://user-images.githubusercontent.com/94170892/169093229-f859f10f-b5d8-4253-8e27-7c307da88053.png)
![a6](https://user-images.githubusercontent.com/94170892/169093265-497a1dd0-35ae-4174-9df9-071f0bc68d17.png)

### After applying Ordinal Encoding Method in column- Ord_2::
![a7](https://user-images.githubusercontent.com/94170892/169093398-55af6d7c-94fb-4ced-9c4d-b09212ac9edf.png)

### Applying Binary Encoding Method in column- bin_1::
![a8](https://user-images.githubusercontent.com/94170892/169093471-59b6a416-0604-4b18-a214-2aa67d0973a3.png)

### Applying Binary Encoding Method in column- bin_1:
![a9](https://user-images.githubusercontent.com/94170892/169093545-b7594feb-37ba-4e2f-8cc2-2123503ddca5.png)

### Applying Binary Encoding Method in column- bin_2:
![a10](https://user-images.githubusercontent.com/94170892/169093680-f7912e4b-c024-4974-a420-d7e5b9a91b6e.png)

### After Binary Encoding Method in column- bin_2:
![a11](https://user-images.githubusercontent.com/94170892/169093756-c3272a3d-53e8-46ce-b1b8-d39e9ade10d2.png)

### One Hot Encoding Method:
![a12](https://user-images.githubusercontent.com/94170892/169093813-e5535c14-f865-4c67-9900-942bdd6b45f5.png)
![a13](https://user-images.githubusercontent.com/94170892/169093841-73762fea-6caf-4abe-91dd-c598e73882c3.png)

### Final DataSet after applying Encoding Methods:
![a13](https://user-images.githubusercontent.com/94170892/169093917-12e3a2cc-f648-49c9-8657-e7aa5a22fef2.png)

## Feature Scaling Techniques:
Feature scaling is a method used to normalize the range of independent variables or features of data. In data processing, it is also known as data normalization and is generally performed during the data preprocessing step.
```
1.Min-Max Scaler.
2.Standard Scaler.
3.Max Abs Scaler.
4.Robust Scaler.
```

### Feature Scaling - Min-Max Scaler Technique:
![a14](https://user-images.githubusercontent.com/94170892/169094094-268a670b-c06a-41fc-a422-5b2186a75854.png)

### Feature Scaling - Standard Scaler Technique:
![a15](https://user-images.githubusercontent.com/94170892/169094167-ac978b14-88ee-4778-b713-8179ab8c8bda.png)

### Feature Scaling - Max Abs Scaler Technique:
![a16](https://user-images.githubusercontent.com/94170892/169094233-a487845b-ffd2-4d6b-b11c-f53bc5db9e9a.png)

### Feature Scaling - Robust Scaler Technique:
![a17](https://user-images.githubusercontent.com/94170892/169094304-733a9f25-cc1a-4543-a862-65181434ce38.png)

## Dataset 2 - Encoding Data.csv
## Code:
```
import pandas as pd
df=pd.read_csv("Encoding Data.csv")
df
from sklearn.preprocessing import LabelEncoder, OrdinalEncoder
oe=OrdinalEncoder()
oe.fit_transform(df[["ord_2"]])
temp=['Cold','Warm','Hot']
enc=OrdinalEncoder(categories=[temp])
enc
enc.fit_transform(df[['ord_2']])
df1=df.copy()
df1["ord_2"]=enc.fit_transform(df[["ord_2"]])
df1
oe1=OrdinalEncoder()
oe.fit_transform(df[["nom_0"]])
color=['Green','Blue','Red']
enc1=OrdinalEncoder(categories=[color])
enc1
enc1.fit_transform(df[['nom_0']])
df2=df1.copy()
df2["nom_0"]=enc1.fit_transform(df[["nom_0"]])
df2
pip install category_encoders
from category_encoders import BinaryEncoder
be=BinaryEncoder()
newdata=be.fit_transform(df2["bin_1"])
newdata
df3=df2.copy()
df3["bin_1"]=be.fit_transform(df[["bin_1"]])
df3
be1=BinaryEncoder()
newdata2=be1.fit_transform(df3['bin_2'])
newdata2
df4=df3.copy()
df4["bin_2"]=be1.fit_transform(df[["bin_2"]])
df4

from sklearn.preprocessing import MinMaxScaler
scaler=MinMaxScaler()
df5=pd.DataFrame(scaler.fit_transform(df4),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df5

from sklearn.preprocessing import StandardScaler
Stdscaler=StandardScaler()
df6=pd.DataFrame(Stdscaler.fit_transform(df4),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df6

from sklearn.preprocessing import MaxAbsScaler
maxabsscaler=MaxAbsScaler()
df7=pd.DataFrame(maxabsscaler.fit_transform(df4),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df7

from sklearn.preprocessing import RobustScaler
rscaler = RobustScaler()
df8=pd.DataFrame(rscaler.fit_transform(df4),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df8
```

## Output:
### DataFrame (Encoding Data.csv):
![d1](https://user-images.githubusercontent.com/94170892/169094572-d8b12b23-8da4-43c0-870e-281be5a89957.png)

### Applying Ordinal Encoding Method in column - ord_2:
![d2](https://user-images.githubusercontent.com/94170892/169094699-2b42d97a-3d25-466f-869c-20a8c5c4ecd1.png)
![d3](https://user-images.githubusercontent.com/94170892/169094732-44e57f63-8ddd-4642-9827-8dc4ce8ef613.png)

### After applying Ordinal Encoding Method in column - ord_2:
![d4](https://user-images.githubusercontent.com/94170892/169094779-b7930dc3-0a42-4780-97d3-649f75f36072.png)

### Applying Ordinal Encoding Method in column - nom_0:
![d5](https://user-images.githubusercontent.com/94170892/169094834-5f9282fa-d623-45b7-bda5-b6f6cf09567d.png)
![d6](https://user-images.githubusercontent.com/94170892/169094858-963f6b11-1ad9-4a5d-8a65-e8a2167eb542.png)

### After applying Ordinal Encoding Method in column - nom_0:
![d7](https://user-images.githubusercontent.com/94170892/169094918-2a526f1a-5ac8-4c6a-949b-b52b39d046c0.png)

### Applying Binary Encoding Method in column - bin_1:
![d8](https://user-images.githubusercontent.com/94170892/169094968-c4248045-8c75-4187-9481-aac77a093eeb.png)

### After applying Binary Encoding in column- bin_1:
![d9](https://user-images.githubusercontent.com/94170892/169095027-6abce7a7-1f69-4db0-b25d-ee70a2760466.png)

### Applying Binary Encoding Method in column - bin_2:
![d10](https://user-images.githubusercontent.com/94170892/169095095-98f86218-7d89-4935-ad1b-3371e32eb758.png)

### After applying Binary Encoding in column- bin_2:
![d11](https://user-images.githubusercontent.com/94170892/169095158-84dd36d6-a757-4c81-98cd-49e4764ab042.png)

### Final DataSet after applying Encoding Methods:
![d11](https://user-images.githubusercontent.com/94170892/169095220-8a37c6f1-7b34-4832-9a7f-0e7510e69169.png)

## Feature Scaling Techniques:
```
1.Min-Max Scaler.
2.Standard Scaler.
3.Max Abs Scaler.
4.Robust Scaler.
```

### Feature Scaling - Min-Max Scaler Technique:
![d12](https://user-images.githubusercontent.com/94170892/169095358-4f8d3c83-4440-411b-a5f4-2834c7dbbf33.png)

### Feature Scaling - Standard Scaler Technique:
![d13](https://user-images.githubusercontent.com/94170892/169095421-a921c299-e894-4e00-9009-b5635ff86021.png)

### Feature Scaling - Max Abs Scaler Technique:
![d14](https://user-images.githubusercontent.com/94170892/169095465-31e1462e-dba8-4543-9365-05038fb28fd1.png)

### Feature Scaling - Robust Scaler Technique:
![d15](https://user-images.githubusercontent.com/94170892/169095523-db41a182-a951-437d-8552-392f8481a147.png)

## Dataset 3 - titanic_dataset.csv
## Code:
```
import pandas as pd
df=pd.read_csv("titanic_dataset.csv")
df
df.drop("Name",axis=1,inplace=True)
df
df.drop("Cabin",axis=1,inplace=True)
df
df.drop("Ticket",axis=1,inplace=True)
df
df.info()
df.isnull().sum()
df["Age"]=df["Age"].fillna(df["Age"].median())
df["Embarked"]=df["Embarked"].fillna(df["Embarked"].mode()[0])
df.boxplot()
df.isnull().sum()
df

from sklearn.preprocessing import LabelEncoder, OrdinalEncoder
oe=OrdinalEncoder()
oe.fit_transform(df[["Embarked"]])
embark=['S','C','Q']
enc=OrdinalEncoder(categories=[embark])
enc
enc.fit_transform(df[['Embarked']])
df1=df.copy()
df1["Embarked"]=enc.fit_transform(df[["Embarked"]])
df1
pip install category_encoders
from category_encoders import BinaryEncoder
be=BinaryEncoder()
newdata=be.fit_transform(df1["Sex"])
newdata
df2=df1.copy()
df2["Sex"]=be.fit_transform(df1[["Sex"]])
df2

from sklearn.preprocessing import MinMaxScaler
scaler=MinMaxScaler()
df3=pd.DataFrame(scaler.fit_transform(df2),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked'])
df3

from sklearn.preprocessing import StandardScaler
Stdscaler=StandardScaler()
df4=pd.DataFrame(Stdscaler.fit_transform(df2),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked'])
df4

from sklearn.preprocessing import MaxAbsScaler
maxabsscaler=MaxAbsScaler()
df5=pd.DataFrame(maxabsscaler.fit_transform(df2),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked'])
df5

from sklearn.preprocessing import RobustScaler
rscaler = RobustScaler()
df6=pd.DataFrame(rscaler.fit_transform(df2),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked'])
df6
```
## Output:
### DataFrame - (titanic_dataset.csv):
![t1](https://user-images.githubusercontent.com/94170892/169095691-b79362a0-e6b6-4f32-9417-1e4f7e6806e9.png)

### Droping "Name" column from DataFrame:
![t2](https://user-images.githubusercontent.com/94170892/169095754-a61f6738-4f52-4674-89c8-92e27fcc1d07.png)

### Droping "Cabin" and "Ticket" column from DataFrame:
![t4](https://user-images.githubusercontent.com/94170892/169095816-5c9ee822-fb23-4cfe-8178-936a7a1a87c7.png)

### Non Null-data Count:
![t5](https://user-images.githubusercontent.com/94170892/169095878-68928736-dd72-4453-a3e5-b0acaacbdc44.png)

### Sum of null data present in each column:
![t6](https://user-images.githubusercontent.com/94170892/169095901-d32d1fe3-0797-4b61-b74f-89efb7459fb8.png)

### Handling Null data in Column "Age" and "Embarked" :
![t8](https://user-images.githubusercontent.com/94170892/169096014-7d5e7973-8795-4eb2-a1f5-ace7e5f64f93.png)

### Data Frame after removing column - Age,Cabin,Ticket:
![t9](https://user-images.githubusercontent.com/94170892/169096129-563bbe35-7c16-4978-b683-62f12cdc061e.png)

## Feature Generation Process:
```
1.Ordinal Encoder.
2.Binary Encoder.
3.One Hot Encoder.
```

### Applying Ordinal Encoding Method in column - Embarked:
![t10](https://user-images.githubusercontent.com/94170892/169096283-cc820375-c6b0-44dc-aaee-a2762d3c61e4.png)
![t11](https://user-images.githubusercontent.com/94170892/169096326-a92ce58e-54e1-4d68-a3e7-52cc724757ea.png)

### After applying Ordinal Encoding Method in column - Embarked:
![t12](https://user-images.githubusercontent.com/94170892/169096433-c11a8734-2b5d-4251-b37c-ef4613fc8a6e.png)

### Applying Binary Encoding Method in column - Sex:
![t13](https://user-images.githubusercontent.com/94170892/169096491-5dc97fb7-a820-437f-b2c7-8c672e1d991c.png)

## After applying Binary Encoding in column- Sex:
![t14](https://user-images.githubusercontent.com/94170892/169096539-139412a0-7e30-4ffa-a09f-06c37c977faa.png)

### Feature Scaling Techniques:
```
1.Min-Max Scaler.
2.Standard Scaler.
3.Max Abs Scaler.
4.Robust Scaler.
```

### Feature Scaling - Min-Max Scaler Technique:
![t15](https://user-images.githubusercontent.com/94170892/169096703-971c16fc-6934-4a26-9ec6-8248522fb1ba.png)

### Feature Scaling - Standard Scaler Technique:
![t16](https://user-images.githubusercontent.com/94170892/169096749-21be84eb-a6cf-4a73-816e-1079a21c1492.png)

### Feature Scaling - Max Abs Scaler Technique:
![t17](https://user-images.githubusercontent.com/94170892/169096807-85bbc433-3edc-4ce1-8ebc-aab43e2a2f34.png)

### Feature Scaling - Robust Scaler Technique:
![t18](https://user-images.githubusercontent.com/94170892/169096857-81b4c3ab-c206-4a52-9223-a61f4bf29f5c.png)

## Result:
Feature Generation process and Feature Scaling process is applied to the given data frame sucessfully.
