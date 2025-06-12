# CAPSTONE-3-Telco-Customer-Churn

# Telco Customer Churn Prediction

This capstone project aims to predict customer churn in a telecommunications company using machine learning. The primary goal is to help the company take proactive steps to retain high-risk customers and reduce financial losses due to churn.

---

## Project Structure

- `Telco Churn Capstone.ipynb` – Main notebook containing full data pipeline, model training, evaluation, and insights.
- `README.md` – Overview and documentation of the project.
- `/data` – Raw and processed data files (not included here).
- `/images` – Visualizations and plots used in the notebook.

---

## Project Objectives

- Predict whether a customer will churn or not using historical data.
- Interpret model output to derive actionable business insights.
- Optimize model to balance recall (for churners) and cost-effectiveness.
- Compare machine learning strategy with traditional business decision-making.

---

## Tools & Techniques

- **Language**: Python 3.x  
- **Libraries**: `pandas`, `scikit-learn`, `matplotlib`, `seaborn`, `imbalanced-learn`, `shap`
- **Techniques Used**:
  - Data preprocessing & feature encoding
  - Handling class imbalance using SMOTE
  - Model building with Logistic Regression
  - Threshold optimization to prioritize recall
  - Explainable AI via SHAP
  - Business cost-benefit analysis

---

## Key Results

### Technical Conclusion

The final model used Logistic Regression with regularization (`C=100`), SMOTE oversampling, and a decision threshold of 0.30. It achieved a test recall of 93.02% for churners and 58.07% accuracy for non-churners. The F2 score, which places more weight on recall than precision, was selected as the key evaluation metric to align with the business objective of minimizing customer loss.

However, there is a noticeable gap between the training F2 score (~0.93) and the test F2 score (~0.76), indicating that the model is overfitting the training data. Overfitting in this context suggests the model is learning noise or patterns specific to the training set that do not generalize well. This is likely compounded by the synthetic nature of SMOTE and the sparsity introduced by one-hot encoding. Regularization, alternative modeling strategies, or more data could mitigate this issue.

### Business Conclusion

Three scenarios were compared to evaluate financial outcomes:

- Retain everyone (assume all customers are at risk): $97,100 in retention costs.
- Do nothing (assume no one is at risk): $90,300 in acquisition costs.
- Use machine learning predictions: $60,200 (including both retention and acquisition).

By using machine learning to target only high-risk customers, the company can save up to $36,900. Customers most likely to churn are those with short tenure, on month-to-month contracts, and not using additional services like OnlineSecurity or TechSupport. Many of these are newer customers who may not understand the benefits of bundled services or long-term plans. This insight suggests a need for improved onboarding and targeted marketing.

---

## Recommendations

### Technical Recommendations

- Reduce overfitting through stronger regularization or alternative model types like Random Forest or XGBoost, with careful cross-validation and hyperparameter tuning.
- Apply stratified k-fold cross-validation to improve generalizability and performance estimation.
- Improve feature engineering by including behavior-based metrics (e.g., usage frequency, service changes).
- Consider dimensionality reduction techniques to mitigate sparsity from one-hot encoding.
- Implement a monitoring pipeline for real-world feedback to retrain and recalibrate the model as customer behavior evolves.

### Business Recommendations

- Proactively engage high-risk customers with personalized bundles, discounts, or free trials of premium services.
- Strengthen the onboarding process to help new customers understand available service packages and long-term contract benefits.
- Implement quarterly customer reviews to identify those with minimal engagement or no add-on services, and re-engage them through targeted campaigns.
- Equip marketing and customer service teams with churn predictions to personalize outreach and improve customer satisfaction.

---

## Cost Assumptions (Sources)

- **Customer acquisition cost**: $350  
  Source: [UpGrowth](https://www.upgrowth.in/understanding-the-average-customer-acquisition-cost-by-industry/)

- **Retention incentive cost**: $100  
  Source: [Paylode](https://paylode.com/articles/customer-retention-cost)

---

## Dataset

The dataset includes customer demographics, subscription types, tenure, contract details, and churn labels. It is commonly used in binary classification examples and is representative of a typical telecom provider's customer base.

---

## Future Work

- Deploy the model through a web app using Flask or Streamlit for internal stakeholder access.
- Integrate real-time data sources to dynamically update churn predictions.
- Explore multiclass churn classification (e.g., voluntary, involuntary, billing-related) for richer insights.

---

## Contact

**Kaila Amira**  
Email: *kaaailamira@gmail.com*  
