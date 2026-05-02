# Identifying Undervalued Football Players Using Machine Learning

## Executive Summary
This project uses 2025/26 player performance data from Europe’s top five leagues to estimate player market value and identify potentially undervalued footballers.

A Random Forest regression model was trained to predict a player’s current “fair” market value based on statistical performance. Players whose predicted value exceeded their actual market value were flagged as potential undervaluation candidates.

---

## Business Problem
Football clubs often overpay for high-profile players while missing lower-cost players with strong statistical profiles. This project explores whether machine learning can support scouting decisions by identifying players whose performance suggests a higher market value than their current valuation.

---

## Dataset
The dataset was sourced from Kaggle and contains player-level statistics for the 2025/26 season across Europe’s top five leagues.

The project uses:
- Player performance statistics
- Market value data
- Position information
- League information

---

## Project Workflow
1. Exploratory Data Analysis  
2. Data Cleaning and Feature Engineering  
3. Market Value Modelling  
4. Model Evaluation  
5. Undervalued Player Identification  
6. Visualisation and Insights  

---

## Exploratory Data Analysis
Initial exploration was conducted to understand the dataset structure, missing values, league coverage, position distributions and market value range.

The dataset contained a heavily skewed market value distribution, with a small number of elite players valued far above the majority of the dataset.

![Market Value Distribution](visuals/market_value_distribution.png)

---

## Data Cleaning and Feature Engineering
Key preprocessing steps included:

- Filtering noisy low-value player records
- Cleaning player names for matching
- Handling missing values
- Creating per-90 performance metrics
- Creating attacking contribution features
- Encoding league and position variables
- Removing value-related columns from model inputs to prevent data leakage

A major part of the project involved checking valuation fields carefully. External valuation data was tested but found to be inconsistent, so the more realistic market value column from the main dataset was used.

---

## Modelling Approach
A Random Forest Regressor was used to estimate market value from player statistics.

Random Forest was chosen because:
- It handles non-linear relationships well
- It works effectively with mixed football performance features
- It provides feature importance for interpretation
- It is less sensitive to outliers than simpler linear models

Market value was log-transformed because the distribution was highly skewed.

---

## Model Evaluation
The model was evaluated using:

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² score

The predicted values were compared with actual values to assess model performance.

![Actual vs Predicted](visuals/actual_vs_predicted.png)

---

## Identifying Undervalued Players
Players were ranked using:
