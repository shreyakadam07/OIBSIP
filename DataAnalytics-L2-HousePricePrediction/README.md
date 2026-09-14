House Price Prediction using Linear Regression

Track: Data Analytics (Level 2) Internship: Oasis Infobyte SIP Author: Shreya Kadam

📌 Objective

Build and evaluate a Linear Regression model that predicts house prices based on features such as number of rooms, neighborhood socioeconomic status, and pupil-teacher ratio.

🧰 Tech Stack
- Python
- pandas, numpy
- scikit-learn (LinearRegression, train_test_split, metrics)
- matplotlib, seaborn
- Jupyter Notebook
  
📂 Dataset

Housing Dataset (Boston Housing — reduced feature set), 489 rows

Column	Description <br>
RM	Average number of rooms per dwelling <br>
LSTAT	% of lower-status population in the area <br>
PTRATIO	Pupil-teacher ratio by town <br>
MEDV	Median house value (target variable)

No missing values or categorical features were present in this dataset.

🔍 Approach
EDA — checked nulls, viewed distribution of target variable (MEDV), and plotted a correlation heatmap. <br>
Feature Selection — used RM, LSTAT, and PTRATIO as predictors based on their correlation with price. <br>
Train/Test Split — 80/20 split using train_test_split. <br>
Model Training — trained a LinearRegression model on the training set. <br>
Evaluation — measured performance using MSE, RMSE, MAE, and R² Score. <br>
Residual Analysis — plotted residuals to check for systematic prediction errors. <br>
Coefficient Analysis — examined each feature's impact on predicted price. 

📊 Results
- Metric	Value
- MSE	6,789,025,559.27
- RMSE	82,395.54
- MAE	64,277.29
- R² Score	0.691

The model explains about 69.1% of the variance in house prices — a reasonably solid fit for a linear model using only 3 features, though it leaves room for improvement (e.g., with more features or a non-linear model).

📈 Coefficient Analysis
- Feature	Coefficient
- RM	+87,322.20
- LSTAT	−10,620.64
- PTRATIO	−19,324.41
  
💡 Key Insight

RM (number of rooms) had by far the strongest impact on price, with each additional room associated with an ~₹87,322 increase in predicted value. Both LSTAT (% lower-status population) and PTRATIO (pupil-teacher ratio) were negatively correlated with price, with PTRATIO having a notably larger negative effect than LSTAT — suggesting neighborhood school quality/funding may weigh more heavily on buyer valuation than socioeconomic composition alone in this dataset.

📁 Files in This Folder <br>

Housing.ipynb — full analysis notebook <br>
README.md — this file <br>
housing.csv — dataset 
