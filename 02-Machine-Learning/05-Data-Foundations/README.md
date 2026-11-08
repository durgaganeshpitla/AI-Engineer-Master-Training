# 🎓 AI Engineer Master Training
# Class 05 – Data Foundations for AI/ML

**Level:** Beginner to Advanced  
**Module:** Machine Learning Fundamentals

---

## 1. Introduction to Data in AI/ML

### 🟢 Telugu Understanding

Manam oka student exam lo marks entha vasthayo predict cheyali anukundham.

Andhuku computer ki student previous information ivvali:

- Student study hours
- Attendance
- Previous exam marks
- Final exam marks

Ila information collect chesi computer ki isthe, computer aa information lo patterns nerchukoni final marks predict cheyadaniki try chesthundhi.

Ikkada important point enti ante:

**Data correct ga unte, model useful predictions cheyadaniki ekkuva chance untundhi. Data lo mistakes unte, model results kuda wrong avvachu.**

Anduke AI/ML lo data ni understand cheyadam first step.

### 🔵 English Definition

Data is a collection of facts, observations, measurements, or information used by Artificial Intelligence and Machine Learning systems to learn patterns, train models, and make predictions.

---

## 2. What is a Dataset?

### 🟢 Telugu Understanding

Dataset ante related information ni oka organized format lo store chesina collection.

Example: Students dataset.

| Student | Study Hours | Attendance | Marks |
|---|---:|---:|---:|
| Ravi | 2 | 70% | 55 |
| Sita | 5 | 90% | 85 |
| Ram | 3 | 80% | 65 |
| Priya | 6 | 95% | 92 |

Ikkada complete table ni Dataset antam.

- Each row oka student's information.
- Each column oka type of information.
- Study Hours, Attendance, Marks lanti values data.

### 🔵 English Definition

A dataset is an organized collection of related data used for analysis, training, validation, and testing of Machine Learning models.

### Dataset Structure

```text
             DATASET
                |
       +--------+--------+
       |                 |
     ROWS              COLUMNS
       |                 |
   Observations       Features
       |
   Individual Records
```

**Example:** Student dataset lo oka row = one student record.

---

## 3. Types of Data

Data ni different ways lo classify cheyachu.

### 3.1 Structured Data

#### 🟢 Telugu Understanding

Structured data ante proper rows and columns format lo organize chesina data.

Example:

| ID | Name | Age | Salary |
|---|---|---:|---:|
| 101 | Ravi | 22 | 25000 |
| 102 | Sita | 24 | 30000 |

Ee data ni databases and spreadsheets lo easy ga store cheyachu.

#### 🔵 English Definition

Structured data is data organized in a predefined format, usually in rows and columns, with a consistent schema.

**Examples:**
- MySQL databases
- Excel spreadsheets
- Employee records
- Banking transactions

### 3.2 Semi-Structured Data

#### 🟢 Telugu Understanding

Semi-structured data ki normal table laga fixed rows and columns undakapovachu. Kani data ni organize cheyadaniki tags, keys, and labels untayi.

Example: JSON data.

```json
{
  "name": "Ravi",
  "age": 22,
  "skills": ["Python", "SQL"]
}
```

Ikkada `name`, `age`, `skills` ane keys data ni organize chesthunnayi.

#### 🔵 English Definition

Semi-structured data does not follow a strict tabular structure but contains organizational elements such as keys, tags, or metadata.

**Examples:**
- JSON
- XML
- HTML
- Log files

### 3.3 Unstructured Data

#### 🟢 Telugu Understanding

Unstructured data ante fixed table format lo leni data.

Example:
- Images
- Videos
- Audio recordings
- Documents
- Social media posts

Computer ki ee data ni directly simple table laga understand cheyadam kastam. Processing techniques and AI models use chestharu.

#### 🔵 English Definition

Unstructured data is information that does not follow a predefined tabular structure or fixed data schema.

### Comparison

