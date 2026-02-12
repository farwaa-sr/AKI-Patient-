# AKI-Patient-
Comprehensive ML project for predicting Acute Kidney Injury (AKI) stages from patient data. Features exploratory data analysis, data preprocessing with missing value imputation and class rebalancing, dimensionality reduction visualization using PCA and t-SNE, classification models including hyperparameter-tuned KNN and Gaussian Naive Bayes.

## Project Overview: 
This is an exploratory data analysis and machine learning classification project focused on predicting Acute Kidney Injury (AKI) stages using patient data.

## Main Sections:
### 1. Imports & Setup - Standard ML/data science libraries (pandas, sklearn, matplotlib, seaborn, etc.) plus visualization libraries like missingno and sweetviz.

### 2. Data Generation & Exploration
- Loads AKI patient data from CSV
- Dataset contains various patient features and AKI stage labels (0-3 stages)

### 3. Data Preprocessing

- Missing Values Analysis: Identifies features with >40% missing values and removes them
- Data Imputation: Missing values filled with column means (excluding removed features)
- Class Imbalance Handling: Original dataset heavily skewed toward class 0; rebalanced by keeping only 10% of class 0 samples

### 4. Train-Test Split
- 70-30 split for training and testing
- Data standardized using StandardScaler separately for train/test to avoid data leakage

### 5. Unsupervised Learning & Visualization
- PCA: Reduced to 20 components for variance analysis
- t-SNE: Dimensionality reduction visualization showing that stages 0 and 3 are well-separated, while stages 1 and 2 overlap significantly
- Sweetviz report generation for exploratory analysis

### 6. KNN Classification
- Hyperparameter tuning with GridSearchCV
- Parameters optimized: n_neighbors (3-15), weights (uniform/distance), metric (euclidean/manhattan)
- Uses StratifiedKFold cross-validation (5 folds)
- Optimized for macro-F1 score
- Results: Full classification report and confusion matrix visualization

### 7. Gaussian Naive Bayes Classification
- Similar pipeline with GridSearchCV
- Hyperparameter: var_smoothing (1e-12 to 1e-6)
- Same evaluation metrics: accuracy, precision, recall, F1-score
- Confusion matrix visualization in purple heatmap

## Unified Results Comparison
- Summary table comparing both models across accuracy, precision_macro, recall_macro, and F1_macro scores
- Key Insights: The t-SNE visualization reveals that the classification task is moderately challenging due to overlap between classes 1 and 2, though classes 0 and 3 are well-separated.
PCA: Reduced to 20 components for variance analysis
t-SNE: Dimensionality reduction visualization showing that stages 0 and 3 are well-separated, while stages 1 and 2 overlap significantly
Sweetviz report generation for exploratory analysis
