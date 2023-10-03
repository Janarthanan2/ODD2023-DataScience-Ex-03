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
z = np.abs(stats.zscore(df['Sales']))
df = df[z<0.75]
sns.boxplot(y='Sales',data=df)
sns.distplot(df['Sales'])
sns.histplot(data=df['Sales'])
```
- <B>.diabetes.csv</B>
```python
import pandas as pd
import seaborn as sns
import numpy as np
from scipy import stats
df = pd.read_csv("/content/diabetes.csv")
df.info()
sns.boxplot(data=df)
#DATA CLEANING
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
