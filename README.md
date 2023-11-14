# EX 04 MULTIVARIATE ANALYSIS
### Aim:
To perform Multivariate EDA on the given data set.
### Explanation:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
### Algorithm:
- Step1: Import the built libraries required to perform EDA and outlier removal.
- Step2: Read the given csv file.
- Step3: Convert the file into a dataframe and get information of the data.
- Step4: Return the objects containing counts of unique values using (value_counts()).
- Step5: Plot the counts in the form of Histogram or Bar Graph.
```
Developed By: 212222230141
Register Number: SHABREENA VINCENT
```
### Program:
- SuperStore.csv
```Python
import pandas as pd
import seaborn as sns
from scipy import stats
import matplotlib.pyplot as plt
df=pd.read_csv('SuperStore.csv')
df.describe()
df.isnull().sum()
df.info()
# FILLING NULL VALUES
df['Postal Code']=df['Postal Code'].fillna(df['Postal Code'].mode()[0])
sns.boxplot(df)
sns.scatterplot(x=df['Region'],y=df['Sales'])
plt.figure(figsize=(10,3))
sns.barplot(x=df['State'],y=df['Sales'])
plt.xticks(rotation=90)
sns.heatmap(df.corr(),annot=True)
sns.displot(df,x='Region',hue="Category")
```
- Output: (SuperStorE.csv)
<img height=20% width=35% src="https://github.com/ROHITJAIND/EX-04-MULTIVARIATE-ANALYSIS/assets/118707073/319a4805-b9d3-4a61-9500-10fa72a9ea55">
<img height=20% width=25% src="https://github.com/ROHITJAIND/EX-04-MULTIVARIATE-ANALYSIS/assets/118707073/b5522c34-2e4e-4083-8115-1c57861d9971">
<img height=20% width=35% src="https://github.com/ROHITJAIND/EX-04-MULTIVARIATE-ANALYSIS/assets/118707073/10438e60-a3cc-437a-8aff-26f2820f5b41">

<img height=25% width=40% src="https://github.com/ROHITJAIND/EX-04-MULTIVARIATE-ANALYSIS/assets/118707073/5f012279-55d1-4d88-8ca3-e560607be7f5">
<img height=25% width=50% src="https://github.com/ROHITJAIND/EX-04-MULTIVARIATE-ANALYSIS/assets/118707073/6d913e29-1e8b-4398-8c36-b1a3579fabcb">

<img height=25% width=100% src="https://github.com/ROHITJAIND/EX-04-MULTIVARIATE-ANALYSIS/assets/118707073/10ad78c1-f66b-4e37-8d4a-a0c63366f360">

<img height=25% width=40% src="https://github.com/ROHITJAIND/EX-04-MULTIVARIATE-ANALYSIS/assets/118707073/c7b8247f-c1d5-457c-81d3-57a414d500f2">
<img height=25% width=50% src="https://github.com/ROHITJAIND/EX-04-MULTIVARIATE-ANALYSIS/assets/118707073/f4beff7c-1e30-436e-9827-d285fef2c576">

- Diabetes.csv
```Python
import pandas as pd
import seaborn as sns
from scipy import stats
import matplotlib.pyplot as plt
df=pd.read_csv('diabetes.csv')
df.describe()
df.isnull().sum()
# REMOVING OUTLIER
z = np.abs(stats.zscore(df['Glucose']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['BloodPressure']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['SkinThickness']))
df=df[(z<3)]
z = np.abs(stats.zscore(dfc['BMI']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['Insulin']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['DiabetesPedigreeFunction']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['Age']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['Outcome']))
df=df[(z<3)]
sns.boxplot(data=dfc)
plt.xticks(rotation=90)
sns.boxplot(data=dfc)
plt.xticks(rotation=90)
sns.scatterplot(x=df['Glucose'], y=df['BloodPressure'], hue=df['Outcome'])
Age=df.loc[:,["Age","BMI"]]
Age=Age.groupby(by=["Age"]).sum().sort_values(by="BMI")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=Age.index,y="BMI",data=Age)
sns.boxplot(x=df['DiabetesPedigreeFunction'],y=df['Insulin'])
sns.displot(df, x="Glucose", hue="Outcome")
df.corr()
sns.heatmap(df.corr(),annot=True)
```
- Output (Diabetes.csv):

<img height=10% width=75% src="https://github.com/ROHITJAIND/EX-04-MULTIVARIATE-ANALYSIS/assets/118707073/fee952ae-9cbd-4295-8f98-a58f7e0f7d17">  
<img height=10% width=20% src="https://github.com/ROHITJAIND/EX-04-MULTIVARIATE-ANALYSIS/assets/118707073/ea560b82-9523-408b-9915-097221aae2bf">

<img height=25% width=45% src="https://github.com/ROHITJAIND/EX-04-MULTIVARIATE-ANALYSIS/assets/118707073/bc1c32be-0000-47f3-a330-ff838e101f90">
<img height=25% width=45% src="https://github.com/ROHITJAIND/EX-04-MULTIVARIATE-ANALYSIS/assets/118707073/46028ead-2c8c-49fb-b546-ec4a3819e97d">

<img height=25% width=45% src="https://github.com/ROHITJAIND/EX-04-MULTIVARIATE-ANALYSIS/assets/118707073/4369728a-44b6-444c-8acb-d137136ef7a0">
<img height=25% width=45% src="https://github.com/ROHITJAIND/EX-04-MULTIVARIATE-ANALYSIS/assets/118707073/503045a2-d013-42d4-b786-f3dd91af053d">

<img height=25% width=45% src="https://github.com/ROHITJAIND/EX-04-MULTIVARIATE-ANALYSIS/assets/118707073/31dfea60-84a2-4e07-bca4-d2520c65db81">
<img height=25% width=45% src="https://github.com/ROHITJAIND/EX-04-MULTIVARIATE-ANALYSIS/assets/118707073/c17932ac-ff8a-4c2a-865e-c114a80e31c4">

### RESULT:
Thus we have read the given data and performed the multivariate analysis with different types of plots.