| Data Type | Structure | Examples |
|---|---|---|
| Structured | Fixed rows and columns | SQL tables |
| Semi-Structured | Keys, tags, metadata | JSON, XML |
| Unstructured | No fixed tabular structure | Images, videos, audio |

---

## 4. What are Features and Labels?

Machine Learning lo idi chala important concept.

### 4.1 Features

#### 🟢 Telugu Understanding

Features ante model ki input ga iche information.

Example: House price predict cheyali anukundham.

House gurinchi:
- Area
- Number of bedrooms
- Location
- Age of house

Ivi anni model ki inputs. Kabatti veetini Features antaru.

#### 🔵 English Definition

Features are the input variables or measurable characteristics used by a Machine Learning model to make predictions.

### 4.2 Labels

#### 🟢 Telugu Understanding

Label ante manam predict cheyali anukuntunna final answer or target value.

House price prediction lo house price anedhi manam predict cheyali anukuntunnam.

Kabatti House Price = Label.

#### 🔵 English Definition

A label is the target variable or expected output that a supervised Machine Learning model learns to predict.

### Example Dataset

| Area (sq.ft) | Bedrooms | Age | House Price |
|---:|---:|---:|---:|
| 1000 | 2 | 5 | 25 Lakhs |
| 1500 | 3 | 3 | 40 Lakhs |
| 2000 | 3 | 2 | 55 Lakhs |

```text
          DATASET
             |
      +------+------+
      |             |
    FEATURES       LABEL
      |             |
  Area             |
  Bedrooms         |
  Age              |
                   |
              House Price
```

**Remember:**
- Features = Input (X)
- Label = Output (y)

---

## 5. Labeled and Unlabeled Data

### 5.1 Labeled Data

#### 🟢 Telugu Understanding

Labeled data ante input tho paatu correct answer kuda already available ga undadam.

Example:

| Email Text | Label |
|---|---|
| You won a prize! | Spam |
| Meeting at 10 AM | Not Spam |
| Claim your free reward | Spam |

Ikkada email tho paatu Spam or Not Spam ane answer kuda undhi.

Model ee examples nunchi nerchukuntundhi.

#### 🔵 English Definition

Labeled data is a dataset in which each input example is associated with a known target or correct output.

### 5.2 Unlabeled Data

#### 🟢 Telugu Understanding

Unlabeled data ante input information untundhi, kani correct answer or category already ivvaru.

Example:

Manaki 1000 customer records unnayi. Kani e customer ye group ki belong avutharo labels levu.

Model similar customers ni groups ga divide cheyadaniki try chesthundhi.

#### 🔵 English Definition

Unlabeled data is a dataset that contains input examples without predefined target labels.

### Comparison

| Labeled Data | Unlabeled Data |
|---|---|
| Input + Correct output | Only input |
| Used in supervised learning | Commonly used in unsupervised learning |
| Example: Spam / Not Spam | Example: Customer records without groups |

---

## 6. Types of Machine Learning

Data and labels availability batti Machine Learning ni different learning approaches ga classify chestham.

### 6.1 Supervised Learning

#### 🟢 Telugu Understanding

Supervised Learning ante model ki input data tho paatu correct answers kuda istham.

Teacher student ki questions and answers explain chesinattu, model ki examples and correct outputs istham.

Model aa relationship nerchukoni new input ki answer predict chesthundhi.

**Example:** Previous house details and their prices use chesi new house price predict cheyadam.

#### 🔵 English Definition

Supervised Learning is a type of Machine Learning in which a model learns from labeled data containing input-output pairs to predict outputs for new inputs.

**Types:**

1. Classification – Categories predict chesthundhi.
2. Regression – Continuous numerical values predict chesthundhi.

**Examples:**

| Problem | Type |
|---|---|
| Spam or Not Spam | Classification |
| Disease Positive or Negative | Classification |
| House Price Prediction | Regression |
| Temperature Prediction | Regression |

