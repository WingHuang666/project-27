# project-27


# Indian Bail Judgments — Machine Learning Analysis

## 1. Project Overview

This project analyzes Indian bail judgment cases using exploratory data analysis (EDA), supervised machine learning, natural language processing (NLP), and unsupervised clustering.

The project aims to examine relationships between case characteristics and bail outcomes, compare predictive models, identify important features, and explore patterns across different groups of cases.

## 2. Dataset

**Dataset:** `Indian-Bail-Judgments new.csv`

The dataset contains 1,200 observations and 21 variables, covering Indian bail judgments from 1975 to 2025.

The variables include:

- **Case information:** Year, court, region, and crime type.
- **Bail information:** Bail type and bail outcome.
- **Defendant information:** Gender and prior case history.
- **Legal narratives:** Case facts, legal issues, judgment reasoning, and summaries.
- **Additional information:** Judges and other case-related indicators.

## 3. Research Questions

The project investigates five research questions:

**RQ1: Bail Outcome Prediction Using Structured Features**

Can structured case characteristics predict whether bail is granted or rejected?

**RQ2: Simplified Bail Outcome Prediction**

How effectively can crime type and bail type alone predict bail outcomes?

**RQ3: Legal Narrative Analysis**

Does incorporating case facts and legal issues improve bail outcome prediction compared with structured features alone?

**RQ4: Bail Cancellation Classification**

Can structured case characteristics identify bail cancellation-related cases?

**RQ5: Case Clustering**

Can bail judgment cases be grouped into meaningful clusters based on their characteristics and legal narratives?

## 4. Data Preprocessing

The following preprocessing procedures are applied:

- Inspect data types, missing values, duplicates, and categorical distributions.
- Clean and standardize text variables.
- Apply One-Hot Encoding to categorical features.
- Use TF-IDF to transform legal narratives into numerical features.
- Identify and separate multiple judge names within individual cells.
- Handle unknown or missing values appropriately.
- Exclude outcome-revealing variables from predictive features to reduce data leakage.
- Prepare numerical and categorical features for machine learning pipelines.

Preprocessing is integrated into model pipelines where appropriate to avoid information leakage between training and testing datasets.

## 5. Exploratory Data Analysis

EDA examines the dataset's overall structure and distributions, including:

- Bail outcome frequencies.
- Crime type distributions.
- Bail grant rates across crime types and bail procedures.
- Defendant gender distributions and observed grant rates.
- Judge information and legal narrative characteristics.
- Relationships between selected case characteristics and outcomes.

Visualizations include bar charts, heatmaps, and summary tables.

## 6. Machine Learning Models

The supervised learning analysis compares the following models:

1. Logistic Regression
2. Random Forest
3. Extra Trees
4. Dummy Classifier (baseline)

Model selection is based on the evaluation metric appropriate to each research question.

### Evaluation Metrics

- **Balanced Accuracy:** Evaluates classification performance across both classes.
- **F1 Score:** Balances precision and recall.
- **ROC-AUC:** Measures the ability to distinguish between classes.
- **Average Precision (AP):** Evaluates positive-class ranking performance, particularly for imbalanced classification.
- **Confusion Matrix:** Examines correct and incorrect predictions by class.

Cross-validation is used for model comparison, followed by evaluation on a held-out test set.

## 7. Feature Importance

Permutation Importance is used to evaluate the contribution of individual features to predictive performance.

Feature importance is calculated using a selected non-Dummy model and visualized with horizontal bar charts.

The analysis focuses on identifying predictive relationships rather than establishing causality.

## 8. Natural Language Processing

Legal narrative variables are processed using TF-IDF vectorization.

The text-processing pipeline includes:

- Text cleaning and normalization.
- Unigram and bigram extraction.
- Removal of extremely rare and overly common terms.
- Conversion of narrative text into numerical features.
- Integration of text features with structured case characteristics.

This approach allows textual information to contribute to predictive modeling without treating entire narratives as simple categorical labels.

## 9. Clustering Analysis

Unsupervised learning is used to explore similarities among cases.

The clustering workflow includes:

- Feature preprocessing and transformation.
- Dimensionality reduction using Truncated SVD.
- K-Means clustering.
- Elbow Method for evaluating within-cluster inertia.
- Silhouette Score for assessing cluster separation.
- Selection of an appropriate number of clusters.
- Cluster profiling and comparison.
- Two-dimensional visualization of cluster assignments.

Cluster profiles are examined using case characteristics, bail outcomes, and additional indicators.

## 10. Project Structure

```text
Indian-Bail-Judgments/
│
├── Indian-Bail-Judgments new.csv
│
├── Indian_Bail_Judgments_Project.qmd
│
└── README.md
```

## 11. Requirements

The project uses Python and Quarto.

Required Python libraries:

```bash
pip install numpy pandas matplotlib seaborn scipy scikit-learn joblib
```
