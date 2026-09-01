# Repeat Purchase Paradox: Finding High-Value Customers in Declining Revenue

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2C2D72?style=for-the-badge&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557c?style=for-the-badge)
![Data Analysis](https://img.shields.io/badge/Data_Analysis-RFM-008080?style=for-the-badge)

> **View the visual summary & business impact on my [Portfolio Website ↗]([MASUKKAN_LINK_WEBSITE_PORTOPOLIO_KAMU_DISINI])**

## 📌 Business Problem
An Australian e-commerce fashion business was experiencing a steady decline in monthly revenue throughout the second half of 2021. The management lacked visibility into their customer base, treating all customers equally. 

The core objective of this project was to segment the customer base to separate **highly valuable, loyal repeat buyers** from one-time shoppers, preventing retention budgets from being spread inefficiently across the wrong segments.

## 🗂️ Data Overview & Preparation
The raw data consisted of 993 orders from 616 unique customers across Jan–Oct 2021, scattered across 4 tables (`customers`, `orders`, `products`, `sales`).

**Data Cleaning & Feature Engineering:**
- Imputed missing gender values (labeled as "Prefer not to say").
- Reconstructed missing `total_price` values using `price_per_unit × quantity`.
- Corrected inaccurate age outliers and deduplicated rows.
- Engineered new features: `delivery_time`, `age_group` (Youth/Adults/Seniors), and customer `status` (Active/Non-Active).

## 🧠 Methodology (RFM Analysis)
To identify the most valuable segments, I applied **RFM Analysis**:
- **Recency:** How recently did the customer purchase?
- **Frequency:** How often do they purchase?
- **Monetary:** How much do they spend?

## 📊 Key Insights

### 1. Repeat Buyers are the Revenue Engine
While 58.1% of customers only transacted once, **repeat buyers generated 63.3% of total revenue**. The top-tier loyal segment (frequency ≥ 4) made up only 3.1% of the customer base but contributed an oversized 8.4% of total revenue. 
*(Retention is far more cost-efficient than pure acquisition).*

### 2. Revenue Trend & The Danger of Averages
Monthly revenue peaked in March (Rp 131,364) and steadily weakened to its lowest point in October (Rp 84,266). Without a targeted retention mechanism, early-year acquisition momentum naturally deflates.

![Monthly Revenue Trend]([MASUKKAN_LINK_GAMBAR_VIZ_1_DARI_GITHUB_DISINI])
*(Example: `images/viz_1.png`)*

### 3. Product Performance: Denim Dominates
Denim sold 527 units—nearly double the second-best product (Joggers, 334 units). Conversely, Mandarin Collar and Dress lines underperformed, signaling a need for strategic inventory evaluation.

![Top Products]([MASUKKAN_LINK_GAMBAR_VIZ_2_DARI_GITHUB_DISINI])
*(Example: `images/viz_2.png`)*

## 💡 Business Recommendations
1. **Targeted Retention:** Shift marketing budgets (email re-engagement, loyalty points) toward top-RFM customers rather than spreading it evenly.
2. **Inventory Optimization:** Strengthen stock availability and cross-promotions around Denim, while reducing spend on Mandarin Collar.
3. **Data Quality Fix:** 75% of users opted out of providing gender data. The business should avoid making gender-based marketing decisions until data collection methods improve.

## 📂 Repository Structure
```text
├── data/
│   ├── raw/                 # Original 4 tables (customers, orders, etc.)
│   └── processed/           # Cleaned and merged master dataset
├── images/                  # Charts and graphs used in this README
├── notebooks/
│   └── 01_EDA_and_RFM.ipynb # Main analysis notebook
├── requirements.txt         # Project dependencies
└── README.md                # Project documentation