### 6.2 Unsupervised Learning

#### 🟢 Telugu Understanding

Unsupervised Learning lo model ki correct answers ivvam.

Model itself data lo similarities and patterns identify chesthundhi.

Example:

Oka shopping website daggara thousands of customer records unnayi. Customers purchasing behavior batti similar customers ni groups ga divide cheyachu.

#### 🔵 English Definition

Unsupervised Learning is a type of Machine Learning in which a model discovers hidden patterns, relationships, or groups in unlabeled data.

**Common techniques:**
- Clustering
- Dimensionality Reduction
- Association Rule Learning

**Example Algorithms:**
- K-Means
- Hierarchical Clustering
- DBSCAN
- PCA

### 6.3 Reinforcement Learning

#### 🟢 Telugu Understanding

Reinforcement Learning ante oka agent environment lo actions perform chesthundhi.

Correct action chesthe reward vasthundhi. Wrong action chesthe penalty or negative reward ravachu.

Repeated practice dwara better decisions teesukovadam nerchukuntundhi.

Example:

Oka robot maze lo correct path find cheyali.

- Correct direction → Reward
- Wrong direction → Penalty
- Goal reach avvadam → Higher Reward

#### 🔵 English Definition

Reinforcement Learning is a type of Machine Learning in which an agent learns to make decisions by interacting with an environment and receiving rewards or penalties.

### Reinforcement Learning Flow

```text
        AGENT
           |
           v
        ACTION
           |
           v
     ENVIRONMENT
           |
           v
     REWARD / PENALTY
           |
           v
        LEARNING
           |
           v
    BETTER ACTIONS
```

---

## 7. Training, Validation, and Testing Data

### 🟢 Telugu Understanding

Manam Machine Learning model build chesthunnam anukundham.

Available dataset motham model ki okesari ivvakudadhu. Usually dataset ni three parts ga divide chestham.

1. Training Data – Model ki nerpinchadaniki.
2. Validation Data – Model settings and performance tune cheyadaniki.
3. Testing Data – Final ga model performance check cheyadaniki.

### 🔵 English Definition

Training, validation, and testing datasets are separate portions of data used to train a model, tune its configuration, and evaluate its performance on unseen examples.

### Example: 1000 Records

```text
           TOTAL DATA
           1000 ROWS
                |
       +--------+--------+
       |        |        |
       v        v        v
   TRAINING VALIDATION TESTING
     70%      15%      15%
      |        |        |
     700      150      150
```

| Dataset | Percentage | Purpose |
|---|---:|---|
| Training | 70% | Learn patterns |
| Validation | 15% | Tune model |
| Testing | 15% | Final evaluation |

**Note:** 70/15/15 is only an example split. Actual proportions depend on dataset size and project requirements.

### Important Difference

| Training | Validation | Testing |
|---|---|---|
| Learns from data | Helps tune model | Evaluates final model |
| Used during training | Used during model selection | Kept separate for final evaluation |

**Important:** Test data ni model tuning kosam repeatedly use cheyakudadhu. Ala chesthe final evaluation trustworthy ga undadhu.

---

## 8. What is Data Preprocessing?

### 🟢 Telugu Understanding

Real-world data anedhi always clean ga undadhu.

Dataset lo:
- Missing values undachu.
- Duplicate records undachu.
- Wrong values undachu.
- Different formats undachu.
- Text and numbers mix ayi undachu.

Ila unna raw data ni clean chesi Machine Learning model ki suitable ga prepare cheyadanni Data Preprocessing antaru.

Example:

| Name | Age | Salary |
|---|---:|---:|
| Ravi | 22 | 25000 |
| Sita | NaN | 30000 |
| Ram | 24 | NaN |
| Ravi | 22 | 25000 |

Ikkada:
- `NaN` = Missing value.
- Ravi record duplicate ga undhi.

Model training mundhu ee issues ni handle cheyali.

### 🔵 English Definition

