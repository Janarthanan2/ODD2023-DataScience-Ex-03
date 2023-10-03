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
- <B>Diabetes.csv</B>
```python
import pandas as pd
import seaborn as sns
import numpy as np
from scipy import stats
df = pd.read_csv("/content/employeesal.csv")
df.describe()
sns.boxplot(data=df)
z = np.abs(stats.zscore(df['Salary']))
dfc = df[z<1]
sns.boxplot(data=dfc)
```
