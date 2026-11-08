# 📘 Class 06 – Exploratory Data Analysis (EDA) and Data Preprocessing

**Domain:** Machine Learning  
**Level:** Beginner to Advanced  
**Chapter:** 02 – Machine Learning  
**Class:** 06  
**Status:** In Progress

---

# 1. Introduction to EDA

### 🟢 Telugu Understanding

Manam oka dataset teesukunnam anuko. Andulo student names, ages, study hours, marks unnayi.

Direct ga aa data ni Machine Learning model ki ivvakudadhu.

Mundhu konni questions adugutham:

- Dataset lo enni rows unnayi?
- Enni columns unnayi?
- Missing values unnaya?
- Duplicate records unnaya?
- Students average marks entha?
- Study hours perigite marks kuda perugutunnaya?
- Data lo unusual values unnaya?

Ila dataset ni observe chesi, understand chesi, patterns and problems identify chese process ni **Exploratory Data Analysis (EDA)** antaru.

Simple ga cheppalante:

**EDA ante model build cheyyakamundhu data ni examine cheyyadam.**

### 🔵 English Definition

Exploratory Data Analysis (EDA) is the process of examining, summarizing, and visualizing a dataset to understand its structure, identify patterns, detect anomalies, and discover relationships between variables before building a machine learning model.

### EDA Process

```text
             Raw Dataset
                  |
                  v
          Inspect the Data
                  |
                  v
       Understand Rows & Columns
                  |
                  v
       Identify Missing Values
                  |
                  v
       Find Duplicates & Outliers
                  |
                  v
        Visualize Data Patterns
                  |
                  v
          Draw Conclusions
```

### Why is EDA important?

- Helps understand the dataset.
- Identifies missing and incorrect values.
- Detects unusual observations.
- Reveals relationships between features.
- Helps select suitable preprocessing techniques.
- Improves the reliability of machine learning workflows.

---

# 2. Introduction to Pandas

### 🟢 Telugu Understanding

Python lo datasets ni handle cheyyadaniki Pandas ane library use chestham.

Excel lo rows and columns untayi kada? Alage Pandas lo kuda tabular data ni easy ga work cheyyachu.

Example:

| Name | Age | Marks |
|---|---:|---:|
| Ravi | 20 | 85 |
| Sita | 21 | 90 |
| Arun | 19 | 75 |

Ilaanti data ni Pandas DataFrame lo store cheyyachu.

### 🔵 English Definition

Pandas is a Python library used for data manipulation and analysis. It provides powerful data structures such as Series and DataFrame for working with structured data.

### Important Pandas Data Structures

| Structure | Description |
|---|---|
| Series | One-dimensional labeled data |
| DataFrame | Two-dimensional tabular data with rows and columns |

### Example

```python
import pandas as pd

data = {
    "Name": ["Ravi", "Sita", "Arun"],
    "Age": [20, 21, 19],
    "Marks": [85, 90, 75]
}

df = pd.DataFrame(data)

print(df)
```

**Output:**

```text
   Name  Age  Marks
0  Ravi   20     85
1  Sita   21     90
2  Arun   19     75
```

Here, `df` is a DataFrame.

---

# 3. Understanding a Dataset Using Pandas

EDA lo first step dataset ni inspect cheyyadam.

### 3.1 head()

🟢 **Telugu Understanding:** Dataset lo first 5 rows choodadaniki use chestham. Dataset lo first records ela unnayo telustundi.

🔵 **English Definition:** The `head()` method returns the first five rows of a DataFrame by default.

```python
df.head()
```

First 5 rows display avutayi.

```python
df.head(10)
```

First 10 rows display avutayi.

### 3.2 tail()

🟢 **Telugu Understanding:** Dataset lo last 5 rows choodadaniki use chestham.

🔵 **English Definition:** The `tail()` method returns the last five rows of a DataFrame by default.

```python
df.tail()
```

### 3.3 shape

🟢 **Telugu Understanding:** Dataset lo enni rows, enni columns unnayo telusukovadaniki use chestham.

🔵 **English Definition:** The `shape` attribute returns the number of rows and columns in a DataFrame.

```python
print(df.shape)
```

Output:

```text
(100, 4)
```

Meaning:
- 100 = Rows
- 4 = Columns

**Remember:** Shape is an attribute, so we use `df.shape`, not `df.shape()`.