Data Preprocessing is the process of cleaning, transforming, and organizing raw data into a suitable format for Machine Learning algorithms.

### Common Preprocessing Steps

```text
          RAW DATA
              |
              v
      HANDLE MISSING VALUES
              |
              v
       REMOVE DUPLICATES
              |
              v
       HANDLE OUTLIERS
              |
              v
      ENCODE CATEGORICAL DATA
              |
              v
          SCALE DATA
              |
              v
       PROCESSED DATA
              |
              v
       MODEL TRAINING
```

Detailed implementation manam Class 06 lo practical ga nerchukuntam.

---

## 9. What is an Algorithm and a Model?

### 9.1 Algorithm

#### 🟢 Telugu Understanding

Algorithm ante oka problem solve cheyadaniki follow ayye method or set of steps.

Machine Learning lo algorithm anedhi data nunchi patterns nerchukovadaniki use chese learning method.

Examples:
- Linear Regression
- Decision Tree
- K-Nearest Neighbors
- Random Forest

#### 🔵 English Definition

A Machine Learning algorithm is a computational method or procedure used to learn patterns from data and solve a specific problem.

### 9.2 Model

#### 🟢 Telugu Understanding

Algorithm ni data tho train chesina tarvatha, nerchukunna patterns and parameters tho ready ayye result ni model antam.

Simple ga:

- Algorithm = Learning method.
- Model = Training tarvatha ready ayina learned system.

#### 🔵 English Definition

A Machine Learning model is the learned representation produced by training an algorithm on data, which can be used to make predictions or decisions.

### Example

```text
       TRAINING DATA
             |
             v
       ML ALGORITHM
             |
             v
          TRAINING
             |
             v
       TRAINED MODEL
             |
             v
        PREDICTIONS
```

---

## 10. Training and Inference

### 10.1 Model Training

#### 🟢 Telugu Understanding

Training ante model ki training data chupinchi, data lo patterns nerpinchadam.

Example: Previous house areas and prices use chesi relationship nerpinchadam.

#### 🔵 English Definition

Model training is the process of learning patterns and parameters from training data by applying a Machine Learning algorithm.

### 10.2 Inference

#### 🟢 Telugu Understanding

Training complete ayyaka, new data model ki istham.

Model already nerchukunna patterns use chesi output predict chesthundhi.

Ee process ni Inference antaru.

Example: 1800 square feet unna new house price predict cheyadam.

#### 🔵 English Definition

Inference is the process of using a trained Machine Learning model to generate predictions or outputs for new input data.

### Difference

| Training | Inference |
|---|---|
| Model learns patterns | Model uses learned patterns |
| Uses training data | Uses new input data |
| Builds the model | Produces predictions |

---

## 11. Overfitting and Underfitting

Model performance understand cheyadaniki ee two concepts important.

### 11.1 Overfitting

#### 🟢 Telugu Understanding

Oka student previous question papers answers matrame by-heart chesukunnadu anukundham.

Practice questions lo full marks vasthayi. Kani new questions ichinappudu answers cheppalekapothunnadu.

Alage Machine Learning model training data ni chala ekkuvaga memorize chesukoni, new data meedha poor performance chupisthe Overfitting antaru.

#### 🔵 English Definition

Overfitting occurs when a Machine Learning model learns the training data too closely, including noise and irrelevant details, resulting in poor generalization to unseen data.

### 11.2 Underfitting

#### 🟢 Telugu Understanding

Oka student topic sarigga study cheyaledhu anukundham.

Practice questions ki kuda correct answers ivvalekapothunnadu.

Alage model data lo basic patterns kuda nerchukolekapothe Underfitting antaru.

#### 🔵 English Definition

Underfitting occurs when a Machine Learning model is too simple or insufficiently trained to capture the underlying patterns in the data.

### Comparison

| Condition | Training Performance | Test Performance |
|---|---|---|
| Underfitting | Poor | Poor |
| Good Fit | Good | Good |
| Overfitting | Very good | Poor |

