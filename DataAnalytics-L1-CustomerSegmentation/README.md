Customer Segmentation Analysis

Track: Data Analytics (Level 1) Internship: Oasis Infobyte SIP Author:Shreya Kadam

📌 Objective

Apply clustering algorithms to segment an e-commerce company's customer base into distinct groups based on purchasing behaviour, enabling targeted marketing strategies.

🧰 Tech Stack
Python
pandas
scikit-learn (KMeans, StandardScaler)
matplotlib / seaborn
Jupyter Notebook
📂 Dataset

Online Retail Dataset:
Transactional data from a UK-based online retailer, covering invoices, products, quantities, prices, and customer IDs. Originally sourced from the UCI Machine Learning Repository, obtained via Kaggle.
Source: Source: [Kaggle — Online Retail Dataset]
(https://www.kaggle.com/datasets/ulrikthygepedersen/online-retail-dataset)

🔍 Approach
Data Cleaning — removed rows with missing CustomerID, cancelled orders (invoices starting with 'C'), and invalid (negative/zero) quantities or prices.
RFM Feature Engineering — calculated Recency (days since last purchase), Frequency (number of distinct orders), and Monetary (total amount spent) for each customer.
Feature Scaling — standardized RFM features using StandardScaler so K-Means isn't biased by scale differences.
Optimal K Selection — used the Elbow Method to determine the ideal number of clusters.
K-Means Clustering — segmented customers into distinct groups based on their RFM profile.
Cluster Profiling — calculated mean RFM values per cluster and interpreted each segment's behaviour.
📊 Key Visualizations
RFM distribution histograms
Elbow plot for optimal K
Recency vs Monetary and Frequency vs Monetary scatter plots (colored by cluster)
Customer count per cluster bar chart


💡 Insights & Marketing Recommendations
Cluster	Profile	Recommended Action
[e.g., Champions]	Low Recency, High Frequency, High Monetary	Loyalty rewards, early access, referral incentives
[e.g., At Risk]	High Recency, moderate past activity	Win-back email campaigns, personalized discounts
[e.g., New/Low-Value]	Low Frequency, Low Monetary	Onboarding offers, bundle deals to grow basket size
[e.g., Steady Regulars]	Moderate across all metrics	Upsell/cross-sell campaigns


📁 Files in This Folder
customer_segmentation_analysis.ipynb — full analysis notebook
README.md — this file
screenshots/ — exported chart images