### 3.4 columns

🟢 **Telugu Understanding:** Dataset lo column names enti ani choodadaniki use chestham.

🔵 **English Definition:** The `columns` attribute returns the column labels of a DataFrame.

```python
print(df.columns)
```

### 3.5 info()

🟢 **Telugu Understanding:** Dataset lo columns, data types, non-null values, memory usage laanti details telusukovachu.

🔵 **English Definition:** The `info()` method provides a concise summary of a DataFrame, including column names, data types, non-null counts, and memory usage.

```python
df.info()
```

### 3.6 describe()

🟢 **Telugu Understanding:** Numerical columns ki sambandhinchina statistical summary telusukovachu.

🔵 **English Definition:** The `describe()` method generates descriptive statistics such as count, mean, standard deviation, minimum, maximum, and quartiles.

```python
df.describe()
```

| Statistic | Meaning |
|---|---|
| count | Number of non-missing values |
| mean | Average |
| std | Standard deviation |
| min | Minimum value |
| 25% | First quartile |
| 50% | Median |
| 75% | Third quartile |
| max | Maximum value |

### 3.7 value_counts()

🟢 **Telugu Understanding:** Oka column lo different values enni sarlu vachayo count chestundi.

🔵 **English Definition:** The `value_counts()` method returns the frequency of each unique value in a Series.

```python
df["Gender"].value_counts()
```

Example output:

```text
Female    55
Male      45
```

---

# 4. Missing Values

### 🟢 Telugu Understanding

Dataset lo konni cells empty ga unnayi anuko.

Example:

| Name | Age | Marks |
|---|---:|---:|
| Ravi | 20 | 85 |
| Sita | 21 | NaN |
| Arun | NaN | 75 |

Sita marks and Arun age missing unnayi.

Missing values ni identify chesi, correct strategy tho handle cheyyali. Lekapothe model ki incomplete information vellachu.

### 🔵 English Definition

Missing values are data entries that are absent or unavailable in a dataset. Handling missing values is an important preprocessing step to ensure data quality.

### Identify Missing Values

```python
df.isnull()
```

Missing values count:

```python
df.isnull().sum()
```

Example:

```text
Name     0
Age      1
Marks    1
```

### Methods to Handle Missing Values

**Method 1: Remove missing rows**

```python
df.dropna()
```

Telugu: Missing value unna entire row remove avutundi. Kaani data ekkuva loss avvakudadhu.

**Method 2: Fill with mean**

```python
df["Age"] = df["Age"].fillna(df["Age"].mean())
```

Telugu: Numerical column lo missing values ni average tho fill cheyyachu. Outliers ekkuvaga unte mean suitable kakapovachu.

**Method 3: Fill with median**

```python
df["Age"] = df["Age"].fillna(df["Age"].median())
```

Telugu: Median ante middle value. Outliers unna situations lo mean kanna median better ga undochu.

**Method 4: Fill with mode**

```python
df["Gender"] = df["Gender"].fillna(df["Gender"].mode()[0])
```

Telugu: Mode ante most frequently repeated value. Categorical data ki use cheyyachu.

### Comparison

| Method | Suitable situation |
|---|---|
| Drop rows | Few missing rows and enough data |
| Mean | Numerical data without strong outlier influence |
| Median | Numerical data with skewness or outliers |
| Mode | Categorical data |

**Important:** Real ML workflow lo imputation values ni training data nunchi learn chesi, validation/test data ki apply cheyyali. Full dataset average use cheyyadam data leakage ki lead avvachu.

---

# 5. Duplicate Values

### 🟢 Telugu Understanding

Dataset lo same record rendu sarlu repeat ayithe danini duplicate row antam.

Example:

| Name | Age | Marks |
|---|---:|---:|
| Ravi | 20 | 85 |
| Sita | 21 | 90 |
| Ravi | 20 | 85 |

Ravi record rendu sarlu undi. Idi duplicate.

### 🔵 English Definition

Duplicate records are repeated rows in a dataset. Duplicate detection and removal help prevent repeated observations from distorting analysis or model training.

### Identify Duplicates

```python
df.duplicated()
```

Total duplicate count:

```python
df.duplicated().sum()
```

### Remove Duplicates

```python
df = df.drop_duplicates()
```

**Note:** Every repeated-looking row is not automatically wrong. Domain knowledge batti duplicates ni remove cheyyali.

