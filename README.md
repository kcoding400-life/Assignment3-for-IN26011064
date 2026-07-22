# Assignment3-for-IN26011064

## Salary Prediction using Polynomial Regression

**Author:** Kushagra Raghuvanshi 

**Registration Number:** 23BSA10072

**Application Number:** IN26011064

**Batch Number:** 2B

A machine learning project that predicts employee salaries based on position level using **Polynomial Regression**. Since salary growth across position levels is non-linear (e.g., a jump from Senior Partner to CEO isn't proportional to lower-level jumps), a polynomial model captures this relationship far better than simple linear regression.

## 📊 Dataset

**Position Salaries Dataset** — [Kaggle Link](https://www.kaggle.com/datasets/akram24/position-salaries)

| Column   | Description                                  |
|----------|-----------------------------------------------|
| Position | Job title (e.g., Manager, CEO)                |
| Level    | Numeric position level (1–10)                 |
| Salary   | Annual salary in USD                          |

- **Input Feature:** `Level`
- **Target Variable:** `Salary`

## 🎯 Problem Statement

A company wants to estimate employee salaries based on their position level. Since the relationship between position level and salary is non-linear, this project develops a Polynomial Regression model to predict salaries accurately.

## 🛠️ Tech Stack

- Python
- Pandas & NumPy — data handling
- Scikit-learn — model building & evaluation
- Matplotlib — visualization
- Google Colab / Jupyter Notebook

## 🚀 Project Workflow

### 1. Data Understanding
- Load dataset via `kagglehub`
- Display first 5 records
- Programmatically identify input feature and target variable
- View dataset info and summary statistics

### 2. Data Preprocessing
- Check for missing values
- Select feature (`Level`) and target (`Salary`)
- Split data into 80% training / 20% testing

### 3. Model Development
- Transform `Level` using `PolynomialFeatures` (degree = 3)
- Train a `LinearRegression` model on the transformed features
- Predict salaries on the test set

### 4. Model Evaluation
- Evaluate using:
  - **MAE** (Mean Absolute Error)
  - **MSE** (Mean Squared Error)
  - **R² Score**
- Visualize:
  - Scatter plot of actual data
  - Polynomial regression curve fit

## 📈 Results

| Metric | Value |
|--------|-------|
| MAE    | *70635.25* |
| MSE    | *6263853282.86* |
| R²     | *0.8763* |

## 🔍 Observations

1.  **Strong Explanatory Power**: The R2 Score of `0.8763` suggests that the polynomial regression model (with degree 3) explains a high percentage of the variance in salary, indicating a good overall fit to the data's trend.
2.  **Noticeable Prediction Errors**: Despite the high R2 score, the Mean Absolute Error (MAE) of approximately `$70,635` indicates that the model's predictions can still deviate significantly from the actual salaries for individual data points. This is further highlighted by the large Mean Squared Error (MSE).
3.  **Effective Capture of Non-Linearity**: Visually, the polynomial regression curve effectively captures the non-linear relationship between 'Position Level' and 'Salary', following the general upward trend of the data points. While it doesn't pass through every single point perfectly, it provides a reasonable approximation of the underlying pattern.


## Task 5: Conclusion
Our exploration into predicting salaries based on position level using polynomial regression yielded insightful results. The model, with a polynomial degree of 3, achieved an impressive R2 score of approximately 0.8763. This indicates that it explains about 87.63% of the variance in salary, suggesting a strong fit to the data's inherent non-linear trend. However, the Mean Absolute Error (MAE) of around $70,635 and a large Mean Squared Error (MSE) highlight that while the overall pattern is well-captured, individual predictions can still have significant deviations, especially given the wide range of salaries in the dataset.

The fundamental difference between Linear Regression and Polynomial Regression lies in their ability to model relationships. Linear Regression attempts to fit a straight line to the data, suitable only for relationships that are directly proportional. In contrast, Polynomial Regression extends this by fitting a curved line using polynomial features (e.g.,  x2 ,  x3 ), allowing it to capture complex, non-linear relationships. For this dataset, where salary growth accelerates significantly with higher position levels, a linear model would severely underperform.

Therefore, a key advantage of employing Polynomial Regression for this particular dataset is its ability to accurately model the non-linear relationship between 'Position Level' and 'Salary'. As observed from the scatter plot, salary does not increase uniformly with level; instead, it shows an exponential-like growth. A linear model would struggle to represent this curvature, leading to poor predictions. Polynomial Regression, by introducing higher-order terms, successfully adapted to this increasing rate of change, providing a far more realistic and higher-performing predictive model than a simple linear approach could have achieved.
