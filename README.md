ReadMe For Comparing Classifiers


Business Understanding

The objective of this project is to improve the effectiveness of a bank’s direct marketing campaign by predicting whether a customer will subscribe to a term deposit after being contacted. By identifying customers with a higher likelihood of subscription, the bank can reduce unnecessary outreach, lower operational costs, and allocate marketing resources more efficiently.

Data Cleaning and Preparation

The dataset required preprocessing to ensure it was appropriate for machine learning classification. Several key steps were taken:

The feature duration was removed to prevent target leakage, since call duration is only known after the contact occurs.

The variable pdays contained a sentinel value (999) indicating no prior contact, which was handled through feature engineering rather than treated as a true numeric value.

Binary variables such as loan and housing status were encoded into numeric form.

Categorical variables were transformed using one-hot encoding.

“Unknown” values were retained and handled through imputation instead of dropping rows, which would have resulted in significant data loss.

These steps ensured the dataset remained representative and usable for model comparison.

Descriptive and Inferential Statistics

Descriptive analysis showed that the target outcome is highly imbalanced: most customers do not subscribe to the deposit. This imbalance makes accuracy alone an incomplete performance measure.

Inferential statistical testing highlighted meaningful relationships between predictors and subscription behavior. For example, customers who subscribed tended to be contacted during periods with significantly lower Euribor interest rates, suggesting that macroeconomic conditions influence campaign success. Previous campaign outcomes also showed a strong association with future subscription likelihood, indicating that prior engagement is an important predictor.

Findings

Overall model accuracy was approximately 90%, largely because the majority of customers decline the offer. While the tuned models performed similarly in terms of accuracy, the analysis revealed that customer subscription behavior is influenced by both personal history and broader economic context.

Actionable Insights:

Customers with successful prior campaign outcomes should be prioritized for outreach.

Campaign timing may matter, as subscription rates appear higher during lower-interest-rate environments.

Features that are unavailable before contact (such as call duration) should not be used in realistic predictive deployment.

Next Steps and Recommendations

To improve practical usefulness, future work should evaluate models using metrics beyond accuracy, such as recall, ROC-AUC, lift, and precision–recall performance, since correctly identifying likely subscribers is the true business objective. Additional recommendations include testing more advanced models such as gradient boosting, tuning classification thresholds to balance false positives and missed subscribers, and deploying the model as a ranking tool to target the most promising customers rather than contacting the full population.
