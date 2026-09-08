# RFM Customer Segmentation

## Overview

This project uses RFM analysis and clustering to identify customer groups and support targeted marketing and retention strategies.

## Data

The analysis uses the UCI Online Retail dataset:

- 541,909 transaction records
- 392,692 records retained after cleaning
- 4,338 customers
- 3,665 products
- 18,532 invoices
- 37 countries
- £8.89 million in revenue

## Data Preparation

- Converted invoice dates and created transaction-level revenue
- Removed cancellations, duplicate records, missing customer IDs, and non-positive quantities or prices
- Engineered Recency, Frequency, and Monetary features for each customer
- Standardized the RFM features before clustering

## Methodology

K-Means and hierarchical clustering were compared using silhouette and Davies–Bouldin scores. K-Means hyperparameters were also tested across initialization methods and iteration limits.

The final model used:

- 5 clusters
- K-Means++ initialization
- 10 initializations
- 100 maximum iterations
- Random state of 42

## Key Results

| Model | Silhouette Score | Davies–Bouldin Index |
|---|---:|---:|
| K-Means | 0.617 | 0.716 |
| Hierarchical clustering | 0.609 | 0.742 |

K-Means produced the stronger separation, identifying five customer segments:

| Segment | Customers | Average Recency | Average Frequency | Average Spend |
|---|---:|---:|---:|---:|
| Balanced Customers | 3,048 | 43.9 days | 3.7 purchases | £1,333 |
| Lost Customers | 1,063 | 248.5 days | 1.6 purchases | £479 |
| VIP Whales | 8 | 6.5 days | 120.5 purchases | £55,099 |
| Loyal Big Spenders | 213 | 15.7 days | 21.3 purchases | £12,814 |
| Top-Tier Champions | 6 | 7.7 days | 42.8 purchases | £190,809 |

## Business Recommendations

- Offer product bundles and loyalty incentives to balanced customers
- Use reactivation discounts for customers who have not purchased recently
- Assign personal account support to high-value customers
- Develop loyalty rewards for frequent, high-spending customers
- Offer exclusive shopping events to top-tier customers

## Technologies

Python, Pandas, NumPy, Scikit-learn, SciPy, Matplotlib, Seaborn

## Repository Contents

- `rfm_customer_segmentation.ipynb`: data cleaning, exploratory analysis, RFM feature engineering, model comparison, customer segmentation, and visualizations