### Visual Understanding

```text
UNDERFITTING       GOOD FIT        OVERFITTING

   Too Simple      Balanced       Too Complex

   Poor Learning   Good Learning  Memorizes Data
```

### How to Reduce Overfitting?

- Use more representative training data.
- Apply regularization.
- Reduce unnecessary model complexity.
- Use cross-validation.
- Apply early stopping where appropriate.

### How to Reduce Underfitting?

- Use a more suitable model.
- Add useful features.
- Increase model complexity if needed.
- Train for an appropriate duration.
- Reduce excessive regularization.

---

## 12. Data Leakage

### 🟢 Telugu Understanding

Data Leakage ante model training time lo model ki available undakudadhu anukune information accidentally training lo enter avvadam.

Example:

Manam future house price predict cheyali anukundham.

Kani training data lo future sale price ki directly related information or actual final price leak ayithe, model ki answer mundhe telisinattu avuthundhi.

Appudu training and evaluation results artificially high ga ravachu. Real-world lo new data meedha poor results ravachu.

### 🔵 English Definition

Data Leakage occurs when information that would not legitimately be available at prediction time is used during model training or evaluation, leading to overly optimistic performance estimates.

### How to Avoid Data Leakage?

1. Split data before fitting preprocessing transformations.
2. Fit scalers and encoders only on training data.
3. Apply the learned transformations to validation and test data.
4. Avoid using future information while predicting past or current outcomes.
5. Keep the final test set separate.

---

## 13. Introduction to Important Python Libraries for Data

Machine Learning projects lo different libraries use chestham.

| Library | Purpose |
|---|---|
| NumPy | Numerical calculations and arrays |
| Pandas | Data handling and analysis |
| Matplotlib | Data visualization |
| Seaborn | Statistical visualization |
| Scikit-learn | ML algorithms and preprocessing |
| TensorFlow | Deep Learning |
| PyTorch | Deep Learning |

### Example: Pandas

```python
import pandas as pd

data = {
    "Name": ["Ravi", "Sita", "Ram"],
    "Age": [22, 24, 23],
    "Marks": [75, 90, 80]
}

df = pd.DataFrame(data)

print(df)
```

**Output:**

```text
   Name  Age  Marks
0  Ravi   22     75
1  Sita   24     90
2   Ram   23     80
```

Explanation:

- `import pandas as pd` – Pandas library import chesthunnam.
- `DataFrame()` – Data ni table format lo create chesthundhi.
- `df` – Manam create chesina dataset.

---

## 14. Practical Example – Simple Machine Learning Workflow

Ippudu manam complete basic ML workflow chuddam.

**Problem:** Study hours batti student marks predict cheyadam.

### Step 1: Import Libraries

```python
import pandas as pd

from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_absolute_error
```

### Step 2: Create Dataset

```python
data = {
    "Study_Hours": [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
    "Marks": [20, 25, 35, 40, 50, 60, 65, 75, 85, 95]
}

df = pd.DataFrame(data)

print(df)
```

### Step 3: Separate Features and Label

```python
X = df[["Study_Hours"]]

y = df["Marks"]
```

- `X` = Features (input).
- `y` = Label (target output).

### Step 4: Split the Dataset

```python
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)
```

- `test_size=0.2` – 20% data testing kosam.
- `random_state=42` – Repeated runs lo same split ravadaniki.

### Step 5: Create and Train Model

```python
model = LinearRegression()

model.fit(X_train, y_train)
```

`fit()` method model ki training data nunchi patterns nerpisthundhi.

### Step 6: Make Predictions

```python
predictions = model.predict(X_test)

print(predictions)
```

`predict()` method new inputs ki predicted marks isthundhi.

### Step 7: Evaluate the Model

```python
mae = mean_absolute_error(y_test, predictions)

print("Mean Absolute Error:", mae)
```

