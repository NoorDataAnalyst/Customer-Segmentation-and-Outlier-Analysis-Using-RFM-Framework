# RFM-Based Customer Segmentation with Outlier Analysis and Interpretation

## Overview

This project performs customer segmentation using the classic RFM (Recency, Frequency, Monetary) analysis technique, enhanced with a thorough outlier detection and interpretation process. It also includes comprehensive data cleaning to ensure data quality before analysis.

The goal is to identify distinct customer segments, understand their purchasing behaviors, and analyze outlier customers separately to gain deeper business insights.

The analysis is done on a transactional dataset containing customer purchase history and includes:

- Data cleaning to handle missing, duplicate, or inconsistent records.
- Calculation of RFM scores and segments for non-outlier customers.
- Identification and segmentation of outlier customers based on monetary and frequency values.
- Visualization of RFM distributions using violin plots, heatmaps, and bar charts.
- Combination of non-outlier and outlier segments with distinct naming conventions.
- Interpretation of customer segments with actionable labels.
### Link to dataset: https://archive.ics.uci.edu/dataset/502/online+retail+ii

## Dataset

The analysis is based on the **Online Retail II dataset**, which contains transactional data from a UK-based online retail store between 2010–2011. The original dataset includes the following key columns:

- `InvoiceNo`: Invoice number. A 6-digit unique number for each transaction. If it starts with 'C', it indicates a cancellation.  
- `StockCode`: Product (item) code. A 5-digit unique number assigned to each product.  
- `Description`: Product name.  
- `Quantity`: Number of units of each product per transaction.  
- `InvoiceDate`: Invoice date and time of the transaction.  
- `UnitPrice`: Price per unit in sterling (£).  
- `CustomerID`: Customer number. A 5-digit unique number assigned to each customer.  
- `Country`: Customer's country of residence.

### Processed Dataset for Analysis

For the RFM analysis, the original dataset was cleaned and aggregated to create a new DataFrame (`aggregated_df`) with the following calculated variables:

- `MonetaryValue`: Total spend per customer.  
- `Frequency`: Total number of transactions per customer.  
- `Recency`: Number of days since the last purchase.  
- `R_Score`, `F_Score`, `M_Score`: RFM scores (1–5) for Recency, Frequency, and MonetaryValue.  
- `RFM_Score`: Combined RFM score (sum of R, F, M).  
- `Segment`: Customer segment assigned based on RFM scores.  
- Outlier flags and segments were also added to handle extreme customers separately.


## Data Cleaning

- Removed duplicates.
- Handled missing values appropriately.
- Corrected data types for date and numeric columns.
- Ensured consistency in customer identifiers.


## Methodology

1. **Outlier Detection**  
   - Monetary and Frequency outliers detected using the Interquartile Range (IQR) method.
   - Outliers segmented separately with meaningful labels distinct from non-outliers.

2. **RFM Scoring and Segmentation**  
   - Non-outlier customers scored on R, F, and M dimensions.
   - Segments like `At-Risk`, `New`, `Loyal`, `VIP`, etc., are assigned based on score thresholds.

3. **Outlier Segmentation**  
   - Outliers grouped into clusters such as `High Monetary`, `High Frequency`, or `Both`.
   - Separate segment names like `PAMPER`, `UPSELL`, and `DELIGHT` assigned for clarity.

4. **Visualization**  
   - Violin plots to visualize the distribution of R, F, and M across segments.
   - Heatmaps showing average RFM values per segment.
   - Bar charts displaying customer counts per segment.
   - Combined visualizations to compare non-outlier and outlier groups.

## Results and Interpretation
<img width="1201" height="681" alt="image" src="https://github.com/user-attachments/assets/35ecf9fc-1d83-4440-8ffd-90368f8b9421" />

- Clear differentiation of customer segments based on recency, frequency, and monetary value.
- Identification of outlier customers representing either extremely valuable or infrequent shoppers.
- Meaningful segment labels help marketing and sales teams tailor communication strategies.
- Visual aids support understanding and validation of segmentation quality.

## Usage

- Load the dataset into a Pandas DataFrame.
- Perform data cleaning steps.
- Run the provided code for scoring, segmentation, and outlier detection.
- Use the visualization cells to explore customer behavior.
- Modify thresholds or segment definitions as per business requirements.

## Requirements

- Python 3.x
- pandas
- matplotlib
- seaborn

Install dependencies via:

```bash
pip install pandas matplotlib seaborn
