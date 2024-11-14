# WDW-Waiting
Predict Wait Times at Walt Disney World
The project focuses on developing a predictive model for maximum wait times at Walt Disney World using data from 2018 to 2022. The goal is to enhance visitor traffic management and resource optimization.

## Data Introduction and Preprocessing

The dataset consists of 3.5 million records, including variables like wait times, attraction capacity, and guest numbers. Key preprocessing steps involved handling missing values, normalizing data, converting date and time formats, and creating new features such as event duration and time-based variables.

## Feature Engineering

1. **Dependent Variable Transformation**: The original wait time data was right-skewed, so a logarithmic transformation was applied for normalization.

2. **Time-Based Features**: Features were created to capture seasonal patterns, weekend effects, and daily wait time trends.

3. **Attraction-Based Features**: Attractions were categorized by popularity.

4. **Time Series Features**: Lag and rolling mean features were added to capture historical wait time trends.

## Feature Selection

One-hot encoding was used for categorical data, and multicollinearity was assessed using VIF. Features with VIF values over 15 were excluded for linear models, but retained for non-linear models.

## Model Development

1. **Linear Regression**: Showed moderate explanatory power but struggled with non-linear relationships.

2. **Non-linear Models**: Advanced techniques like Decision Tree, Random Forest, XGBoost, LightGBM, and Neural Network were used to capture complex patterns.

   - **Decision Tree**: Highlighted Lag1 and guest numbers as key predictors.
   - **Random Forest**: Achieved the best performance with GridSearchCV tuning, emphasizing Lag1 and RollingMean_Hour.
   - **XGBoost and LightGBM**: Showed strong predictive power, focusing on historical and recent trends.
   - **Neural Network**: Struggled with non-zero values, indicating limitations in capturing certain data characteristics.

## Model Comparison

Random Forest with tuning provided the lowest mean squared error and high R-squared value, outperforming other models. While Neural Networks showed potential, simpler models like Random Forest were more effective for this dataset.

## Conclusion

The Random Forest model is recommended for its accuracy and interpretability, making it suitable for Disney’s operational needs. This case underscores the importance of selecting models that align with data characteristics.
