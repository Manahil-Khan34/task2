Project 2 Exploratory Data Analysis (EDA)

DecodeLabs Industrial Training Kit | Batch 2026

Overview

This project is the discovery phase of the DecodeLabs Data Analytics track. Building on the cleaned dataset from Project 1, the goal is to interrogate the data to uncover hidden patterns, trends, and outliers, transforming a static table of numbers into meaningful, actionable insight.

Completing this project unlocks Project 3 next week.

Objective

Analyze the cleaned e-commerce orders dataset to:


Calculate basic statistics (mean, median, count, five-number summary)
Identify trends and outliers
Summarize key observations as business-relevant insight


Dataset

File: Dataset_for_Data_Analytics.xlsx (same dataset cleaned in Project 1)
Rows: 1,200
Numeric columns analyzed: Quantity, UnitPrice, TotalPrice, ItemsInCart

Methodology

1. Descriptive Statistics

Calculated mean, median, standard deviation, and the full five-number summary (min, Q1, median, Q3, max) for all numeric columns.

2. Outlier Detection (IQR Method)

Applied the 1.5×IQR rule to flag outliers. 8 high-value orders were identified in TotalPrice, all with Quantity = 5 and UnitPrice above $665 interpreted as genuine bulk/premium purchases (signal) rather than data errors (noise).

3. Categorical Distribution Analysis

Examined the spread of Product, PaymentMethod, OrderStatus, ReferralSource, and CouponCode to understand category-level patterns.

4. Time-Based Trend Analysis

Grouped revenue by year and month to detect directional trends in order volume and value.

5. Correlation Analysis

Calculated Pearson correlation coefficients between all numeric variables to identify which factors most strongly drive TotalPrice.

6. Segment Performance

Broke down revenue and average order value by Product, OrderStatus, PaymentMethod, and CouponCode to translate statistics into business-relevant findings.

Key Findings

#FindingDetail1Revenue is right-skewedMean ($1,053.97) > Median ($823.62) — use median for "typical" order value28 high-value outliers detectedAll Quantity=5, UnitPrice > $665 legitimate bulk purchases, not errors3Quantity & UnitPrice uncorrelatedr = 0.015 independent purchase decisions4Categories are evenly distributedUnusual for real-world e-commerce data; worth noting541.4% of orders cancelled/returnedThe single most actionable finding investigate fulfillment6Revenue appears to decline by year2023→2025, but 2025 data may be incomplete7Credit Card has highest avg order value$1,128 vs $1,002 for Debit Card — modest pattern

Tools Used


Python 3 with Pandas, NumPy for analysis
Matplotlib and Seaborn for visualization
ReportLab for PDF report generation


Files in This Submission

File Description: task2.ipynb script containing all EDA logic and chart generation. Project2_EDA_Report.pdf Full report with findings, statistics tables, and embedded chartscharts/Folder containing all 6 generated chart images (PNG). README.md: This file

How to Run


Place task2.ipynb in the same folder as Dataset_for_Data_Analytics.xlsx
Install dependencies: pip install pandas numpy matplotlib seaborn openpyxl
Run the script: python task2.ipynb
Output: console prints the full statistical analysis; 6 charts are saved to a new charts/ folder and (since plt.show() is included) pop up on screen as they're generated


Key Takeaway

EDA is the diagnostic phase that comes before any dashboard or predictive model. As this analysis shows, the most valuable insight wasn't a fancy chart — it was a simple percentage (41.4% cancelled/returned) that points directly to a business problem worth solving.
