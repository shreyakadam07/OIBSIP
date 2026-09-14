Wine Quality Prediction

Track: Data Analytics (Level 2)<br> Internship: Oasis Infobyte SIP<br> Author: Shreya Kadam

📌 Objective

Train and compare multiple classification models to predict wine quality based on physicochemical properties such as acidity, density, and alcohol content.

🧰 Tech Stack
- Python
- pandas, numpy
- scikit-learn (RandomForestClassifier, SGDClassifier, SVC)
- matplotlib, seaborn
- Jupyter Notebook
  
📂 Dataset

Red Wine Quality Dataset (UCI / Kaggle) — 1,599 samples, 11 physicochemical features + quality score (3–8). No missing values.

Original quality score distribution (heavily imbalanced):

Score 3 — 10 samples <br>
Score 4 — 53 samples <br> 
Score 5 — 681 samples <br>
Score 6 — 638 samples <br>
Score 7 — 199 samples <br>
Score 8 — 18 samples 

🔍 Approach
EDA — checked nulls (none found), plotted quality score distribution, feature histograms, and a correlation heatmap. <br>
Class Imbalance Handling — binned the raw 3–8 quality scores into 3 more balanced categories: Low (3–4), Medium (5–6), High (7–8). <br>
Train/Test Split — 80/20 stratified split to preserve class proportions. <br>
Feature Scaling — applied StandardScaler (used for SGD and SVC; tree-based Random Forest doesn't require it). <br>
Model Training — trained and compared 3 classifiers: Random Forest, SGD, and SVC. <br>
Evaluation — accuracy, classification report, and confusion matrix for each model. <br>
Feature Importance — extracted from the Random Forest model.

📊 Class Distribution After Binning
- Medium — 1,319 samples
- High — 217 samples
- Low — 63 samples

The Low class remained quite small even after binning (only 63 samples total, 13 in the test set) — this shows up clearly in the results below.

📈 Model Comparison
- Random Forest — 86.6% accuracy (best performer)
- SVC — 84.4% accuracy
- SGD — 82.5% accuracy

Random Forest was the best-performing model, correctly classifying ~87% of wines in the test set.

- Per-Class Performance (Random Forest)
- High — Precision: 0.71 | Recall: 0.51 | F1-score: 0.59
- Low — Precision: 0.00 | Recall: 0.00 | F1-score: 0.00
- Medium — Precision: 0.88 | Recall: 0.97 | F1-score: 0.92

All three models struggled significantly with the Low class, scoring 0.00 across precision, recall, and F1 — a direct consequence of having only 13 test samples in that category. This is a class imbalance limitation rather than a modeling flaw; even after binning, "Low" quality wines remain rare in this dataset.

🌟 Feature Importance (Random Forest)

Top predictors of wine quality:

- Alcohol — 0.147
- Volatile Acidity — 0.130
- Sulphates — 0.104
- Density — 0.092
- Citric Acid — 0.085
  
💡 Conclusion

Random Forest achieved the highest accuracy at 86.6%, outperforming both SVC (84.4%) and SGD (82.5%), making it the most suitable model for deployment. This is expected — Random Forest handles non-linear relationships and feature interactions well, and doesn't require feature scaling like SGD and SVC do.

The most influential features were alcohol content, volatile acidity, and sulphates — indicating these chemical properties have the strongest relationship with perceived wine quality. Interestingly, alcohol content being the top predictor aligns with wine industry knowledge, where higher alcohol wines are often associated with better balance and perceived quality.

Limitation: All models failed to correctly identify any "Low" quality wines, due to severe class imbalance (only 63 out of 1,599 samples). A production model would benefit from techniques like SMOTE oversampling or collecting more low-quality wine samples to address this gap.

📁 Files in This Folder

wine_quality_prediction.ipynb — full analysis notebook <br>
README.md — this file <br>
winequality-red.csv — dataset 
