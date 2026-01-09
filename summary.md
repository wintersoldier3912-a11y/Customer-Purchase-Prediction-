
# Executive Summary: Purchase Prediction Model

## 1. Final Model Choice
**Random Forest Classifier** with class weight balancing. This model outperformed Logistic Regression and Gradient Boosting in terms of F1-score and ROC-AUC during 5-fold cross-validation.

## 2. Final Performance (Test Set)
- **F1-Score:** ~0.82
- **ROC-AUC:** ~0.89
- **Accuracy:** ~85%

## 3. Key Findings & Feature Importance
The top 3 predictors of purchase behavior are:
1. **SpendingScore:** Higher scores strongly correlate with purchase.
2. **EngagementScore:** Digital engagement is a leading indicator.
3. **LastVisitDays:** Recency plays a significant role (lower days = higher probability).

## 4. Recommendations
- **Targeting:** Focus marketing efforts on customers with EngagementScore > 7.
- **Re-engagement:** Automate "We miss you" campaigns for customers reaching 30+ `LastVisitDays`.
- **Next Steps:** Implement SHAP monitoring in production to detect feature drift and explain individual high-value predictions to the sales team.
