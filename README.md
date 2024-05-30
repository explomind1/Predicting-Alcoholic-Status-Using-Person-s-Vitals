**Title**: Predicting Alcoholic Status Using Person's Vitals

This repository contains my solution for the Kaggle competition "Predicting Alcoholic Status Using Person's Vitals." The goal of the competition is to develop the best classification model to predict alcoholic status based on a person's vitals. The dataset consists of 70,000 training observations and 30,000 test observations, with 26 predictors each.

### Detailed README

# Predicting Alcoholic Status Using Person's Vitals

## Overview

This repository contains my solution for the Kaggle competition "Predicting Alcoholic Status Using Person's Vitals." The competition, hosted for UCLA statistics students, aims to create the best classification model to predict whether an individual is an alcoholic based on their vitals.

## About the Competition

- **Start Date**: October 26, 2023
- **End Date**: December 8, 2023
- **Submission Deadline**: December 1, 2023 @ 11:59 PM

### Dataset Description

The dataset is sourced from the National Health Insurance Service in Korea, with all personal and sensitive data excluded. It comprises training and testing datasets, each containing 26 predictors:

- **Training Data**: 70,000 observations
- **Testing Data**: 30,000 observations (without the response variable)

The primary objectives are:
1. Analysis of body signals
2. Classification of drinker (Alcoholic status)

### Evaluation

The competition evaluates models based on their accuracy scores on the testing data. Additionally, participants are evaluated on their project presentation and final paper. The Kaggle score forms a part of the overall project grade.

## Solution Approach

### Data Preprocessing

1. **Handling Missing Values**:
    - Numerical values were imputed with the median.
    - Categorical values were imputed with the mode.
    - Categorical variables were converted to factors for modeling.

2. **Feature Engineering**:
    - Interaction terms were created based on domain knowledge.
    - Categorical variables were encoded.
    - Numerical variables were standardized.

### Exploratory Data Analysis (EDA)

- Summary statistics for numerical and categorical variables.
- Visualizations: Histograms for key numerical variables (Age, Weight, BMI).
- Correlation analysis among numerical variables.
- Analysis of categorical variables (e.g., Smoking Status vs. Alcoholic Status).

### Model Building

Given the need for a nuanced and high-performing model, I used a Gradient Boosting Machine (GBM) model due to its efficacy in handling both numerical and categorical data and its ability to capture complex patterns.

### Model Training and Evaluation

1. **Data Splitting**:
    - Split the training data into training and validation sets.

2. **GBM Model**:
    - Built using the `caret` package in R.
    - Hyperparameter tuning was performed to find the best combination of parameters.
    - Model was trained and evaluated on the validation set.

3. **Performance**:
    - The best model achieved an accuracy of approximately 73.23% on the validation set.

### Final Predictions

The model was used to generate predictions on the test dataset. The predicted 'Alcoholic.Status' was then saved in a CSV file for submission.

## Repository Structure

```
|-- data/
|   |-- TrainSAData2.csv
|   |-- TestSAData2NoY.csv
|-- scripts/
|   |-- data_preprocessing.R
|   |-- eda.R
|   |-- model_building.R
|-- results/
|   |-- submission.csv
|-- README.md
|-- KaggleCompGodMode.Rmd
```

## Usage

1. **Data Preprocessing**:
    - Run `data_preprocessing.R` to clean and preprocess the data.
    
    ```R
    source('scripts/data_preprocessing.R')
    ```

2. **Exploratory Data Analysis**:
    - Run `eda.R` to perform exploratory data analysis.
    
    ```R
    source('scripts/eda.R')
    ```

3. **Model Building and Prediction**:
    - Run `model_building.R` to build the GBM model and generate predictions.
    
    ```R
    source('scripts/model_building.R')
    ```

## Results

- The final submission file (`submission.csv`) is located in the `results` directory.
- The model achieved an accuracy of approximately 73.23% on the validation set.

## Future Work

- Model tuning: Further adjustments to parameters like the number of estimators, learning rate, and tree depth.
- Advanced feature engineering: Creation of more complex interaction terms or derivation of new features based on domain knowledge.
- Exploring alternative models: Trying other models like Random Forest, XGBoost, or deep learning approaches to potentially improve performance.

## Conclusion

This repository demonstrates the process of developing a classification model to predict alcoholic status using a person's vitals. The solution includes data preprocessing, exploratory data analysis, feature engineering, model building, and evaluation, culminating in a robust GBM model that achieved competitive performance in the Kaggle competition.

---

Feel free to explore the code and use it as a reference for similar classification tasks. If you have any questions or suggestions, please open an issue or contact me.

## Contact

- **Email**: emreturan1269@gmail.com
