# Credit Card Fraud Detection
## Why I Built This
When I was working at Uber as a Risk & Compliance Specialist, I dealt 
with fraud cases every single day. Someone booking a ride with a stolen 
card. Customers reporting their credit card was used without permission. 
I manually investigated each case, verified it, and blocked the card.
Finding fraud manually is exhausting and slow. You can miss cases. 
You cannot process thousands of transactions at once.
So I built this model to do it automatically — the same job I used to 
do by hand, now done by machine in milliseconds.
## The Data
- 284,807 real credit card transactions
- Only 492 are fraud — that is 0.17%
- Source: Kaggle — ULB Machine Learning Group
This imbalance is exactly what makes fraud detection hard. A lazy model 
can score 99.8% accuracy by flagging nothing as fraud. That is useless.
## My Approach
1. Explored the data and visualised the class imbalance
2. Preprocessed — scaled Amount feature, removed Time, 80/20 train/test split
3. Built a baseline Logistic Regression model
4. Handled class imbalance using class_weight='balanced'
5. Improved with Random Forest
## Results
| Model | Precision | Recall | F1 Score |
|-------|-----------|--------|----------|
| Logistic Regression | 85% | 57% | 0.68 |
| LR with class_weight | 6% | 92% | 0.12 |
| Random Forest | 97% | 74% | 0.84 |
Random Forest was the winner — 97% precision with 74% recall.
## What I Learned
Accuracy is a misleading metric for imbalanced data. Recall is what 
matters for fraud detection — missing a real fraud means a criminal 
walks free and the bank loses money.
## Tools
Python, Pandas, Scikit-learn, Matplotlib
