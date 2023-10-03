# AIM
To read the given data and perform univariate analysis on them.
# EXPLANATION
This is simplest form of data analysis, where the data being analyzed consists of just one variable. Since it’s a single variable, it doesn’t deal with causes or relationships. The main purpose of univariate analysis is to describe the data and find patterns that exist within it.<br>
<B>Univariate Analysis:</B>Data consists of only one variable (only x value).

- Line Plots / Bar Charts
- Histograms
- Box Plots
- Count Plots
- Descriptive Statistics techniques
- Violin Plot

# ALGORITHM
### Step 1
Read the given data.

### Step 2
Remove null values if present.

### Step 3
Using box plot, determine if outliers are present and remove them.

### Step 4
Apply univariate analysis on each column in the data.

# CODE
- <B>employeesal.csv</B>
```python
import pandas as pd
import seaborn as sns
import numpy as np
from scipy import stats
df = pd.read_csv("/content/employeesal.csv")
df.describe()

# BEFORE DATA CLEANING
sns.boxplot(data=df)

# PERFORMING DATA CLEANING
z = np.abs(stats.zscore(df['Salary']))
dfc = df[z<1]

# AFTER DATA CLEANING
sns.boxplot(data=dfc)
sns.histplot(x='Experience_Years',data=df2)
sns.histplot(x='Age',data=df2)
sns.histplot(x='Salary',data=df2)
```
- <B>SuperStore.csv</B>
```python
import pandas as pd
import seaborn as sns
import numpy as np
from scipy import stats
df = pd.read_csv("/content/SuperStore.csv")
df.describe()
sns.boxplot(data=df)

# DATA CLEANING
z = np.abs(stats.zscore(df['Sales']))
df = df[z<0.75]

# AFTER DATA CLEANING
sns.boxplot(y='Sales',data=df)
sns.distplot(df['Sales'])
sns.histplot(data=df['Sales'])
```
- <B>Diabetes.csv</B>
```python
import pandas as pd
import seaborn as sns
import numpy as np
from scipy import stats
df = pd.read_csv("/content/diabetes.csv")
df.info()
sns.boxplot(data=df)

# DATA CLEANING
z = np.abs(stats.zscore(df['Glucose']))
dfc=df[(z<2)]
z = np.abs(stats.zscore(dfc['BloodPressure']))
dfc=dfc[(z<2)]
z = np.abs(stats.zscore(dfc['SkinThickness']))
dfc=dfc[(z<3)]
z = np.abs(stats.zscore(dfc['BMI']))
dfc=dfc[(z<2)]
z = np.abs(stats.zscore(dfc['Insulin']))
dfc=dfc[(z<2)]
z = np.abs(stats.zscore(dfc['DiabetesPedigreeFunction']))
dfc=dfc[(z<2)]
z = np.abs(stats.zscore(dfc['Age']))
dfc=dfc[(z<2)]
z = np.abs(stats.zscore(dfc['Outcome']))
dfc=dfc[(z<3)]

# AFTER DATA CLEANING
sns.boxplot(data=dfc)
sns.histplot(dfc)
sns.histplot(x='Glucose',data=dfc)
sns.histplot(x='BloodPressure',data=dfc)
sns.histplot(x='SkinThickness',data=dfc)
sns.histplot(x='Insulin',data=dfc)
sns.histplot(x='BMI',data=dfc)
sns.histplot(x='DiabetesPedigreeFunction',data=dfc)
sns.histplot(x='Age',data=dfc)
```
# OUTPUT
- <B>employeesal.csv</B>
  - Before Data Cleaning
