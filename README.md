# Time Series Classification with Logistic Regression and Feature Engineering

This project focuses on classifying human activities based on time series data from a wireless sensor network. This includes feature extraction, binary classification using logistic regression, and multiclass classification using L1-penalized multinomial regression and Naïve Bayes. This project is part of Homework 4 for the DSCI 552 course.

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Feature Extraction](#feature-extraction)
- [Binary Classification](#binary-classification)
- [Multiclass Classification](#multiclass-classification)
- [Requirements](#requirements)

## Project Overview
The main objectives of this project are:
1. Extracting time-domain features from time series data.
2. Performing binary classification to distinguish between "bending" and other activities.
3. Exploring multiclass classification to identify specific human activities.

## Dataset
The dataset, known as the AReM (Activity Recognition system based on Multisensor data fusion) data, can be downloaded from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Activity+Recognition+system+based+on+Multisensor+data+fusion). It contains seven folders, each representing a different human activity, with each instance containing six time series:
- `avg rss12`, `var rss12`
- `avg rss13`, `var rss13`
- `avg rss23`, `var rss23`

## Feature Extraction
1. **Time-Domain Features**: Extracted features include:
   - Minimum, Maximum, Mean, Median, Standard Deviation, First Quartile, and Third Quartile for each of the six time series.
2. **Feature Selection**: Three significant features were selected based on statistical analysis for further classification tasks.

## Binary Classification
1. **Logistic Regression**:
   - A logistic regression model was used to classify "bending" activities from others.
   - Recursive feature elimination and p-values were used to select significant features.
   - Stratified cross-validation was employed to handle class imbalance, and metrics such as confusion matrix, ROC, and AUC were reported.
2. **L1-Penalized Logistic Regression**:
   - Used L1 regularization to select features instead of p-values.
   - Cross-validation was conducted for optimal values of `l` (number of segments) and λ (L1 penalty weight).

## Multiclass Classification
1. **Multinomial Logistic Regression**:
   - Built an L1-penalized multinomial regression model to classify all activities.
   - Confusion matrices and ROC curves were analyzed for multiclass classification.
2. **Naïve Bayes Classifier**:
   - Implemented both Gaussian and Multinomial priors to compare performance with logistic regression.
3. **Comparison of Methods**: A comparative analysis was performed to determine the most effective classification approach for this dataset.

## Requirements
The project requires:
- Python
- Libraries: `numpy`, `pandas`, `scipy`, `matplotlib`, `sklearn`