# Used-Car-Price-Prediction
Used car price prediction using Python and Machine Learning.



# 🚗 Used Car Price Prediction | Machine Learning Project

<p align="center">
  <b>An End-to-End Regression Project to Estimate Used Car Prices</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Machine%20Learning-Regression-orange" alt="Machine Learning">
  <img src="https://img.shields.io/badge/Scikit--learn-Modeling-F7931E?logo=scikitlearn&logoColor=white" alt="Scikit-learn">
  <img src="https://img.shields.io/badge/Status-Completed-success" alt="Project Status">
</p>

---

## 📌 1. Project Overview

This project focuses on predicting the estimated selling price of used cars using Machine Learning regression algorithms.

The model analyzes vehicle characteristics such as brand, model, vehicle age, kilometres driven, transmission type, ownership history, and fuel type to estimate a car's price.

The project follows an end-to-end Machine Learning workflow, including data cleaning, exploratory data analysis (EDA), feature engineering, preprocessing, model training, evaluation, hyperparameter tuning, and saving the trained model.

**Objective:** Build a data-driven model that helps estimate used car prices from historical vehicle data.

---

## 🎯 2. Business Problem

Estimating the price of a used car can be difficult because its value depends on multiple factors, including age, brand, usage, fuel type, and transmission.

An inaccurate estimate may lead to overpricing or underpricing.

This project explores how Machine Learning can use historical data to identify patterns between vehicle characteristics and asking prices.

### Business Questions

* How does vehicle age affect its estimated price?
* How does the distance driven influence car value?
* Do brand and model contribute to price differences?
* How do fuel type, transmission, and ownership relate to price?
* Which regression model performs best on the test dataset?

### Potential Business Applications

* Used-car price estimation platforms
* Pre-owned vehicle dealerships
* Online car marketplaces
* Preliminary vehicle valuation
* Data-driven pricing support

---

## 🛠️ 3. Tools and Technologies

| Technology           | Purpose                                         |
| -------------------- | ----------------------------------------------- |
| Python               | Programming and analysis                        |
| Pandas               | Data manipulation and cleaning                  |
| NumPy                | Numerical operations                            |
| Matplotlib / Seaborn | Data visualization and EDA                      |
| Scikit-learn         | Preprocessing, model training, and evaluation   |
| Joblib               | Saving trained models and preprocessing objects |
| Jupyter Notebook     | Interactive development and documentation       |
| Git & GitHub         | Version control and project portfolio           |

*Note: Keep only the libraries actually used in your notebook and project.*

---

## 📂 4. Dataset Description

The project uses a used-car dataset containing vehicle information and asking prices.

### Dataset Summary

| Property                         | Details                    |
| -------------------------------- | -------------------------- |
| Dataset                          | `used_cars_dataset_v2.csv` |
| Original data source             | To be specified if known   |
| Records after cleaning           | 11,008                     |
| Features after cleaning          | 10                         |
| Missing values after cleaning    | 0                          |
| Duplicate records after cleaning | 0                          |
| Year range retained              | 2011–2024                  |
| Target variable                  | `AskPrice`                 |

### Important Features

* **Brand:** Manufacturer of the vehicle
* **Model:** Specific vehicle model
* **Age:** Age of the vehicle
* **kmDriven:** Total kilometres driven
* **Transmission:** Transmission category
* **Owner:** Ownership information
* **FuelType:** Fuel category
* **kmDrivenPerYear:** Engineered feature representing annual usage
* **GoodCondition:** Engineered condition-related indicator
* **AgeGroup:** Engineered age category
* **AskPrice:** Target variable used for price prediction

The final feature list used for training excludes `AskPrice`, because it is the value the model is learning to predict.

---

## 🔍 5. Project Workflow

The project follows these Machine Learning stages:

1. Data loading and inspection
2. Exploratory Data Analysis (EDA)
3. Data cleaning and validation
4. Feature engineering
5. Feature selection
6. Train-test splitting
7. Categorical encoding and preprocessing
8. Regression model training
9. Model evaluation and comparison
10. Hyperparameter tuning
11. Final model selection
12. Model serialization using Joblib
13. Prediction for a new vehicle

---

## 🧹 6. Data Cleaning and Preparation