---

# 6. Outliers

### 🟢 Telugu Understanding

Dataset lo normal values ki chaala different ga unna values ni outliers antaru.

Example:

```text
Student ages: 18, 19, 20, 21, 22, 95
```

95 age unusual ga undi. Idi data-entry error kavachu, leda genuine observation kavachu.

Outlier ni direct ga delete cheyyakudadhu. Mundhu verify cheyyali.

### 🔵 English Definition

An outlier is an observation that differs significantly from the general pattern of the other observations in a dataset.

### Example: Boxplot

A boxplot helps visualize the distribution of numerical data and identify potential outliers.

```python
import seaborn as sns
import matplotlib.pyplot as plt

sns.boxplot(x=df["Age"])
plt.title("Age Distribution")
plt.show()
```

### IQR Method

IQR means Interquartile Range.

Formula:

```text
IQR = Q3 - Q1

Lower Bound = Q1 - 1.5 × IQR

Upper Bound = Q3 + 1.5 × IQR
```

Where:

- Q1 = 25th percentile
- Q3 = 75th percentile
- IQR = Difference between Q3 and Q1

### Worked Example

Suppose:

```text
Q1 = 20
Q3 = 40
```

Then:

```text
IQR = 40 - 20
    = 20

Lower Bound = 20 - (1.5 × 20)
            = -10

Upper Bound = 40 + (1.5 × 20)
            = 70
```

Values below -10 or above 70 are potential outliers according to this rule.

### Python Implementation

```python
Q1 = df["Age"].quantile(0.25)
Q3 = df["Age"].quantile(0.75)

IQR = Q3 - Q1

lower_bound = Q1 - 1.5 * IQR
upper_bound = Q3 + 1.5 * IQR

outliers = df[
    (df["Age"] < lower_bound) |
    (df["Age"] > upper_bound)
]

print(outliers)
```

**Important:** IQR identifies potential outliers; it does not prove that those values are errors.

---

# 7. Data Visualization

### 🟢 Telugu Understanding

Numbers and tables choodatam kanna charts lo data patterns easy ga understand avuthayi.

Example:
- Study hours and marks relation telusukovadaniki Scatter Plot.
- Marks distribution telusukovadaniki Histogram.
- Categories compare cheyyadaniki Bar Chart.
- Outliers identify cheyyadaniki Boxplot.

### 🔵 English Definition

Data visualization is the graphical representation of data using charts and plots to identify patterns, trends, distributions, and relationships.

### Common Visualization Techniques

| Chart | Purpose |
|---|---|
| Bar Chart | Compare categories |
| Histogram | Understand numerical distribution |
| Scatter Plot | Examine relationships between two numerical variables |
| Boxplot | Examine spread and potential outliers |
| Heatmap | Visualize a matrix, such as feature correlations |

### 7.1 Histogram

```python
plt.hist(df["Marks"], bins=5)
plt.xlabel("Marks")
plt.ylabel("Frequency")
plt.title("Marks Distribution")
plt.show()
```

### 7.2 Scatter Plot

```python
plt.scatter(df["Study_Hours"], df["Marks"])
plt.xlabel("Study Hours")
plt.ylabel("Marks")
plt.title("Study Hours vs Marks")
plt.show()
```

### 7.3 Correlation Heatmap

```python
sns.heatmap(
    df.corr(numeric_only=True),
    annot=True,
    cmap="coolwarm"
)

plt.title("Correlation Heatmap")
plt.show()
```

### Correlation

Correlation measures the strength and direction of the relationship between two numerical variables.

Correlation coefficient ranges from -1 to +1.

| Value | Interpretation |
|---|---|
| +1 | Perfect positive correlation |
| 0 | No linear correlation |
| -1 | Perfect negative correlation |

**Important:** Correlation does not prove causation. Two variables moving together does not mean one causes the other.

---

# 8. Categorical Encoding

### 🟢 Telugu Understanding

Machine Learning algorithms generally numerical inputs tho work chestayi.

Kaani dataset lo Gender, City, Department laanti text values undochu.

Example:

```text
Gender
Male
Female
Male
Female
```

Ilaanti text categories ni suitable numerical representation ga convert cheyyadam Encoding antaru.

### 🔵 English Definition

Categorical encoding is the process of converting categorical variables into numerical representations that can be used by machine learning algorithms.

### 8.1 Label Encoding

