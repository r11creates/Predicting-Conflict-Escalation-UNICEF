# UNICEF-Predicting-Conflict-Escalation

## Table of Contents
1. [Project Overview](#project-overview)
2. [Problem Statement](#problem-statement)
3. [Data Description](#data-description)
4. [Methodology](#methodology)
5. [Model Development](#model-development)
6. [Results and Findings](#results-and-findings)
7. [Ethical Considerations](#ethical-considerations)
8. [Technical Implementation](#technical-implementation)
9. [Installation and Usage](#installation-and-usage)
10. [Future Work](#future-work)
11. [License](#license)

## Project Overview

This project aims to enhance conflict prediction capabilities in less fortunate parts of the world by developing a meta-model that predicts the performance of different conflict prediction models based on country-specific characteristics. The project was conducted in collaboration with UNICEF to improve resource allocation and conflict preparedness in unstable regions.

### Key Features:
- Development of a meta-model to predict the performance of three conflict prediction models (Transformer, FFNN, xgboost)
- Utilization of linear regression to analyze country-specific predictors
- Implementation of feature selection techniques to improve model interpretability and generalizability
- Comprehensive statistical analysis and model validation
- Creation of data visualizations for enhanced interpretation of results
- Analysis of ethical implications and potential real-world impacts

## Problem Statement

UNICEF utilizes three predictive machine-learning models (Transformer, FFNN, and xgboost) to forecast conflict escalation in unstable regions. However, the accuracy of these models can vary depending on the characteristics of the country being analyzed. Our task was to design a meta-model that can predict which predictive model will perform better for different types of countries, thereby improving overall prediction accuracy and resource allocation.

## Data Description

The project utilized two primary datasets:

1. **Conflict Prediction Dataset**: 
   - Contains predicted probabilities of near-term conflict for the three models (Transformer, FFNN, xgboost)
   - Includes real-world data on whether conflict occurred in a given month

2. **Country Statistics Dataset**:
   - Contains over 1300 different statistics for each country
   - Includes both continuous variables (e.g., population, GDP) and categorical variables (e.g., World Bank lending category)

## Methodology

Our approach involved the following key steps:

1. **Data Preprocessing**: 
   - Standardization of continuous variables
   - Handling of categorical variables

2. **Feature Selection**:
   - Initial model creation with all available predictors
   - Iterative removal of predictors based on p-value analysis
   - Reduction from 1300+ predictors to 17 key variables

3. **Model Development**:
   - Utilization of linear regression to predict the error difference between historical conflict results and model predictions
   - Implementation of techniques to address multicollinearity

4. **Model Validation**:
   - Normality tests for error distribution
   - Residual analysis
   - Cross-validation using 80-20 split for training and testing

5. **Visualization**:
   - Creation of heatmaps to visualize multicollinearity
   - Geographic representation of key predictors

## Model Development

The model development process involved several iterations:

1. **Initial Model**: Included all available predictors (both categorical and continuous)
2. **Intermediate Models**: Iterative removal of predictors with high p-values
3. **Final Model**: Included 17 key predictors with improved multicollinearity characteristics

Key considerations during model development:
- Balancing the number of predictors to maximize R-squared while minimizing multicollinearity
- Standardization of continuous variables for fair comparison
- Analysis of condition number to assess overall multicollinearity

## Results and Findings

Key findings from the project include:

1. The final model achieved comparable performance to the initial model, with error differences typically less than 1%
2. Reduction in the number of predictors from 1300+ to 17 improved model interpretability and generalizability
3. Identification of key country characteristics that influence the performance of different conflict prediction models
4. Visual representation of model performance across different geographical regions

## Ethical Considerations

The project involved careful consideration of ethical implications, including:

- Potential consequences of accurate and inaccurate predictions on societal stability
- Risks of creating self-fulfilling prophecies through conflict predictions
- Equitable access to prediction technologies across different governments and organizations
- Long-term societal impacts of widespread use of conflict prediction models

## Technical Implementation

The project is implemented in Python, utilizing several key libraries for data analysis, machine learning, and visualization:

- **Pandas**: For data manipulation and analysis
- **NumPy**: For numerical computing
- **Scikit-learn**: For machine learning models and preprocessing
- **Statsmodels**: For statistical computations and diagnostics
- **Matplotlib** and **Seaborn**: For data visualization
- **Geopandas**: For geographical data handling and visualization

Key components of the implementation include:

1. **Data Preprocessing**: 
   - Standardization of continuous variables using `StandardScaler`
   - One-hot encoding of categorical variables

2. **Feature Selection**:
   - Utilization of p-values from `statsmodels` OLS regression results
   - Iterative feature removal based on significance thresholds

3. **Model Development**:
   - Implementation of linear regression using `scikit-learn`'s `LinearRegression`
   - Multicollinearity analysis using condition number and variance inflation factor (VIF)

4. **Model Validation**:
   - Implementation of train-test split and cross-validation using `scikit-learn`
   - Calculation of performance metrics (RMSE, R-squared)

5. **Visualization**:
   - Creation of correlation heatmaps using `seaborn`
   - Geographical plots using `geopandas` and `matplotlib`

## Installation and Usage

To set up the project environment and run the code, follow these steps:

1. Clone the repository:
   ```
   git clone https://github.com/your-username/conflict-prediction-meta-model.git
   cd conflict-prediction-meta-model
   ```

2. Create a virtual environment (optional but recommended):
   ```
   python -m venv venv
   source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
   ```

3. Install the required dependencies:
   ```
   pip install -r requirements.txt
   ```

4. Run the main script:
   ```
   python main.py
   ```

   This will execute the entire pipeline, from data preprocessing to model evaluation and visualization.

Note: Ensure you have Python 3.7+ installed on your system before setting up the project.

## Future Work

Potential areas for future research and development include:

1. Incorporation of additional data sources to enhance prediction accuracy
2. Exploration of alternative machine learning techniques for meta-model development
3. Development of a user-friendly interface for model deployment and interpretation
4. Longitudinal studies to assess the long-term impact of using the meta-model for resource allocation
5. Collaborative efforts with ethicists and policymakers to develop guidelines for responsible use of conflict prediction technologies


## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
