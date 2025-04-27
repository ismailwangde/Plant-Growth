# Plant Growth Analysis Based on Pollution Metrics
This repository explores the relationship between plant growth and various environmental factors across different locations. The study examines soil moisture, temperature, air quality, total dissolved solids (TDS), plant height, and the impact of location-based pollution levels on these variables.

## Methodology
### Multivariate Analysis
Performed a MANOVA to assess the combined impact of predictors on the dependent variables:

Model: SM + Temp + AirQuality + TDS + Height ~ Location

Results showed significant differences across locations with high F-values indicating strong location effects.

### Univariate Analysis
Conducted ANOVA for Soil Moisture:

Result: Greatest F-value for the Location predictor, highlighting significant location-based differences.

Used Tukey’s HSD for post-hoc analysis:

Conclusion: Mulund > Andheri > Bhandup > Goregaon > Vile Parle in terms of Soil Moisture.

### Regression Models
Developed models to predict plant height:

Linear Regression:

Coefficients: [ -2.95, -12.16, 10.90, 6.57]

Intercept: -237.40

Ridge Regression:

Applied regularization with alpha=800.

Coefficients: [-1.44, -1.25, 1.01, 4.37]

### Feature Engineering and Model Optimization
Created dummy variables for categorical data (Location, TDS).

Optimized the regression model using polynomial features and interaction terms:

Best Model: Height ~ Location_Mulund + Temp + Location_Parle + AirQuality*TDS_50 + Location_Bhandup + I(Temp**2)

R-squared: 0.547 (Adjusted: 0.535)

### Multicollinearity Check
Calculated Variance Inflation Factor (VIF) for all predictors to ensure low multicollinearity.

## Key Results
### Best Predictors for Height:

Temperature: Positive influence.

Air Quality: Negative influence.

Interaction effects: Air Quality and TDS_50 had significant combined effects.

### Location Insights:

Locations significantly impact all metrics, with Mulund showing the highest soil moisture.

## Conclusion
This study reveals that environmental pollution levels and specific factors like temperature and air quality have a measurable impact on plant growth. The models developed provide insights into how location-based factors influence growth metrics.