MAE ante actual values and predicted values madhya average absolute difference.

**Formula:**

\[
MAE = \frac{1}{n}\sum_{i=1}^{n}|y_i-\hat{y}_i|
\]

Where:

- \(n\) = Number of predictions
- \(y_i\) = Actual value
- \(\hat{y}_i\) = Predicted value

Lower MAE generally means predictions are closer to actual values.

---

## 15. Complete Machine Learning Workflow

```text
       DEFINE THE PROBLEM
               |
               v
         COLLECT DATA
               |
               v
       UNDERSTAND DATA
               |
               v
      DATA PREPROCESSING
               |
               v
      SELECT FEATURES (X)
               |
               v
       IDENTIFY LABEL (y)
               |
               v
        SPLIT THE DATA
               |
               v
       SELECT ALGORITHM
               |
               v
        TRAIN THE MODEL
               |
               v
      EVALUATE THE MODEL
               |
               v
       MAKE PREDICTIONS
               |
               v
        DEPLOY THE MODEL
```

This is a simplified workflow. Real projects may repeat preprocessing, training, and evaluation steps several times.

---

## 16. Important Interview Questions

### Q1. What is a dataset?

A dataset is an organized collection of related data used for analysis and Machine Learning.

### Q2. What are features and labels?

Features are input variables used by a model, whereas labels are the target outputs that the model is expected to predict.

### Q3. What is the difference between supervised and unsupervised learning?

Supervised learning uses labeled data, while unsupervised learning discovers patterns in unlabeled data.

### Q4. What is the difference between classification and regression?

Classification predicts categories, while regression predicts continuous numerical values.

### Q5. Why do we split data into training and testing sets?

We split data to train the model on one portion and evaluate its performance on unseen data using another portion.

### Q6. What is data preprocessing?

Data preprocessing is the process of cleaning and transforming raw data into a suitable format for Machine Learning.

### Q7. What is overfitting?

Overfitting happens when a model performs very well on training data but poorly on unseen data because it has learned the training data too closely.

### Q8. What is underfitting?

Underfitting occurs when a model fails to learn important patterns from the training data.

### Q9. What is data leakage?

Data leakage occurs when information that should not be available during model training or evaluation accidentally influences the model.

### Q10. What is the difference between training and inference?

Training is the process of learning patterns from data. Inference is the process of using a trained model to make predictions on new data.

### Q11. What is the difference between an algorithm and a model?

An algorithm is the learning procedure, whereas a model is the learned result produced after training.

### Q12. What is the purpose of Pandas?

Pandas is a Python library used for data manipulation, cleaning, analysis, and handling tabular datasets.

---

## 17. Knowledge Check

Try answering these questions without looking at the notes.

1. What is a dataset?
2. What are structured, semi-structured, and unstructured data?
3. What is the difference between features and labels?
4. What is the difference between labeled and unlabeled data?
5. Explain the three types of Machine Learning.
6. What is the purpose of training data?
7. Why do we need testing data?
8. What is data preprocessing?
9. Explain overfitting and underfitting with examples.
10. What is data leakage?
11. What is the difference between an algorithm and a model?
12. What is the difference between training and inference?

---

## 18. Class Summary

Data is the foundation of Machine Learning. A model learns patterns from data and uses those patterns to make predictions.

We learned:

- Dataset and its structure.
- Structured, semi-structured, and unstructured data.
- Features and labels.
- Labeled and unlabeled data.
- Supervised, unsupervised, and reinforcement learning.
- Training, validation, and testing datasets.
- Data preprocessing.
- Algorithms and models.
- Training and inference.
- Overfitting and underfitting.
- Data leakage.
- Basic ML workflow using Pandas and Scikit-learn.

**Class 05 Completed!**

**Next Class: Class 06 – Exploratory Data Analysis (EDA) and Data Preprocessing**

In the next class, we will work with a real dataset and learn how to inspect, clean, analyze, and visualize data using Python.