Example:

```text
Low     → 0
Medium  → 1
High    → 2
```

Python:

```python
from sklearn.preprocessing import LabelEncoder

encoder = LabelEncoder()

df["Level_Encoded"] = encoder.fit_transform(df["Level"])
```

**Telugu:** Categories ki numeric labels assign chestham.

**Use:** Target labels or suitable categorical variables. Unordered categories ki arbitrary numbers assign chesthe false order create avvachu.

### 8.2 One-Hot Encoding

Example:

Original:

| City |
|---|
| Hyderabad |
| Chennai |
| Mumbai |

After One-Hot Encoding:

| City_Chennai | City_Hyderabad | City_Mumbai |
|---:|---:|---:|
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 0 | 0 | 1 |

Python:

```python
encoded_df = pd.get_dummies(
    df,
    columns=["City"],
    dtype=int
)
```

**Telugu:** Prathi category ki separate column create chestham. Andulo matching category ki 1, migatha vatiki 0 assign chestham.

### Label Encoding vs One-Hot Encoding

| Label Encoding | One-Hot Encoding |
|---|---|
| Assigns integer labels | Creates separate binary columns |
| Compact representation | Can increase column count |
| May imply order | Does not imply order |
| Useful for ordered categories or target labels | Useful for nominal categories |

---

# 9. Feature Scaling

### 🟢 Telugu Understanding

Oka dataset lo Age values 18–60 range lo unnayi. Salary values 10,000–1,00,000 range lo unnayi.

Different scales lo unna features ni common scale ki convert cheyyadam Feature Scaling antaru.

Idi especially distance-based and gradient-based algorithms ki important.

### 🔵 English Definition

Feature scaling is a preprocessing technique used to transform numerical features to comparable scales without changing the underlying information represented by them.

### 9.1 Standardization

Formula:

```text
z = (x - mean) / standard deviation
```

Where:

- x = Original value
- mean = Feature mean
- standard deviation = Feature standard deviation
- z = Standardized value

Python:

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()

scaled_data = scaler.fit_transform(df[["Age", "Salary"]])
```

StandardScaler transforms the training feature distribution to have approximately zero mean and unit variance.

### 9.2 Min-Max Normalization

Formula:

```text
X_scaled = (X - X_min) / (X_max - X_min)
```

Python:

```python
from sklearn.preprocessing import MinMaxScaler

scaler = MinMaxScaler()

scaled_data = scaler.fit_transform(df[["Age", "Salary"]])
```

Usually values are transformed to the range 0 to 1.

### StandardScaler vs MinMaxScaler

| StandardScaler | MinMaxScaler |
|---|---|
| Uses mean and standard deviation | Uses minimum and maximum |
| Centers around zero | Usually maps to 0–1 |
| Does not restrict values to a fixed range | Sensitive to extreme minimum and maximum values |

**Important:** Scaling is not necessary for every algorithm. Decision trees and Random Forests generally do not require feature scaling.

---

# 10. Training and Testing Data

### 🟢 Telugu Understanding

Manam dataset tho ML model train chestham. Model performance ni evaluate cheyyadaniki separate test data kavali.

Example:

1000 records unnayi anuko:

- 800 records → Training
- 200 records → Testing

Training data tho model patterns nerchukuntundi. Test data tho unseen data meeda model performance evaluate chestham.

### 🔵 English Definition

Train-test splitting is the process of dividing a dataset into separate subsets for model training and evaluation.

### Python

```python
from sklearn.model_selection import train_test_split

X = df[["Study_Hours"]]
y = df["Marks"]

X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42
)
```

- X = Input features
- y = Target variable
- test_size=0.2 = 20% test data
- random_state=42 = Reproducible split

---

# 11. Data Leakage

### 🟢 Telugu Understanding

Test data information training process loki accidentally vellipothe danini Data Leakage antaru.

Example:

Manam full dataset meeda StandardScaler fit chesi, taruvatha train/test split chesthe, test data statistics kuda scaler ki telisipothayi.

Idi correct process kaadu.

Correct process:

1. First train/test split cheyyali.
2. Scaler ni training data meeda fit cheyyali.
3. Training data ni transform cheyyali.
4. Test data ni same fitted scaler tho transform cheyyali.

### 🔵 English Definition

Data leakage occurs when information from outside the training data, especially validation or test data, improperly influences model training or evaluation, leading to overly optimistic performance estimates.

### Correct Flow

```text
              Raw Dataset
                   |
                   v
             Train-Test Split
                /       \
               /         \
              v           v
        Training Data   Test Data
              |           |
              v           |
       Fit Preprocessor   |
              |           |
              v           v
       Transform Train  Transform Test
              \           /
               \         /
                v       v
              Train and Evaluate
