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
Register Number: shabreena vincent
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

```
