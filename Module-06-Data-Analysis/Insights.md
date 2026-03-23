# Insights

## Fraud Analysis

* Comparing dispute categories across regions did not reveal strong consistent patterns.
* This suggests either:

  * Balanced distribution, or
  * Artificial/random dataset characteristics

## Temporal Behavior

* Analysis across hours and days showed no clear peaks or dips in approval rates.
* Indicates absence of meaningful time-based trends.

## Correlation Findings

* Correlation values help quantify relationships:

  * Strong correlation (close to ±1) → strong linear relationship
  * Weak correlation (near 0) → little to no relationship

Examples:

* Cases vs deaths → strong positive relationship
* Vaccination vs deaths → relatively weaker connection

## Regression Observations

* Regression models explain relationships numerically:

  * R² around 0.66 → moderate explanatory power

* Interpretation:

  * Positive coefficient → variables move together
  * Negative coefficient → inverse relationship

* Importance of p-values:

  * Values below 0.05 indicate statistical significance

## Forecasting Behavior

* Linear forecasting is suitable for steady trends
* Seasonal models (like ETS) work better when patterns repeat over time

## Outlier Observations

* Outliers may:

  * Distort analysis
  * Highlight rare but important events

Decision depends on context:

* Remove → if data error
* Retain → if meaningful

## Geospatial Observations

* Location plays a key role in business performance:

  * Customer proximity influences demand
  * High density leads to competition

## Performance Insights

* DuckDB provides:

  * Faster execution compared to Pandas
  * Lower memory usage
  * Efficient handling of large datasets

## Key Conclusion

Insights should always be interpreted cautiously. Patterns must be validated before drawing conclusions, especially when working with synthetic or sampled data.