```

---

# 12. Scikit-learn Pipeline

### 🟢 Telugu Understanding

Manam missing values fill cheyyadam, scaling cheyyadam, model train cheyyadam anni separate ga rayachu.

Kaani real projects lo steps ni oka organized workflow lo combine cheyyadam better.

Scikit-learn Pipeline ante preprocessing steps and ML model ni oka sequence lo arrange cheyyadam.

### 🔵 English Definition

A Scikit-learn Pipeline chains multiple data transformation steps and an optional final estimator into a single object, ensuring consistent and reproducible preprocessing and modeling.

### Example

```python
from sklearn.pipeline import Pipeline
from sklearn.impute import SimpleImputer
from sklearn.preprocessing import StandardScaler
from sklearn.linear_model import LinearRegression

pipeline = Pipeline([
    ("imputer", SimpleImputer(strategy="median")),
    ("scaler", StandardScaler()),
    ("model", LinearRegression())
])
```

Pipeline lo:

1. Missing values median tho fill avutayi.
2. Features scale avutayi.
3. Linear Regression model train avutundi.

When `pipeline.fit(X_train, y_train)` is called, preprocessing is fitted using training data only.

For mixed numerical and categorical columns, `ColumnTransformer` can apply different preprocessing steps to different columns.

---

# 13. Complete Practical Example – Student Performance Dataset

### Project Objective

Study hours base chesukoni student marks predict cheyyadaniki dataset ni inspect, clean, visualize, and prepare cheddham.

### Step 1: Install Libraries

```bash
python -m pip install pandas numpy matplotlib seaborn scikit-learn
```

### Step 2: Import Libraries

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

from sklearn.model_selection import train_test_split
from sklearn.pipeline import Pipeline
from sklearn.impute import SimpleImputer
from sklearn.preprocessing import StandardScaler
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_absolute_error
```

### Step 3: Create a Sample Dataset

```python
data = {
    "Study_Hours": [1, 2, 3, 4, 5, 6, 7, 8, None, 10],
    "Age": [18, 19, 18, 20, 19, 21, 20, 22, 19, 21],
    "Marks": [35, 40, 50, 55, 60, 70, 75, 85, 80, 95]
}

df = pd.DataFrame(data)

print(df)
```

### Step 4: Inspect the Dataset

```python
print(df.head())
print(df.shape)
print(df.info())
print(df.describe())
```

### Step 5: Check Missing Values

```python
print(df.isnull().sum())
```

### Step 6: Visualize the Data

```python
sns.scatterplot(
    data=df,
    x="Study_Hours",
    y="Marks"
)

plt.title("Study Hours vs Marks")
plt.show()
```

### Step 7: Separate Features and Target

```python
X = df[["Study_Hours", "Age"]]
y = df["Marks"]
```

### Step 8: Split the Data

```python
X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42
)
```

### Step 9: Create a Pipeline

```python
pipeline = Pipeline([
    ("imputer", SimpleImputer(strategy="median")),
    ("scaler", StandardScaler()),
    ("model", LinearRegression())
])
```

### Step 10: Train the Model

```python
pipeline.fit(X_train, y_train)
```

### Step 11: Make Predictions

```python
predictions = pipeline.predict(X_test)

print("Actual Marks:")
print(y_test.values)

print("Predicted Marks:")
print(predictions)
```

### Step 12: Evaluate the Model

```python
mae = mean_absolute_error(y_test, predictions)

print("Mean Absolute Error:", mae)
```

**MAE (Mean Absolute Error):** It measures the average absolute difference between actual and predicted values. Lower MAE generally indicates smaller prediction errors.

**Note:** This is a tiny illustrative dataset for learning the workflow, not a reliable real-world student-performance model.

---

# 14. Complete EDA and Preprocessing Workflow

