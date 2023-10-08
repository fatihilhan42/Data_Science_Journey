# Regression Evaluation Metrics

Regression is a machine learning task where the goal is to predict continuous numerical values. To assess the performance of regression models, various evaluation metrics are employed. In this document, we'll explore some of the most commonly used evaluation metrics for regression tasks.

## Common Regression Metrics

### 1. Mean Absolute Error (MAE)

- **Formula:** (1/n) * Σ |actual - predicted|
- **Description:** MAE calculates the average absolute differences between actual and predicted values. It provides an intuitive measure of prediction errors.

### 2. Mean Squared Error (MSE)

- **Formula:** (1/n) * Σ (actual - predicted)^2
- **Description:** MSE computes the average squared differences between actual and predicted values. It penalizes large errors more heavily than MAE.

### 3. Root Mean Squared Error (RMSE)

- **Formula:** √(MSE)
- **Description:** RMSE is the square root of MSE and provides a more interpretable measure of prediction errors in the same units as the target variable.

### 4. R-squared (R²) or Coefficient of Determination

- **Formula:** 1 - (SSR/SST)
- **Description:** R² measures the proportion of the variance in the target variable that is predictable from the independent variables. It ranges from 0 to 1, where higher values indicate a better fit.

### 5. Mean Absolute Percentage Error (MAPE)

- **Formula:** (1/n) * Σ |(actual - predicted) / actual| * 100%
- **Description:** MAPE calculates the average percentage difference between actual and predicted values. It is useful when you want to express errors as a percentage of the actual values.

## Choosing the Right Metrics

The choice of regression metrics depends on the specific problem and the nature of the data. MAE and RMSE are commonly used and provide a good balance between interpretability and sensitivity to errors. R² can help assess how well the model explains the variance in the data.

## Hands-On Examples

In the upcoming sections, we'll provide hands-on examples and code snippets demonstrating how to calculate these regression metrics using popular Python libraries like Scikit-Learn. Understanding these metrics and how to apply them will enable you to evaluate and fine-tune your regression models effectively.

In summary, regression evaluation metrics are essential for quantifying the performance of regression models. By utilizing these metrics and interpreting their results, you can gain valuable insights into the accuracy and predictive power of your regression models.