Data quality is important because inconsistent or invalid values can affect model performance.

The cleaning process included:

* Inspecting dataset dimensions and column types
* Checking missing values
* Removing duplicate records
* Reviewing vehicle manufacturing years
* Retaining records within the selected year range
* Checking important numerical feature ranges
* Preparing the target variable and input features

### Cleaning Results

| Check                       | Result |
| --------------------------- | -----: |
| Rows retained               | 11,008 |
| Missing values remaining    |      0 |
| Duplicate records remaining |      0 |
| Minimum vehicle year        |   2011 |
| Maximum vehicle year        |   2024 |

These results describe the cleaned dataset used in the project.

---

## 📊 7. Exploratory Data Analysis (EDA)

Exploratory Data Analysis helps understand the dataset before training a model.

The analysis can be used to investigate:

* Price distribution and unusual price values
* Car prices across brands and models
* Relationship between vehicle age and price
* Relationship between kilometres driven and price
* Distribution of categorical features
* Potential outliers and patterns in the target variable

EDA supports better feature understanding and helps identify data quality issues before modeling.

---

## ⚙️ 8. Feature Engineering and Selection

Feature engineering creates useful information from existing columns.

The project includes the following engineered features:

* **kmDrivenPerYear:** Average kilometres driven per year, based on the available vehicle age and usage fields
* **GoodCondition:** A condition-related indicator derived from the project's feature logic
* **AgeGroup:** A categorical grouping of vehicle age

Feature selection was used to prepare the input variables for model training.

### Selected Input Features

`Brand`, `model`, `Age`, `kmDriven`, `Transmission`, `Owner`, `FuelType`, `kmDrivenPerYear`, `GoodCondition`, `AgeGroup`

The target variable is `AskPrice`.

---

## 🔄 9. Data Preprocessing

Machine Learning algorithms require features in a suitable numerical format.

The preprocessing stage handles categorical data and prepares the input features for model training.

### Preprocessing Steps

* Separating input features (`X`) and target (`y`)
* Splitting data into training and testing sets
* Encoding categorical features using One-Hot Encoding
* Applying preprocessing consistently to training and testing data

### Train-Test Split

| Dataset      | Records |
| ------------ | ------: |
| Training set |   8,806 |
| Testing set  |   2,202 |
| Total        |  11,008 |

The dataset was divided into training and testing subsets so model performance could be evaluated on data not used for fitting.

The categorical preprocessing produced **407 encoded features**.

---

## 🤖 10. Machine Learning Models

Three regression algorithms were evaluated.

### 1. Linear Regression

A baseline regression model used to learn linear relationships between vehicle features and asking price.

### 2. Decision Tree Regressor

A tree-based model that learns decision rules from feature values and can capture nonlinear relationships.

### 3. Random Forest Regressor

An ensemble model that combines predictions from multiple decision trees. It can capture more complex relationships than a simple linear model.

The models were compared using test-set evaluation metrics to identify the most suitable candidate.

---

## 📈 11. Model Evaluation and Results

The models were evaluated using the following regression metrics.

| Metric   | Meaning                                                             |
| -------- | ------------------------------------------------------------------- |
| R² Score | Measures how much variation in the target is explained by the model |
| MAE      | Mean Absolute Error; average absolute prediction error              |
| RMSE     | Root Mean Squared Error; penalizes larger errors more heavily       |

### Model Comparison

| Model                   |    Test R² |      Test MAE |
| ----------------------- | ---------: | ------------: |
| Linear Regression       |     0.4954 |     ₹5,13,540 |
| Decision Tree Regressor |     0.5608 |     ₹3,68,915 |
| Random Forest Regressor | **0.6741** | **₹1,98,515** |

### Best Model: Random Forest Regressor

The original Random Forest model achieved the best test-set results among the evaluated models.

* **Test R²:** 0.6741
* **MAE:** Approximately ₹1.99 lakh
* **RMSE:** Approximately ₹10.02 lakh
* **Number of trees:** 100

The results indicate that Random Forest performed better than the other evaluated models on this test set.

**Important:** The RMSE is substantially higher than the MAE, suggesting that some predictions have relatively large errors. Model performance should therefore be interpreted carefully, especially for expensive or unusual vehicles.

---

## 🎛️ 12. Hyperparameter Tuning

RandomizedSearchCV was used to explore alternative Random Forest configurations.

### Best Parameters Found

* `n_estimators`: 50
* `max_depth`: 20
* `max_features`: `sqrt`
* `min_samples_split`: 5
* `min_samples_leaf`: 1

The best cross-validation R² score was approximately **0.5933**.

The tuned model achieved a test R² of approximately **0.5640**, which was lower than the original Random Forest model's test R² of approximately **0.6741**.

Therefore, the original Random Forest model was retained as the selected model based on the reported test results.

Hyperparameter tuning does not guarantee an improvement; results depend on the search space, validation strategy, and dataset.

---

## 💾 13. Model Saving

The selected model and its preprocessing object were saved using Joblib so they can be loaded later without repeating the training process.

Saved artifacts:

* `used_car_price_model.pkl`
* `used_car_preprocessor.pkl`

The preprocessing object is important because new vehicle data must undergo the same transformations used during model training.

**Compatibility note:** The model and preprocessor should be loaded with compatible Python and library versions. Pickle-based files should only be loaded from trusted sources.

---

## 🚘 14. Sample Prediction

A sample vehicle was passed through the saved preprocessing workflow and the trained model.

### Example Output

**Predicted Car Price: ₹7,85,589.97**

This is an example prediction from the project run, not a guaranteed selling price or an independent valuation.

Actual market prices may differ because of vehicle condition, location, service history, market demand, and other factors not fully represented in the dataset.

---

## 📁 15. Project Structure

```text
Used-Car-Price-Prediction/
│
├── data/
│   └── used_cars_dataset_v2.csv
│
├── notebooks/
│   └── CAR PRICE PREDICTION.ipynb
│
├── models/
│   ├── used_car_price_model.pkl
│   └── used_car_preprocessor.pkl
│
├── src/
│   └──
│
├── README.md
├── requirements.txt
└── .gitignore
```

* `data/` — Dataset used for the project
* `notebooks/` — Analysis, experiments, and model development
* `models/` — Saved model and preprocessing artifacts
* `src/` — Reusable prediction code, if added
* `README.md` — Project documentation
* `requirements.txt` — Python dependencies
* `.gitignore` — Files excluded from version control

---

## ▶️ 16. How to Run the Project

### Step 1: Clone the Repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd Used-Car-Price-Prediction
```

Replace `YOUR_GITHUB_REPOSITORY_URL` with the actual repository URL.

### Step 2: Create a Virtual Environment (Recommended)

```bash
python -m venv .venv
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

### Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 4: Open the Notebook

```bash
jupyter notebook
```

Open `notebooks/CAR PRICE PREDICTION.ipynb` and run the cells in order.

*Note: The notebook must use project-relative paths or paths updated for your local environment. The exact dependency versions should match the libraries used to train the saved model.*

---

## ⚠️ 17. Limitations

* The model learns from historical dataset patterns and may not reflect current market prices.
* Prediction accuracy may vary by brand, model, price range, and vehicle condition.
* Large prediction errors are possible, as indicated by the RMSE.
* The dataset may not include every factor that affects a vehicle's market value.
* The model should not be treated as a certified vehicle valuation.

---

## 🚀 18. Future Improvements

Possible next steps include:

* Building a simple web application using Streamlit or Flask
* Adding interactive input fields for vehicle details
* Comparing additional regression algorithms
* Using cross-validation for more reliable model comparison
* Analyzing prediction errors across price ranges and vehicle brands
* Investigating feature importance and model interpretability
* Evaluating performance on a separate, more recent dataset
* Adding automated tests and a reusable prediction script

---

## 👨‍💻 19. Author

**Ravikant Bhardwaj**

Aspiring Data Analyst | Machine Learning Learner

* GitHub: [github.com/rkb931566-spec](https://github.com/rkb931566-spec)

---

## 📌 20. Disclaimer

This project was developed for educational and portfolio purposes.

The predicted price is an estimate based on the trained model and available data. It should not be considered a guaranteed market price, financial recommendation, or professional vehicle valuation.

---

<p align="center">
  <b>Built with Python, Machine Learning, and Data Analysis.</b>
</p>