```text
             Collect Dataset
                   |
                   v
             Load with Pandas
                   |
                   v
             Inspect the Data
                   |
                   v
            Perform EDA
                   |
         +---------+---------+
         |         |         |
         v         v         v
      Missing  Duplicates  Outliers
       Values
         |         |         |
         +---------+---------+
                   |
                   v
             Clean the Data
                   |
                   v
           Train-Test Split
                   |
                   v
          Preprocessing Pipeline
          /                  \
         v                    v
     Imputation          Encoding/Scaling
          \                  /
           \                /
                   |
                   v
             Train ML Model
                   |
                   v
             Evaluate Model
```

---

# 15. Important Interview Questions

### Q1. What is EDA?

**Answer:** Exploratory Data Analysis is the process of analyzing and visualizing a dataset to understand its structure, identify patterns, and detect anomalies before model building.

### Q2. What is Pandas?

**Answer:** Pandas is a Python library used for data manipulation and analysis. It provides Series and DataFrame data structures.

### Q3. Difference between `head()` and `tail()`?

**Answer:** `head()` returns the first five rows by default, whereas `tail()` returns the last five rows by default.

### Q4. What is the difference between `shape` and `info()`?

**Answer:** `shape` returns the number of rows and columns, while `info()` provides a summary of columns, data types, non-null counts, and memory usage.

### Q5. How do you handle missing values?

**Answer:** Missing values can be handled by removing rows or columns when appropriate, or by imputing values using mean, median, mode, or more advanced techniques.

### Q6. What are outliers?

**Answer:** Outliers are observations that differ significantly from the overall pattern of the dataset.

### Q7. What is IQR?

**Answer:** Interquartile Range is the difference between the third quartile and first quartile. It is used to identify potential outliers.

### Q8. What is categorical encoding?

**Answer:** Categorical encoding converts categorical variables into numerical representations suitable for machine learning algorithms.

### Q9. Difference between Label Encoding and One-Hot Encoding?

**Answer:** Label Encoding assigns integer values to categories, whereas One-Hot Encoding creates separate binary columns for categories.

### Q10. What is feature scaling?

**Answer:** Feature scaling transforms numerical features to comparable scales so that differences in magnitude do not disproportionately influence certain algorithms.

### Q11. Difference between StandardScaler and MinMaxScaler?

**Answer:** StandardScaler transforms features using their mean and standard deviation, while MinMaxScaler scales values using their minimum and maximum.

### Q12. What is data leakage?

**Answer:** Data leakage occurs when information that should not be available during training influences the model, causing misleading evaluation results.

### Q13. What is a Pipeline in Scikit-learn?

**Answer:** A Pipeline combines preprocessing transformations and a machine learning estimator into one sequential workflow.

---

# 16. Knowledge Check

Try answering these questions before checking the answers.

1. What is the full form of EDA?
2. Which Pandas method displays the first five rows?
3. What does `df.shape` return?
4. Which method identifies missing values?
5. What is the difference between mean and median?
6. What is a duplicate record?
7. What does IQR stand for?
8. Which chart is useful for detecting potential outliers?
9. What is the purpose of One-Hot Encoding?
10. Which scaler uses mean and standard deviation?
11. Why should we split data before fitting a scaler?
12. What is data leakage?

### Practical Assignment

Create a DataFrame with these columns:

- Student_Name
- Age
- Study_Hours
- Marks
- City

Then complete these tasks:

1. Display the first five rows.
2. Print the number of rows and columns.
3. Check data types using `info()`.
4. Calculate descriptive statistics.
5. Find missing values.
6. Find and remove duplicate records where appropriate.
7. Plot a histogram of Marks.
8. Plot Study_Hours versus Marks using a scatter plot.
9. Identify potential outliers in Marks using IQR.
10. Separate input features and target variable.
11. Split the data into training and testing sets.
12. Create a preprocessing Pipeline and explain each step.

---

# 17. Class 06 Summary

In this class, we learned:

- Exploratory Data Analysis (EDA)
- Pandas and DataFrame
- Dataset inspection methods
- Missing value handling
- Duplicate detection
- Outlier detection using IQR
- Data visualization
- Categorical encoding
- Feature scaling
- Train-test splitting
- Data leakage
- Scikit-learn Pipeline
- Complete data preparation workflow

**Class 06 Completed – Exploratory Data Analysis and Data Preprocessing**

### Next Class: Class 07 – Introduction to Machine Learning Algorithms

In the next class, we will begin learning how machine learning algorithms learn from data, starting with supervised learning and regression.