<br><img src="https://github.com/Janarthanan2/ODD2023-DataScience-Ex-03/assets/119393515/72e8516e-7c53-428b-b0d7-d8e32cf3ade2" width="250" height="250">
- After Data Cleaning
<br><img src="https://github.com/Janarthanan2/ODD2023-DataScience-Ex-03/assets/119393515/ad2c45ae-b823-42e4-9cca-3c93ee406217" width="250" height="250"><img src="https://github.com/Janarthanan2/ODD2023-DataScience-Ex-03/assets/119393515/76172f7f-8b0b-4755-af02-28214c7c1587" width="250" height="250"><img src="https://github.com/Janarthanan2/ODD2023-DataScience-Ex-03/assets/119393515/469f5f22-5c18-4e25-93e2-3715cedbb98b" width="250" height="250"><img src="https://github.com/Janarthanan2/ODD2023-DataScience-Ex-03/assets/119393515/8128241f-a15b-4cd1-a93e-11ced3963885" width="250" height="250"><br>

- <B>SuperStore.csv</B>

<br><p>Before Data Cleaning</p>
<img src="https://github.com/Janarthanan2/ODD2023-DataScience-Ex-03/assets/119393515/9a7d8413-801a-4e23-a41f-f1d742801581" width="250" height="250">
<img src="https://github.com/Janarthanan2/ODD2023-DataScience-Ex-03/assets/119393515/a0ab9b85-64dd-46d5-8993-0ca863188d7c" width="250" height="250">
<br><p>After Data Cleaning</p>
<br><img src="https://github.com/Janarthanan2/ODD2023-DataScience-Ex-03/assets/119393515/64aa0b5a-97b7-4e28-95b1-72db7e11c522" width="250" height="250">
<img src="https://github.com/Janarthanan2/ODD2023-DataScience-Ex-03/assets/119393515/9f949a3f-a20d-4777-812f-0fd99b199067" width="250" height="250">
<img src="https://github.com/Janarthanan2/ODD2023-DataScience-Ex-03/assets/119393515/a90caa0b-66ae-4b2a-8e6d-3ca1910d081c" width="250" height="250">

- <B>Diabetes.csv</B>

<p>Before Data Cleaning</p>
<br><img src="https://github.com/Janarthanan2/ODD2023-DataScience-Ex-03/assets/119393515/91f8d1c2-9cea-4360-9647-b4a200b5eafe" width="250" height="250">
<br><p>After Data Cleaning</p>
<br><img src="https://github.com/Janarthanan2/ODD2023-DataScience-Ex-03/assets/119393515/77a451e8-4b53-410a-a88d-9b3ec16779e8" width="250" height="250">
<img src="https://github.com/Janarthanan2/ODD2023-DataScience-Ex-03/assets/119393515/fe46aea8-4dee-4057-a34d-992dcfa28fa7" width="250" height="250">
<img src="https://github.com/Janarthanan2/ODD2023-DataScience-Ex-03/assets/119393515/6e861055-01b2-4c93-bcd0-79114e567611" width="250" height="250">
<img src="https://github.com/Janarthanan2/ODD2023-DataScience-Ex-03/assets/119393515/69f1f869-12e4-44a9-b405-814e3de38bca" width="250" height="250">
<img src="https://github.com/Janarthanan2/ODD2023-DataScience-Ex-03/assets/119393515/c3b78287-2f13-4445-88be-4d594aa4862e" width="250" height="250">
<img src="https://github.com/Janarthanan2/ODD2023-DataScience-Ex-03/assets/119393515/cd226892-2a2e-4408-aa96-352af73643c0" width="250" height="250">
<img src="https://github.com/Janarthanan2/ODD2023-DataScience-Ex-03/assets/119393515/22de1e7f-d39c-42d4-8232-153e2ba16076" width="250" height="250">
<img src="https://github.com/Janarthanan2/ODD2023-DataScience-Ex-03/assets/119393515/b98a5bee-f4e5-4177-99c5-ae7ec678a9d3" width="250" height="250">
<img src="https://github.com/Janarthanan2/ODD2023-DataScience-Ex-03/assets/119393515/05d40b9d-5540-4879-8134-542426d51692" width="250" height="250">

# RESULT
Thus, We have read the given data and performed the univariate analysis with different types of plots.
