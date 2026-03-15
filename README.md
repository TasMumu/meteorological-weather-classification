# Weather Type Classification using Support Vector Machines

![Python](https://img.shields.io/badge/Python-3.10-blue)
![Machine Learning](https://img.shields.io/badge/Machine-Learning-green)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-orange)

## Project Overview

Weather prediction is an important task in environmental monitoring, agriculture, and transportation systems. Machine learning models can analyze meteorological features to identify patterns and classify weather conditions.

This project builds and evaluates **Support Vector Machine (SVM)** models to classify weather types based on atmospheric and environmental features.

The goal is to predict the **weather type** using multiple meteorological parameters and compare the performance of different SVM configurations.

The weather classes in the dataset include:

- Sunny
- Rainy
- Cloudy
- Snowy

---

## Dataset

Dataset: **Weather Type Classification Dataset**

Source: Kaggle  
Author: Nikhil Narayan

The dataset contains several meteorological variables that influence weather conditions.

### Features

| Feature | Description |
|------|------|
| temperature | Temperature in degrees Celsius |
| humidity | Humidity percentage |
| wind_speed | Wind speed in km/h |
| precipitation (%) | Percentage of precipitation |
| cloud_cover | Description of cloud cover |
| atmospheric_pressure | Atmospheric pressure in hPa |
| uv_index | Ultraviolet index |
| season | Season of the year |
| visibility (km) | Visibility distance |
| location | Type of location |
| weather_type | Target variable (Rainy, Sunny, Cloudy, Snowy) |

---

## Project Workflow

### 1. Exploratory Data Analysis

Initial exploration was conducted to understand the distribution and behavior of important meteorological variables.

Visualizations included:

- Histograms for **temperature, humidity, and wind speed**
- Box plot analysis for **precipitation percentage**

These visualizations helped identify feature distributions and potential outliers.

## Visualizations

Feature Distribution

![Distribution of Season](images/Season_Distribution.png)

![Temperature, humidity, and wind_speed histograms](images/Histograms.png)

![Boxplot of Precipitation](images/Precipitation.png)


---

### 2. Data Preprocessing

To prepare the dataset for machine learning models, several preprocessing steps were applied:

**Categorical Encoding**

Categorical features were converted into numerical format using **One-Hot Encoding**:

- cloud_cover
- location
- season

**Feature Scaling**

Numerical variables were standardized to ensure consistent feature ranges, which is essential for algorithms like SVM that are sensitive to feature magnitude.

---

### 3. Model Training

Three Support Vector Machine models were trained and evaluated:

1. **SVM with Linear Kernel**
2. **SVM with Radial Basis Function (RBF) Kernel**
3. **Custom SVM Model with Tuned Hyperparameters**

Hyperparameter configuration for the custom model:

```
C = 0.5
gamma = 'auto'
kernel = 'rbf'
degree = 2
```

---

### 4. Machine Learning Pipeline

A **Scikit-learn Pipeline** was implemented to integrate preprocessing and model training into a single workflow.

This ensures:

- consistent preprocessing
- reduced risk of data leakage
- easier reproducibility

---

## Results

The performance of the different SVM models was evaluated using **classification accuracy**.

| Model | Accuracy |
|------|------|
| SVM (Linear Kernel) | 0.8845 |
| SVM (RBF Kernel) | 0.9055 |
| Custom SVM Model | 0.8989 |

### Key Findings

- The **Linear Kernel SVM** provides a strong baseline but struggles to capture complex patterns.
- The **RBF Kernel SVM** significantly improves performance by modeling non-linear relationships.
- The **Custom SVM model** performs competitively, demonstrating the importance of hyperparameter tuning.

The **RBF Kernel SVM achieved the highest accuracy (90.55%)**, making it the most effective model for this classification task.

---

## Technologies Used

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Scikit-learn

---

## Repository Structure

```
weather-classification-svm
│
├── weather_classification.ipynb
├── weather_classification_data.csv
└── README.md
```

---

## Future Improvements

Potential extensions for this project include:

- testing additional machine learning algorithms
- performing cross-validation
- incorporating more advanced feature engineering
- expanding the dataset for improved model generalization

---

## Author

Tasnim Ahmad Mumu  
Data Analyst | Machine Learning Enthusiast
