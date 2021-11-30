# AutoXGB for Credit Card Fraud Detection

Link to full writeup on Medium: *Coming Soon*

## Context
- XGBoost has established itself as one of the most important machine learning algorithms due to its versatility and impressive performance. 
- Having used XGBoost for previous projects, I am always open to making its implementation faster, better, and cheaper. 
- My curiosity was piqued when I came across AutoXGB (https://github.com/abhishekkrthakur/autoxgb), which claims to be a 'no-brainer' library for simplifying the training and deployment of XGBoost. 
- Given my work in the financial services sector where fraud is a significant concern, it would be an excellent opportunity to use credit card fraud data to assess how AutoXGB fares against the standard XGBoost setup usually used.

## Dataset
- Simulated credit card transaction data from the research collaboration between Worldline and Machine Learning Group (https://github.com/Fraud-Detection-Handbook/simulated-data-transformed)

## Steps
- Data processing of credit card transaction dataset, with special focus on handling class imbalance with SMOTE and Random Undersampling
- Select appropriate performance metric for binary classification task i.e. Average Precision
- Run training for baseline model: XGBoost with RandomizedSearchCV
- Run training for AutoXGB 
- Compare performance and speed

## Verdict
- AutoXGB delivered a slightly higher Average Precision score of 0.782 as compared to the baseline score of 0.776.
- The time taken for AutoXGB training is approximately 30% shorter, taking just 9 minutes as compared to the baseline of 13 minutes.
- Another key advantage of AutoXGB is that we are only one command line away from serving the model as a FastAPI endpoint. This setup reduces the time to model deployment, which is a critical factor beyond training time.
- While the performance metrics give AutoXGB an edge, one of its most significant issues is the loss of granular control in the parameter settings e.g. unable to set `eval_metric` for XGBClassifier, unable to set specific validation sets for cross-validation
- At the end of the day, while solutions like AutoXGB do well in simplifying (and possibly improving) XGBoost implementation, data scientists need to understand its limitations by knowing what goes on under the hood.

## Files/Folders
