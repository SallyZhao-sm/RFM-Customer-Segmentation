# RFM Customer Segmentation

## Overview

This project analyzes online retail transaction data to identify distinct customer groups and translate purchasing behavior into practical marketing actions. Recency, Frequency, and Monetary (RFM) features were created at the customer level, followed by a comparison of K-Means and hierarchical clustering.

## Data

The analysis uses an online retail dataset containing transactions across 37 countries.

- 541,909 original transaction records
- 392,692 records retained after cleaning
- 4,338 customers
- 18,532 invoices
- 3,665 products
- £8.89 million in total revenue

## Data Preparation

The preparation process included:

- Removing cancelled orders, missing customer IDs, invalid quantities, and non-positive prices
- Converting transaction dates and calculating line-level revenue
- Aggregating transactions by customer
- Creating Recency, Frequency, and Monetary features
- Applying log transformation and standardization before clustering

## Methodology

Two clustering approaches were evaluated:

1. **K-Means clustering**
2. **Hierarchical clustering**

The number of clusters was selected using cluster validation metrics and business interpretability. K-Means was also tested across different initialization methods and iteration limits.

## Key Results

A five-cluster K-Means solution produced the strongest overall performance:

- Silhouette score: **0.617**
- Davies-Bouldin index: **0.716**
- Hierarchical clustering silhouette score: **0.609**
- Hierarchical clustering Davies-Bouldin index: **0.742**

The final K-Means model used:

- Number of clusters: 5
- Initialization: k-means++
- Maximum iterations: 100
- Number of initializations: 10
- Random state: 42

## Customer Segments

| Segment | Customers | Average Recency | Average Frequency | Average Monetary Value |
|---|---:|---:|---:|---:|
| Balanced Customers | 3,048 | 43.9 days | 3.7 purchases | £1,333 |
| Lost Customers | 1,063 | 248.5 days | 1.6 purchases | £479 |
| VIP Whales | 8 | 6.5 days | 120.5 purchases | £55,099 |
| Loyal Big Spenders | 213 | 15.7 days | 21.3 purchases | £12,814 |
| Top-Tier Champions | 6 | 7.7 days | 42.8 purchases | £190,809 |

## Business Recommendations

- Offer product bundles and loyalty incentives to balanced customers
- Use targeted discounts and reactivation campaigns for lost customers
- Assign personalized account support to high-value VIP customers
- Provide exclusive loyalty rewards to frequent big spenders
- Develop invitation-only shopping experiences for top-tier champions

## Technologies

- Python
- PySpark
- pandas
- scikit-learn
- SciPy
- Matplotlib
- Seaborn

## Repository Contents

- `rfm_customer_segmentation.ipynb`: data preparation, exploratory analysis, clustering, evaluation, and segment profiling
- `customer_segmentation_report.pdf`: full project report
