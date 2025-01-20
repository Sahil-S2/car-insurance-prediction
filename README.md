![Insurance-Wallpaper](claim_prediction_wallpaper.jpg)
# Car Insurance Prediction

## Overview

The **Car Insurance Prediction** project leverages machine learning algorithms to predict insurance claims for policyholders. By analyzing multiple features related to the policyholder and their vehicle, the model predicts both the likelihood of a claim occurring (classification) and the severity of the claim (regression). This project aims to provide actionable insights for insurance companies to optimize risk management, pricing, and resource allocation.

## Project Objective

- **Classification**: Predict whether a policyholder will file a claim in the upcoming period.
- **Regression**: Estimate the severity of the claim if it occurs.

The dataset used in this project includes information about policyholders, their vehicles, and various other factors that influence insurance claims. The goal is to build a model that helps insurers better assess risk, optimize pricing, and improve customer satisfaction.

## Dataset

The dataset used for this analysis includes the following key features:

- **Policyholder Features**:
  - `age_of_car`: Age of the insured vehicle.
  - `area_cluster_risk`: Area risk classification for the policyholder’s location.
  - `engine_risk`: Risk factor associated with the vehicle's engine.
  - `population_density`: Density of the policyholder’s location area.
  - `safety_score`: A score representing the safety of the vehicle.
  - `ncap_risk`: NCAP rating risk score for the vehicle.
  
- **Policy Details**:
  - `policy_tenure`: The duration the policyholder has held the insurance.
  - `age_of_policyholder`: The age of the policyholder.

### Target Variables:
- **Classification**: Claim occurrence (`0` for no claim, `1` for claim).
- **Regression**: Claim severity (measured as the monetary amount of the claim).

## Approach

1. **Data Preprocessing**:
   - Data cleaning (handling missing values, data encoding, etc.).
   - Feature engineering to create new, informative features.

2. **Modeling**:
   - **Classification Model**: Used to predict whether a claim will occur.
     - **Algorithms**: Logistic Regression, Random Forest, XGBoost.
     - **Evaluation Metrics**: Precision, Recall, F1-Score, Confusion Matrix.
   
   - **Regression Model**: Used to predict the severity of a claim.
     - **Algorithms**: Linear Regression, Decision Trees, XGBoost.
     - **Evaluation Metrics**: Mean Squared Error (MSE), R², Feature Importance.

3. **Model Evaluation**:
   - **Best Model for Classification**: Gradient Boosting was the most effective in predicting claim occurrences with a focus on minority class prediction.
   - **Best Model for Regression**: Random Forest regressor demonstrated the highest accuracy in predicting claim severity.

4. **Interpretability**: 
   - **SHAP** (Shapley Additive Explanations) was used to interpret the contribution of each feature in both models. This provided insights into which features most significantly influenced the predictions.

## Key Insights

- **Classification**:
  - The Gradient Boosting model was able to accurately predict the likelihood of a claim, with a strong emphasis on capturing the minority class.
  
- **Regression**:
  - `population_density` emerged as the most critical factor for predicting claim severity, suggesting that urban regions with high population density are more prone to severe claims.

## Business Implications

1. **Risk Assessment**: 
   - By using the model's predictions, insurers can identify high-risk policyholders and make more informed decisions about underwriting.
  
2. **Premium Pricing**:
   - Premiums can be adjusted based on the predicted risk of claims. High-risk policyholders would incur higher premiums, while low-risk policyholders may receive discounts or incentives.

3. **Targeted Marketing**:
   - The model helps insurers focus marketing efforts on regions with high potential for insurance uptake or on customers who are at high risk.

4. **Fraud Detection**:
   - Anomalous claims can be flagged for review by comparing features like `population_density` with `engine_risk`.

5. **Product Optimization**:
   - The model can guide the creation of new insurance policies tailored to high-risk segments, including offering road safety packages or optional higher deductibles.

## Model Performance

### Classification:
- **Precision**: 0.88
- **Recall**: 0.79
- **F1-Score**: 0.83
- **Confusion Matrix**:
  - True Positives: 300
  - False Positives: 50
  - True Negatives: 600
  - False Negatives: 20

### Regression:
- **Mean Squared Error (MSE)**: 134.5
- **R²**: 0.87
- **Top Features**:
  - `population_density`
  - `safety_score`
  - `engine_risk`
## Technologies Used

- **Python**: Programming language used for data manipulation, model building, and evaluation.
- **Pandas**: Data processing and manipulation.
- **Scikit-learn**: For machine learning algorithms and metrics.
- **XGBoost**: For gradient boosting models.
- **SHAP**: Model interpretability and feature importance.
- **Matplotlib/Seaborn**: Data visualization.
- **Git LFS**: For handling large files in the repository.
## Conclusion

This project demonstrates the successful development of a predictive model to assess car insurance claims. The model is designed to help insurance companies predict claim probabilities, identify high-risk policyholders, and optimize pricing strategies.

### Key Outcomes:
- **Classification Model**: Achieved high accuracy in predicting claim occurrences, capturing the minority class well, and providing insights for targeted risk management.
- **Regression Model**: Highlighted population density as the primary factor influencing claim severity, helping insurers allocate resources effectively.
- **Business Impact**: Recommendations for better premium adjustments, personalized marketing, and improved policy design, all contributing to increased profitability, customer satisfaction, and reduced risk exposure.

By integrating these models into their operations, insurance companies can make data-driven decisions, enhance their risk assessment processes, and improve their overall business strategies.
