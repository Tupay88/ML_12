Team Member 3's Model Notes and Findings to be added by them here using this the template below as a guide
### Model 1: Baseline [Model Name]

**Purpose:** Establish baseline performance

**Model Details:**
- **Algorithm:** [e.g., Logistic Regression, Decision Tree]
- **Library:** [e.g., scikit-learn]
- **Hyperparameters:** 
  - [param1]: [value]
  - [param2]: [value]
  - [List all or note "default parameters"]

**Training:**
- **Training Time:** [X] seconds/minutes
- **Date Trained:** [Date]

**Performance Metrics:**
| Metric | Score |
|--------|-------|
| Accuracy | [X.XX] |
| Precision (weighted) | [X.XX] |
| Recall (weighted) | [X.XX] |
| F1-Score (weighted) | [X.XX] |

**Per-Class Performance:**
| Class | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| [Class 1] | [X.XX] | [X.XX] | [X.XX] | [count] |
| [Class 2] | [X.XX] | [X.XX] | [X.XX] | [count] |
| [Class 3] | [X.XX] | [X.XX] | [X.XX] | [count] |
| [Class 4] | [X.XX] | [X.XX] | [X.XX] | [count] |
| [Class 5] | [X.XX] | [X.XX] | [X.XX] | [count] |

**Observations:**
- [What worked well?]
- [What didn't work?]
- [Any surprises?]

**Visualizations Created:**
- Confusion matrix: `reports/figures/model_results/baseline_confusion_matrix.png`
- [Other visualizations]

---

### Model 2: [Model Name]

**Purpose:** [Why you're trying this model]

**Model Details:**
- **Algorithm:** [e.g., Random Forest Classifier]
- **Library:** [e.g., scikit-learn]
- **Hyperparameters:** 
  - n_estimators: [value]
  - max_depth: [value]
  - [etc.]

**Training:**
- **Training Time:** [X] seconds/minutes
- **Date Trained:** [Date]

**Performance Metrics:**
| Metric | Score |
|--------|-------|
| Accuracy | [X.XX] |
| Precision (weighted) | [X.XX] |
| Recall (weighted) | [X.XX] |
| F1-Score (weighted) | [X.XX] |

**Per-Class Performance:**
| Class | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| [Class 1] | [X.XX] | [X.XX] | [X.XX] | [count] |
| [Class 2] | [X.XX] | [X.XX] | [X.XX] | [count] |
| [Class 3] | [X.XX] | [X.XX] | [X.XX] | [count] |
| [Class 4] | [X.XX] | [X.XX] | [X.XX] | [count] |
| [Class 5] | [X.XX] | [X.XX] | [X.XX] | [count] |

**Comparison to Baseline:**
- Accuracy improvement: [+/- X.XX percentage points]
- F1-Score improvement: [+/- X.XX percentage points]
- [Key differences]

**Observations:**
- [What worked better than baseline?]
- [What didn't improve?]
- [Notable patterns in errors?]

**Visualizations Created:**
- Confusion matrix: `reports/figures/model_results/rf_confusion_matrix.png`
- Feature importance: `reports/figures/model_results/rf_feature_importance.png`
- [Other visualizations]

---

### Model 3: [Model Name]

**Purpose:** [Why you're trying this model]

**Model Details:**
- **Algorithm:** [e.g., XGBoost, Gradient Boosting, SVM]
- **Library:** [e.g., xgboost, scikit-learn]
- **Hyperparameters:** 
  - [param1]: [value]
  - [param2]: [value]
  - [etc.]

**Training:**
- **Training Time:** [X] seconds/minutes
- **Date Trained:** [Date]

**Performance Metrics:**
| Metric | Score |
|--------|-------|
| Accuracy | [X.XX] |
| Precision (weighted) | [X.XX] |
| Recall (weighted) | [X.XX] |
| F1-Score (weighted) | [X.XX] |

**Per-Class Performance:**
| Class | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| [Class 1] | [X.XX] | [X.XX] | [X.XX] | [count] |
| [Class 2] | [X.XX] | [X.XX] | [X.XX] | [count] |
| [Class 3] | [X.XX] | [X.XX] | [X.XX] | [count] |
| [Class 4] | [X.XX] | [X.XX] | [X.XX] | [count] |
| [Class 5] | [X.XX] | [X.XX] | [X.XX] | [count] |

**Comparison to Previous Models:**
- [How does it compare?]

**Observations:**
- [Insights]

**Visualizations Created:**
- Confusion matrix: `reports/figures/model_results/xgb_confusion_matrix.png`
- Feature importance: `reports/figures/model_results/xgb_feature_importance.png`
- [Other visualizations]

---

### [Add more models as needed - copy template above]

---

## Handling Class Imbalance

**Problem:** [Describe the imbalance issue from your data]

**Approaches Tested:**

### Approach 1: [e.g., Class Weights]
- **Method:** Adjusted class weights in model to penalize minority class errors more
- **Implementation:** `class_weight='balanced'` in [model name]
- **Result:** [Did it improve minority class performance? By how much?]
- **Used in Final Model?** Yes/No

### Approach 2: [e.g., SMOTE - Synthetic Minority Over-sampling]
- **Method:** Generated synthetic samples for minority classes
- **Implementation:** `SMOTE(sampling_strategy='auto')` from imblearn
- **Result:** [Impact on performance?]
- **Used in Final Model?** Yes/No

### Approach 3: [e.g., Undersampling Majority Class]
- **Method:** [Description]
- **Implementation:** [Code/library used]
- **Result:** [Impact]
- **Used in Final Model?** Yes/No

**Final Decision:** [Which approach(es) you used and why]

---

## Hyperparameter Tuning

### Model: [Model Name]

**Tuning Method:** [e.g., GridSearchCV, RandomizedSearchCV, manual tuning]

**Parameters Tested:**
```python
param_grid = {
    'param1': [value1, value2, value3],
    'param2': [value1, value2, value3],
    'param3': [value1, value2]
}
```

## Cross-Validation: <br>
Method: [e.g., 5-fold cross-validation, stratified k-fold] <br>
Scoring Metric: [e.g., f1_weighted, accuracy] <br>
Best Parameters Found:
param1: [best_value]
param2: [best_value]
param3: [best_value] <br>
**Performance Improvement:** <br>
Before tuning: [metric] = [score]<br>
After tuning: [metric] = [score]<br>
Improvement: [+X.XX]<br>
Training Time:
Tuning process: [X] hours/minutes
Final model training: [X] seconds/minutes
---
## Feature Importance Analysis
Model Used: [Which model - e.g., Random Forest, XGBoost]<br>
**Top 10 Most Important Features:**<br>
[Feature name] - Importance: [X.XXX] - [Why this matters for business]
[Feature name] - Importance: [X.XXX] - [Why this matters]
[Feature name] - Importance: [X.XXX] - [Why this matters]
[Feature name] - Importance: [X.XXX] - [Why this matters]
[Feature name] - Importance: [X.XXX] - [Why this matters]
[Feature name] - Importance: [X.XXX] - [Why this matters]
[Feature name] - Importance: [X.XXX] - [Why this matters]
[Feature name] - Importance: [X.XXX] - [Why this matters]
[Feature name] - Importance: [X.XXX] - [Why this matters]
[Feature name] - Importance: [X.XXX] - [Why this matters]<br>
**Key Insights:**<br>
[What do these features tell us about incident classification?]
[Any surprises?]
[Business implications?]<br>
**Visualization:**
Feature importance plot: reports/figures/model_results/feature_importance_final.png
---
## Error Analysis
### Confusion Matrix Insights
**Most Common Misclassifications:**
[Class A] confused with [Class B]: [X] cases ([percentage]%)<br>
Possible reason: [Why might these be confused?]
[Class C] confused with [Class D]: [X] cases ([percentage]%)
Possible reason: [Why?]
[List other notable confusions]<br>
Classes with Best Performance:
[Class name]: [X.XX]% accuracy - [Why does model do well here?]<br>
Classes with Worst Performance:
[Class name]: [X.XX]% accuracy - [Why does model struggle here?]
### Error Patterns
**Time-Related Patterns in Errors:**
[Do errors happen more at certain times?]
[Any route-specific error patterns?]<br>
**Potential Causes:**
[Overlapping characteristics between classes?]
[Insufficient features to distinguish?]
[Data quality issues?]
[Class imbalance effects?]
---
## Model Comparison Summary
### Model
Accuracy
Precision
Recall
F1-Score
Training Time
Notes
[Model 1]
[X.XX]
[X.XX]
[X.XX]
[X.XX]
[X]s
Baseline
[Model 2]
[X.XX]
[X.XX]
[X.XX]
[X.XX]
[X]s
[Key note]
[Model 3]
[X.XX]
[X.XX]
[X.XX]
[X.XX]
[X]s
[Key note]
[Model 4]
[X.XX]
[X.XX]
[X.XX]
[X.XX]
[X]s

---
## Final Model Selection
Selected Model: [Model name and configuration]<br>
Rationale:
[Why this model over others?]
[Balance of performance vs. complexity?]
[Training/inference time considerations?]
[Interpretability needs?]
Final Performance:
Test Set Accuracy: [X.XX]%
Test Set F1-Score: [X.XX]
Test Set Precision: [X.XX]
Test Set Recall: [X.XX]
Model File:
Saved as: models/[filename].pkl
File size: [X] MB
Trained on: [Date]
---
## Business Impact
### Operational Improvements
**Baseline vs. Final Model:**
Improvement in accuracy: [X]%
Improvement in F1-score: [X]%
[What this means in practical terms]<br>
Expected Benefits:
Resource Allocation: [How model helps deploy resources]
Response Time: [How model helps reduce response time]
Preventive Maintenance: [How feature importance guides maintenance]
Cost Savings: [Estimated impact on operations]<br>
High-Value Insights:
[Key finding 1 and business implication]
[Key finding 2 and business implication]
[Key finding 3 and business implication]
---

## Limitations
**Model Limitations:**
[Limitation 1 - e.g., struggles with rare incident types]
[Limitation 2 - e.g., cannot predict novel incident types]
[Limitation 3 - e.g., performance degrades for certain routes]
**Data Limitations:**
[Data issue 1 - e.g., missing weather data]
[Data issue 2 - e.g., incomplete location information]
[Data issue 3]
**Assumptions Made:**
[Assumption 1]
[Assumption 2]
[Assumption 3]
---
## Future Improvements
With More Time, I Would:
Additional Models:
[Model type] - [Why it might help]
[Model type] - [Why it might help]
Feature Engineering:
[New feature idea] - [Why valuable]
[New feature idea] - [Why valuable]
Data Collection:
[Additional data needed] - [How it would improve model]
[Additional data needed] - [How it would improve model]
Ensemble Methods:
[Ensemble approach] - [Expected benefit]
Deep Learning:
[If applicable - neural network approach]
Real-time Deployment:
[Considerations for production deployment]
---
## Technical Challenges & Solutions
Challenge 1: [Describe problem]
Problem: [Detailed description]
Solution: [How you solved it]
Outcome: [Result]
Challenge 2: [Describe problem]
Problem: [Detailed description]
Solution: [How you solved it]
Outcome: [Result]
Challenge 3: [Describe problem]
Problem: [Detailed description]
Solution: [How you solved it]
Outcome: [Result]
