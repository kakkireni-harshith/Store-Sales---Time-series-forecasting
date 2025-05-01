# Store-Sales---Time-series-forecasting
You will predict sales for the thousands of product families sold at Favorita stores located in Ecuador. The training data includes dates, store and product information, whether that item was being promoted, as well as the sales numbers. Additional files include supplementary information that may be useful in building your models.

[![Kaggle](https://img.shields.io/badge/Kaggle-20BEFF?style=for-the-badge&logo=Kaggle&logoColor=white)](https://www.kaggle.com/competitions/store-sales-time-series-forecasting/overview)
[![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)

This repository contains the code used to solve the **Store Sales - Time Series Forecasting** problem on Kaggle. The goal of the project is to predict store sales based on time series data using machine learning models like **XGBoost** and various exploratory data analysis (EDA) techniques.

## Table of Contents
1. [Overview](#overview)
2. [Dataset Description](#dataset-description)
3. [Data Preprocessing](#data-preprocessing)
4. [Modeling](#modeling)
5. [Evaluation Metrics](#evaluation-metrics)
6. [Visualizations](#visualizations)
7. [Usage](#usage)
8. [Results](#results)
9. [Future Improvements](#future-improvements)

## Overview
This project is designed to predict store sales for a set of stores and products based on historical data. The time series nature of the problem requires handling date features, categorical variables, and ensuring accurate feature engineering to boost model performance.

## Dataset Description
The dataset consists of the following files:
- `train.csv`: Contains the training data with store and product information along with sales.
- `test.csv`: Contains the test data where the sales need to be predicted.
- `sample_submission.csv`: Provides a template for the submission format.

Key features include:
- `store_id`, `product_id`: Identifiers for stores and products.
- `sales`: The target variable to predict in the training data.
- `date`: A time-based feature that is used for extracting year, month, and day.

## Data Preprocessing
1. **Handling Date Feature**:
   - The `date` column was converted into a `datetime` format.
   - Extracted new features like `year`, `month`, and `day` to capture time-related patterns.
2. **Handling Categorical Data**:
   - Categorical columns such as `store_id` and `product_id` were transformed using **one-hot encoding** to make them compatible with machine learning models.
3. **Scaling Features**:
   - Numerical features were scaled using **StandardScaler** to ensure the model can converge properly during training.

## Modeling
The model used for this problem is **XGBoost**, which is well-suited for structured/tabular data. Key hyperparameters used include:
- `max_depth`: Controls the complexity of the model.
- `learning_rate`: Step size shrinkage to prevent overfitting.
- `n_estimators`: Number of boosting rounds.
- `objective`: Defined as `reg:squarederror` to minimize squared error.

## Evaluation Metrics
The primary evaluation metric used in this competition is **Root Mean Squared Logarithmic Error (RMSLE)**, which measures the ratio of the logarithms of predicted and actual values. It helps reduce the impact of large differences between predicted and actual sales.

## Visualizations
To understand the dataset and evaluate the model, the following visualizations were created:
1. **Correlation Heatmap**:
   - Displays correlations between numeric variables to understand their relationships.
2. **Time Series Plots**:
   - Shows sales trends over time for different stores and products.
     
## Usage
To run the project:
1. Clone the repository:
   ```bash
   git clone https://github.com/Hemanth1818/Store-Sales---Time-Series-Forecasting-from-kaggle.git
   cd store-sales-forecasting
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the notebook: Open `Kaggle_Notebook.ipynb` or the relevant Python files for code execution.
4. Modify paths and settings as required (e.g., dataset paths).

## Results
The model achieved an RMSLE score of **1.47128** on the Kaggle leaderboard, which demonstrates its ability to generalize well on unseen test data.

## Future Improvements
Some possible improvements to this project include:
- **Hyperparameter Tuning**: Further exploration of hyperparameters using techniques like **Grid Search** or **Random Search** to improve the model's performance.
- **Feature Engineering**: Exploring additional features such as **holiday information** or **promotions** could provide more predictive power.
- **Advanced Models**: Testing other time series-specific models like **Prophet** or deep learning-based models like **LSTMs**.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
