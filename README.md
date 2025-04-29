Weather-Based Precipitation Prediction Using JFK Airport Data

This project aims to predict precipitation levels using historical hourly weather observations at JFK Airport (New York), provided by NOAA. The work was conducted entirely in R, using the tidymodels framework for machine learning and model evaluation.

Project Objectives
	•	Build predictive models to estimate hourly precipitation levels based on atmospheric variables.
	•	Practice machine learning techniques including:
	•	Data cleaning and preprocessing
	•	Exploratory data analysis (EDA)
	•	Model development and selection
	•	Performance evaluation and comparison
	•	Identify the most effective model based on performance metrics (RMSE, MAE, R²).

Project Pipeline

1. Data Preparation
	•	Imported dataset using readr::read_csv().
	•	Selected five core variables:
	•	relative_humidity, dry_bulb_temp_f, precip, wind_speed, station_pressure.
	•	Cleaned the precip column:
	•	Replaced "T" (trace) values with "0.0"
	•	Removed “s” suffix from values like "0.02s".

2. Data Transformation
	•	Converted precip to numeric.
	•	Renamed variables for readability.
	•	Split data into training (80%) and testing (20%) subsets.
	•	Removed rows with missing values for model training.

3. Exploratory Data Analysis (EDA)
	•	Created histograms to visualize distributions of each feature.
	•	Scatter plots and linear fits to explore relationships:
	•	Humidity vs. Precip showed a weak upward trend.
	•	Temperature, Wind Speed, Pressure had minimal predictive linear relationships.
	•	Conclusion: Humidity was the most visually correlated with precipitation.

4. Model Development
  • Developed 3 regression models: Multilinear Regression, Polynomial Regression and Ridge Regression
	•	Applied L2 regularization using glmnet with a penalty of 0.1.

5. Insights & Outcome
	•	All models performed similarly, with negligible differences in RMSE and R².
	•	Ridge regression had the lowest MAE, indicating slightly more accurate predictions in absolute terms.
	•	However, all models had a low R² (~0.045), suggesting that only 4.5% of precipitation variation can be explained by the selected variables.
	•	Conclusion: While regularized models slightly improve stability, the features used alone are insufficient to build a highly predictive model.
