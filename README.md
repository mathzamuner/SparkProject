# Mortality Analysis with PySpark

This project performs an in-depth analysis of mortality data from 2013 to 2015 using PySpark. The primary goal is to uncover insights into the causes of death, demographic factors, and to build a predictive model for the age of death.

## Dataset

The dataset used in this analysis is a collection of public mortality data from the years 2013, 2014, and 2015. The data is in Parquet format and includes a JSON file for decoding causes of death.

- `data/2013-data.parquet`: Mortality data for the year 2013.
- `data/2014-data.parquet`: Mortality data for the year 2014.
- `data/2015-data.parquet`: Mortality data for the year 2015.
- `data/2015_codes.json`: A JSON file containing mappings for cause-of-death codes.

## Project Structure

The project is organized into two main directories:

- `data/`: Contains the raw data files used in the analysis.
- `notebooks/`: Contains the Jupyter notebook with the full analysis.

## Analysis and Findings

The analysis is conducted in the `notebooks/mortality_analysis_spark.ipynb` notebook and covers the following key areas:

### 1. Data Loading and Preprocessing

- The Parquet files for 2013, 2014, and 2015 are loaded into a single Spark DataFrame.
- The cause-of-death codes are decoded using the provided JSON file, making the data more interpretable.
- The data is cleaned by handling missing values and dropping columns with a high number of nulls.
- Categorical features, such as sex, are one-hot encoded to prepare the data for machine learning.

### 2. Exploratory Data Analysis (EDA)

The EDA reveals several key insights:

- **Most Common Age of Death**: The analysis shows that the most frequent age of death is around 87 years.
- **Age of Death by Sex**: The notebook includes a visualization comparing the age of death between males and females.
- **Top 20 Causes of Death**: The most common causes of death are identified, with chronic ischemic heart disease being the leading cause.

### 3. Predictive Modeling

Two machine learning models are trained to predict the age of death:

- **Linear Regression**: A baseline model to predict age.
- **Random Forest Regressor**: A more complex model that provides higher accuracy.

The models are evaluated using RMSE, MAE, and R-squared metrics. The notebook also includes an experiment to assess the impact of `recode` columns on prediction accuracy, showing that their inclusion significantly improves model performance.

### Prerequisites

- Python 3
- Apache Spark
- PySpark
- Matplotlib