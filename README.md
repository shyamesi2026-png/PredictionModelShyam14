"# PredictionModelShyam14" 

# Diabetes Prediction using Support Vector Machine

## Overview

This project implements a machine learning model to predict whether a person has diabetes based on medical attributes. It uses a Support Vector Machine (SVM) classifier with a linear kernel and evaluates performance using accuracy score.

## Tech Stack

* Python 3.x
* pandas
* numpy
* scikit-learn

## Project Structure

```
PredictionModelShyam14/
│── diabetes.csv
  │── Untitled3.ipynb
│── README.md
```

## Installation

### Clone the repository

```
git clone https://github.com/your-username/diabetes-prediction.git
cd diabetes-prediction
```

### Install dependencies

```
pip install pandas numpy scikit-learn
```

## Usage

Run the script using:

```
python main.py
```

## Workflow

### 1. Import Libraries

The required libraries for data processing, scaling, model training, and evaluation are imported.

### 2. Load Dataset

The dataset is loaded using pandas:

```
df = pd.read_csv('diabetes.csv')
```

### 3. Feature and Target Separation

The dataset is divided into:

* Features (X): All columns except 'Outcome'
* Target (y): 'Outcome' column

### 4. Train-Test Split

The dataset is split into training and testing sets using an 80-20 ratio.

### 5. Feature Scaling

StandardScaler is used to normalize the feature values to improve model performance.

### 6. Model Training

A Support Vector Machine classifier with a linear kernel is trained on the scaled training data.

### 7. Prediction and Evaluation

Predictions are made on the test dataset and evaluated using accuracy score.

## Output

The program prints:

* Accuracy score (decimal)
* Accuracy score (percentage)

Example:

```
0.77
77.0
```

## Future Improvements

* Add data visualization and analysis
* Perform hyperparameter tuning
* Compare multiple machine learning models
* Build a user interface or API for predictions

## Requirements

Ensure the following file is present in the project directory:

* diabetes.csv

## License

This project is open-source and available under the MIT License.



# House Price Prediction using Random Forest Regression

## Overview

This project implements a machine learning regression model to predict house prices based on input features. It uses a Random Forest Regressor and evaluates model performance using R² score on both training and testing datasets.

## Tech Stack

* Python 3.x
* pandas
* numpy
* scikit-learn

## Project Structure

```id="m4x8sv"
PredictionModelShyam14/
│── house_prices.csv
  │── Untitled3.ipynb
│── README.md
```

## Installation

### Clone the repository

```id="q9c0xb"
git clone https://github.com/your-username/house-price-prediction.git
cd house-price-prediction
```

### Install dependencies

```id="7qpk3v"
pip install pandas numpy scikit-learn
```

## Usage

Run the script using:

```id="3dn1k7"
python main.py
```

## Workflow

### 1. Import Libraries

The required libraries for data handling, preprocessing, model training, and evaluation are imported.

### 2. Load Dataset

The dataset is loaded using pandas:

```python id="8o7hcz"
df = pd.read_csv('house_prices.csv')
```

### 3. Feature and Target Separation

The dataset is divided into:

* Features (X): All columns except 'price'
* Target (y): 'price' column

```python id="ux4n3h"
X = df.drop(columns=['price'], axis=1)
y = df['price']
```

### 4. Train-Test Split

The dataset is split into training and testing sets using an 80-20 ratio.

```python id="r8k0vy"
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
```

### 5. Feature Scaling

StandardScaler is applied to normalize feature values.

```python id="l3v4od"
scaler = StandardScaler()
X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)
```

### 6. Model Training

A Random Forest Regressor is used with the following configuration:

* n_estimators = 1000
* max_depth = None
* min_samples_split = 2
* min_samples_leaf = 1
* random_state = 2
* n_jobs = -1 (parallel processing)

```python id="j9b2tp"
cf2 = RandomForestRegressor(n_estimators=1000, max_depth=None, min_samples_split=2, min_samples_leaf=1, random_state=2, n_jobs=-1)
cf2.fit(X_train_scaled, y_train)
```

