# Water Potability Prediction Using Machine Learning Bayesian Methods

## Overview

This project utilizes machine learning with a Bayesian approach to predict the potability of water in Indonesia, addressing the need for clean water as outlined in the UN's Sustainable Development Goals (SDG). Using a logistic regression model and Bayesian Data Analysis, the project aims to understand the factors influencing water quality based on data from Kaggle's "Water Potability" dataset.

## Table of Contents

1. [Project Motivation](#project-motivation)
2. [Dataset](#dataset)
3. [Methodology](#methodology)
4. [Results](#results)
5. [Further Improvement](#further-improvement)

## Project Motivation

Access to clean and safe drinking water is crucial for health and well-being. Indonesia faces challenges in ensuring the potability of its water sources, which can lead to serious health issues. This project is aimed at improving the understanding of water quality by building predictive models that classify water as either potable or non-potable.

## Dataset

The data used in this project is the "Water_Potability" dataset from Kaggle. It contains multiple features such as:

- pH level
- Hardness
- Solids
- Chloramines
- Sulfates
- Conductivity
- Organic Carbon
- Trihalomethanes
- Turbidity

The target variable, `Potability`, indicates whether the water is safe to drink (1) or not (0).

## Methodology

The project employs a Bayesian approach for logistic regression, with three models designed to classify the water as potable or non-potable:

1. **Model 1**: Basic Bayesian Logistic Regression with normal priors.
2. **Model 2**: Feature selection using Stochastic Search Variable Selection (SSVS).
3. **Model 3**: Bayesian Logistic Regression with alternative priors.

### Data Preprocessing

- Missing values were imputed using the median to handle incomplete data.
- The dataset was cleaned and prepared for model training.

### Bayesian Logistic Regression

Bayesian methods combine prior beliefs with observed data to produce a posterior distribution of model parameters. Markov Chain Monte Carlo (MCMC) sampling was used to estimate the posterior.

Model performance was evaluated using:
- Deviance Information Criteria (DIC)
- Watanabe-Akaike Information Criteria (WAIC)
- Posterior Predictive P-value (PPP)

## Results

The models did not find any significant variables affecting water potability. The posterior predictive p-values for the best-performing models approached 0.5, indicating that the models' predictions were consistent with the real data, although no significant factors were identified.

### Model Performance:

| Model   | DIC   | WAIC   | PPP    |
|---------|-------|--------|--------|
| Model 1 | 4391  | 4391.7 | 0.487  |
| Model 3 | 4391  | 4391.8 | 0.494  |

Model 3 had the best posterior predictive p-value, but no variables were found to be significant predictors of potability.


## Further Improvement

- **Prior Selection**: The results suggest that the chosen priors may not be optimal. Future research could explore different prior distributions based on more extensive domain knowledge.
- **Feature Engineering**: Additional features related to local environmental factors or contaminants could be introduced to improve model accuracy.
- **Model Tuning**: Explore other Bayesian models or machine learning techniques, such as random forests or gradient boosting, to improve classification accuracy.
- **Dataset Expansion**: A larger and more diverse dataset with more features could improve the model’s ability to identify significant factors.
