# ComfortJDDS7255-8
# King County, Washington Housing Price Prediction and Grade Classification Using Feature Engineering, Feature Selection, and Hyperparameter Optimization

## Project summary
This study evaluated whether feature engineering, feature selection, and hyperparameter optimization (HPO) could improve regression and classification performance on King County, Washington housing market data.

The CatBoost regressor, after HPO and feature selection, achieved an R² of 0.914, slightly higher than the 0.913 achieved before optimization, confirming its suitability for housing price prediction.

The random forest classifier, after HPO and feature selection, achieved an accuracy of 0.708, lower than the 0.714 achieved before optimization, indicating that the model was not suitable for housing grade classification.

This study engineered hedonic, geographic, and multiplicative interaction features. Future work could explore polynomial interactions, hybrid feature selection methods, and GPU‑accelerated HPO to expand the model search space.

## 1. Business understanding

Housing transactions are a major component of global economies, and accurate house price prediction is essential for buyers, sellers, and policymakers (Das et al., 2020). Feature engineering enhances machine learning effectiveness by deriving new variables from existing data (Abdelouahed et al., 2024). Feature selection methods help identify the most relevant predictors while avoiding unnecessary transformations (Bouchlaghem et al., 2022). Optimizing machine learning performance requires not only high‑quality data but also appropriate algorithms, hyperparameters, and training procedures (Vincent & Jidesh, 2023).

This study engineered hedonic, geographic, and multiplicative interaction features; future work could explore polynomial interactions, hybrid feature selection methods, and GPU‑accelerated HPO to expand model search space.

### Research questions
**Research Question #1:** Can housing price prediction be improved through feature engineering and selection, and by applying hyperparameter optimization to regression models?
**Research Question #2:** Can the classification of housing grades be improved by applying feature engineering and selection to existing housing data, and hyperparameter optimization to classification models?

## 2. Data understanding

### Import libraries
Core scientific and machine learning libraries were used, including:
* pandas
* numpy
* matplotlib
* seaborn
* scikit‑learn
* catboost
* scipy
* joblib

### Ingest King County housing dataset
The dataset was loaded from a CSV file located in the data/ directory.

### Preliminary data analysis
Data description and data quality check:
* Missing data
* Outliers
* Duplicate rows

### Exploratory data analysis (EDA)
EDA included:
* Summary statistics
* Distribution plots
* Correlation analysis
* Geographic patterns using latitude/longitude

## 3. Data preprocessing
### Data cleansing
* No missing values
* No duplicate rows
* Parse date

### Baseline features
Baseline features included bedrooms, bathrooms, etc.

### Feature engineering
* Hedonic features: house age, total rooms, etc.
* Geographic features: neighborhoods, distance metrics, etc.
* Interaction features: condition times age, bedrooms times bathrooms, etc.

### Data partitioning
* Train, test, and validation
* Regression and classification
* Linear and logistic regression

### Normalization and Scaling
For linear and logistic regression.

## 4. Modeling
### Models
* Linear regression
* Logistic regression
* Random forest (regessor and classifier)
* CatBoost (regessor and classifier)

### Hyperparameter optimization
**Filter:** SelectKBest
**Wrapper:** Recursive feature elimination (RFE)
**Embedded:** Lasso

### Diagnostics
Regression:
* Residual distribution
* Residual versus actual plot
* Residual versus predicted plot
* Q-Q plot

Classification:
* Confustion matrix
* Model features
* Classification report
* ROC-AUC

## 5. Evaluation
Regression spider diagram:
* R2
* MSE
* RMSE
* MAE

Classification spider diagram:
* Accuracy
* Precision
* Recall
* F1 score

Model comparison:
* Baseline vs. engineered features
* Before vs. after hyperparameter optimization and feature selection
* Final model selection based on test‑set performance

## Repository structure
```text
project-name/
│
├── data/
│   └── kc_house_data.csv
│
├── notebooks/
│   └── king_county_housing_analysis.ipynb
│
├── outputs/
│   ├── feature_importance.png
│   ├── model_performance.png
│   ├── residual_plot.png
│   └── confusion_matrix.png
│
├── requirements.txt
├── LICENSE
└── README.md
```

## Installation
Clone the repository:
```bash
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>
```
Install dependencies:
```bash
pip install -r requirements.txt
```

## How to run the project
Launch the Jupyter notebook:
```bash
jupyter notebook notebooks/king_county_housing_analysis.ipynb
```
Run all cells to reproduce:
* Data ingestion
* Feature engineering
* Hyperparameter optimization
* Feature selection
* Model training
* Evaluation and diagnostics

Outputs (plots, metrics) will be saved to the outputs/ directory.

## Requirements
Pinned versions for full reproducibility:
```text
pandas==2.1.4
numpy==1.26.4
matplotlib==3.10.7
seaborn==0.13.2
scikit-learn==1.4.2
catboost==1.2.10
scipy==1.13.1
joblib==1.3.2
jupyter==1.0.0
```
## Licensing
**Code:** MIT License (see LICENSE)
**Data:** Apache 2.0 License (see LICENSE-APACHE-2.0)

## Acknowledgements
**Abdelouahed, S. M., Abla, R., Asmae, E., & Abdellah, A. (2024).** 
Harnessing feature engineering to improve machine learning: A review of different data processing techniques.  
2024 International Conference on Intelligent Systems and Computer Vision (ISCV), 1–6.
https://doi.org/10.1109/ISCV60512.2024.10620105

**Bouchlaghem, Y., Akhiat, Y., & Amjad, S. (2022).** 
Feature Selection: A Review and Comparative Study.  
E3S Web of Conferences, 351, 01046.
https://doi.org/10.1051/e3sconf/202235101046

**Das, S. S. S., Ali, M. E., Li, Y.-F., Kang, Y.-B., & Sellis, T. (2020).**  
Boosting House Price Predictions using Geo-Spatial Network Embedding.  
arXiv.
https://doi.org/10.48550/arXiv.2009.00254

**Soylev, B. (2024, May 23).**  
USA House Prices. House_Prices_Dataset.
https://www.kaggle.com/datasets/fratzcan/usa-house-prices

**Vincent, A. M., & Jidesh, P. (2023).**  
An improved hyperparameter optimization framework for AutoML systems using evolutionary algorithms.  
Scientific Reports, 13(1), 4737.
https://doi.org/10.1038/s41598-023-32027-3
