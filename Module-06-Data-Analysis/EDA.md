# Exploratory Data Analysis (EDA)

## Introduction

Exploratory Data Analysis (EDA) is the foundation of any data-driven project. It focuses on understanding the dataset, identifying patterns, and spotting anomalies before applying statistical models or machine learning techniques.

## Data Ingestion

* Data is loaded using **Pandas**, often from optimized formats like **Parquet**.
* Benefits of Parquet:

  * Faster processing compared to CSV/Excel
  * Efficient storage with compression
  * Column-based structure for analytics

```python
import pandas as pd
df = pd.read_parquet("transactions.parquet")
```

## Understanding the Dataset

Initial inspection helps build familiarity:

```python
df.head()
df.info()
df.describe()
```

Key checks:

* Column names and meanings
* Data types
* Missing or inconsistent values

## Exploring Fraud Trends

* Pivot tables are useful for summarizing categorical patterns:

```python
pd.pivot_table(df, index="region", columns="dispute_type", values="id", aggfunc="count")
```

This helps:

* Compare fraud vs non-fraud cases
* Identify region-wise behavior

## Relationship Analysis

* Evaluate how variables interact:

  * Transaction amount vs approval rate
  * Domestic vs international transactions

```python
df.corr(numeric_only=True)
```

## Time-Based Exploration

* Extract time components from timestamps:

```python
df["hour"] = df["timestamp"].dt.hour
df["day"] = df["timestamp"].dt.date
```

* Analyze trends using:

  * Hourly distributions
  * Heatmaps for approval rates

## Detecting Outliers

Using the IQR method:

* IQR = Q3 − Q1
* Lower bound = Q1 − 1.5 × IQR
* Upper bound = Q3 + 1.5 × IQR

```python
outliers = df[(df["amount"] < lower) | (df["amount"] > upper)]
```

## Visualization Techniques

* Box plots → detect extreme values
* Heatmaps → time-based insights
* Scatter plots → relationships between variables

## Summary

EDA provides clarity about the dataset and ensures that further analysis is based on reliable understanding rather than assumptions.
