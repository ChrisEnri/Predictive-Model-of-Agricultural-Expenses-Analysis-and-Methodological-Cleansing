# Bovine Inventory Regression: Agricultural Expense Predictive Model

## 📖 Project Overview
This repository contains an end-to-end predictive modeling workflow in R designed to estimate expenses in agricultural production units based on bovine inventories. Prioritizing statistical rigor over raw accuracy, this project showcases professional data science practices applied to real-world, non-normally distributed economic data.

Rather than artificially inflating performance metrics, this analysis transparently addresses structural challenges in the dataset, providing a mathematically sound baseline for economic inference.

## 🌍 Language Versions
To ensure accessibility, the code and documentation for this project are available in two languages:

For the English version: Please review the Modelos_Eng file.

For the Spanish version: Please review the Modelos_Esp file.

## 🛠️ Tech Stack & Libraries
Language: R

Data Manipulation & Pipeline: tidyverse (dplyr, readr)

Data Ingestion/Export: readxl, writexl

Statistical Diagnostics: car (VIF), lmtest (Breusch-Pagan)

Visualization: corrplot

## 🔬 Key Methodological Steps
Structural Zeros Treatment: Addressed missing values (NAs) not as data capture errors, but as true physical absences of inventory (structural zeros).

Logarithmic Scaling: Applied log1p to stabilize variance in highly right-skewed economic variables, successfully compressing extreme values while preserving zero values consistently.

Strict Data Leakage Prevention: Performed a randomized 80/20 train-test split. To prevent data leakage during Z-score standardization, the test set was scaled by dynamically projecting the mean and standard deviation extracted exclusively from the training set.

Multicollinearity Eradication: Executed a backward elimination feature selection process using Variance Inflation Factors (VIF), retaining only mathematically independent predictors.

Residual Diagnostics: Evaluated the constancy of residual variance using the Breusch-Pagan test.

## 📊 Results & Conclusions
Feature Independence: The final architecture achieved a maximum VIF of 2.66 (well below the conservative threshold of 5), confirming the complete removal of structural multicollinearity.

Variance Analysis: The Breusch-Pagan test yielded a p-value near zero, confirming the presence of heteroscedasticity. This is an expected phenomenon in economic data, as larger production units naturally exhibit higher dispersion in absolute expenses.

Model Performance: The final parsimonious model yielded an R-squared of 0.13. While a preliminary unoptimized model showed an R-squared of 0.29, that metric was artificially inflated by redundant predictors. The final metric represents an honest, un-overfitted evaluation of the linear relationship.