### 7. Prediction

Predictions are generated for both training and testing datasets:

```python id="8f1a7k"
x_train_pred = cf2.predict(X_train_scaled)
x_test_pred = cf2.predict(X_test_scaled)
```

### 8. Model Evaluation

Model performance is evaluated using R² score:

```python id="1m9v8d"
x_train_r2 = r2_score(y_train, x_train_pred)
x_test_r2 = r2_score(y_test, x_test_pred)
```

---

## Output

The model prints R² scores for both training and testing datasets.

Example:

```id="6z0c4q"
Train R2: 0.95
Test R2: 0.87
```

---

## Interpretation

* R² Score closer to 1 indicates better model performance.
* A significant gap between train and test R² may indicate overfitting.

---

## Future Improvements

* Perform hyperparameter tuning (GridSearchCV / RandomizedSearchCV)
* Add feature importance analysis
* Compare with other regression models
* Add visualization (price distribution, predictions vs actual)
* Build a deployment-ready API

---

## Requirements

Ensure the following file is present in the project directory:

* house_prices.csv

---

## License

This project is open-source and available under the MIT License.

---

# Wine Quality Prediction using Random Forest Classifier

## Overview

This project implements a machine learning classification model to predict wine quality based on physicochemical properties. It uses a Random Forest Classifier and evaluates performance using accuracy score and a detailed classification report.

## Tech Stack

* Python 3.x
* pandas
* scikit-learn

## Project Structure

```id="7lxh7q"
PredictionModelShyam14/
│── winequality.csv
  │── Untitled3.ipynb
│── README.md
```

## Installation

### Clone the repository

```id="g7l2m2"
git clone https://github.com/your-username/wine-quality-prediction.git
cd wine-quality-prediction
```

### Install dependencies

```id="q2x4bx"
pip install pandas scikit-learn
```

## Usage

Run the script using:

```id="h3q0p1"
python main.py
```

## Workflow

### 1. Import Libraries

The required libraries for data handling, preprocessing, model training, and evaluation are imported.

### 2. Load Dataset

The dataset is loaded using pandas:

```python id="n1b5ke"
df = pd.read_csv('winequality.csv')
```

### 3. Feature and Target Separation

The dataset is divided into:

* Features (X): All columns except 'quality'
* Target (y): 'quality' column

```python id="y0df5g"
X = df.drop(columns=['quality'], axis=1)
y = df['quality']
```

### 4. Train-Test Split

The dataset is split into training and testing sets using an 80-20 ratio.

```python id="h9y6lz"
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
```

### 5. Feature Scaling

StandardScaler is applied to normalize feature values.

```python id="t6v2hf"
scaler = StandardScaler()
X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)
```

### 6. Model Training

A Random Forest Classifier is used with the following configuration:

* n_estimators = 500
* max_depth = 15
* random_state = 42

```python id="j4k1ps"
model = RandomForestClassifier(n_estimators=500, max_depth=15, random_state=42)
model.fit(X_train_scaled, y_train)
```

### 7. Prediction

Predictions are generated on the test dataset:

```python id="c0d7wn"
y_pred = model.predict(X_test_scaled)
```

### 8. Model Evaluation

The model is evaluated using:

* Accuracy Score
* Classification Report (precision, recall, F1-score)

```python id="8s5r2n"
accuracy = accuracy_score(y_test, y_pred)
print(classification_report(y_test, y_pred))
```

---

## Output

The program prints:

* Accuracy (decimal)
* Accuracy (percentage)
* Detailed classification report

Example:

```id="e1x9ab"
Accuracy: 0.85
Accuracy Percentage: 85.0%

Classification Report:
              precision    recall  f1-score   support
...
```

---

## Interpretation

* Accuracy indicates overall model performance.
* Classification report provides class-wise evaluation:

  * Precision: correctness of positive predictions
  * Recall: coverage of actual positives
  * F1-score: balance between precision and recall

---

## Future Improvements

* Perform hyperparameter tuning (GridSearchCV / RandomizedSearchCV)
* Handle class imbalance if present
* Add feature importance analysis
* Compare with other classification models
* Build a deployment-ready API or interface

---

## Requirements

Ensure the following file is present in the project directory:

* winequality.csv

---

## License

This project is open-source and available under the MIT License.

---

# Heart Disease Prediction using Random Forest Classifier

## Overview

This project implements a machine learning classification model to predict the presence of heart disease based on patient health data. It uses a Random Forest Classifier and includes data preprocessing steps such as encoding, duplicate removal, and missing value handling.

## Tech Stack

* Python 3.x
* pandas
* scikit-learn

## Project Structure

```id="d9v2xk"
PredictionModelShyam14/
│── heart.csv
  │── Untitled3.ipynb
│── README.md
```

## Installation

### Clone the repository

```id="c3p7qw"
git clone https://github.com/your-username/heart-disease-prediction.git
cd heart-disease-prediction
```

### Install dependencies

```id="z5l8rm"
pip install pandas scikit-learn
```

## Usage

Run the script using:

```id="u2x6fh"
python main.py
```

## Workflow

### 1. Import Libraries

The required libraries for data preprocessing, model training, and evaluation are imported.

### 2. Load Dataset

The dataset is loaded using pandas:

```python id="h4b1tz"
df = pd.read_csv('heart.csv')
```

### 3. Data Preprocessing

#### a. Encode Categorical Data

The 'sex' column is converted into numerical format:

```python id="m9x3jk"
df['sex'] = df['sex'].str.lower().map({'male': 1, 'female': 0})
```

#### b. Remove Duplicates

Duplicate rows are removed to improve data quality:

```python id="r8y2np"
df = df.drop_duplicates()
```

#### c. Handle Missing Values

Missing numerical values are filled using the median:

```python id="t6q4vx"
df = df.fillna(df.median(numeric_only=True))
```

---

### 4. Feature and Target Separation

* Features (X): All columns except 'target'
* Target (y): 'target' column

```python id="w1n5ka"
X = df.drop(columns=['target'], axis=1)
y = df['target']
```

---

### 5. Train-Test Split

The dataset is split into training and testing sets using an 80-20 ratio.

```python id="p7c9hz"
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=2)
```

---

### 6. Feature Scaling

StandardScaler is applied to normalize feature values.

```python id="b4k6ms"
scaler = StandardScaler()
X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)
```

---

### 7. Model Training

A Random Forest Classifier is used with the following configuration:

* n_estimators = 1000
* max_depth = None
* min_samples_split = 2
* min_samples_leaf = 1
* random_state = 2

```python id="g2v8xr"
cf = RandomForestClassifier(n_estimators=1000, max_depth=None, min_samples_split=2, min_samples_leaf=1, random_state=2)
cf.fit(X_train_scaled, y_train)
```

---

### 8. Prediction

Predictions are generated for both training and testing datasets:

```python id="k9r3dw"
x_train_pred = cf.predict(X_train_scaled)
x_test_pred = cf.predict(X_test_scaled)
```

---

### 9. Model Evaluation

Accuracy is calculated for both training and testing datasets:

```python id="v6x2qp"
x_train_acc = accuracy_score(y_train, x_train_pred)
x_test_acc = accuracy_score(y_test, x_test_pred)
```

---

## Output

The program prints:

* Training Accuracy
* Testing Accuracy

Example:

```id="n3k7sy"
0.98
0.85
```

---

## Interpretation

* Training accuracy indicates how well the model fits the training data.
* Testing accuracy indicates how well the model generalizes to unseen data.
* A large difference between training and testing accuracy may indicate overfitting.

---

## Future Improvements

* Add confusion matrix and classification report
* Perform feature importance analysis
* Handle categorical features more robustly
* Apply hyperparameter tuning
* Build a deployment-ready API or interface

---

## Requirements

Ensure the following file is present in the project directory:

* heart.csv

---

## License

This project is open-source and available under the MIT License.

---

## Author

Shyam Chauhan

