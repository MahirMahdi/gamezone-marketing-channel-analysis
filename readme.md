# Gamezone Marketing Channel Analysis

## 1. Business Context

Leadership wanted to understand which channels bring high value customers, not just high order volume.

However, the dataset doesn't include marketing spend or budget information, so measuring ROI is not possible.

That's why I focused on customer value and channel contribution proxy metrics to identify which channels have higher business impact.

---

## 2. Executive Summary

This analysis evaluated channel performance to determine which channels drive the highest customer value versus the greatest revenue scale. Due to the absence of marketing spend data, performance was assessed using proxy metrics including Average Revenue per Customer (ARPC), Repeat Customer Rate (RCR), Average Order Value (AOV), and channel share of total revenue and customers.

The results reveal a clear value–scale tradeoff:

**_`Affiliate`_** drives the strongest per-customer value, with the highest ARPC, AOV, and repeat purchase rate. However, it contributes less than 5% of total revenue due to limited customer acquisition volume.

**_ `Direct`_** accounts for approximately 80% of both customers and total revenue, making it the dominant revenue driver. However, its per-customer value metrics are lower than **_`Affiliate`_**.

**_`Email`_** demonstrates strong retention performance, indicating effective lifecycle marketing influence despite low order value and moderate revenue contribution.

Overall, **_`Affiliate`_** appears to attract higher-value customers but lacks scale, while Direct dominates revenue contribution but may reflect attribution or brand-driven traffic effects. So strategic decisions should balance customer quality with acquisition volume and validate attribution accuracy before reallocating investment.

## 3. Business Objective

### **Primary Question**

***We’re investing across a bunch of channels, but leadership keeps asking which ones are actually worth the money. Can you help us understand how different channels perform—not just in volume, but in quality?***

---

## 4. Dataset Overview

Each row represents a product-level transaction within an order. It includes:

**`CUSTOMER ID`**

**`ORDER ID`**

**`PURCHASE TS`**

**`SHIP TS`**

**`PRODUCT NAME`**

**`PRODUCT ID`**

**`PRICE`**

**`PURCHASE PLATFORM`**

**`MARKETING CHANNEL`**

**`ACCOUNT CREATION METHOD`**

**`COUNTRY`**

***Dataset size: ~22K Rows***

---

## 5. Analytical Approach

To measure customer value and channel business impact, I used the following proxy metrics:

### Customer Value Metrics

- Average Revenue per Customer (ARPC)

- Average Order Value (AOV)

- Repeat Customers Rate (RCR)

### Channel Contribution Metrics

- Share of Total Customers

- Share of Total Revenue

This approach helped to evaluate both:

- Customer quality

- Channel business impact

---

## 6. Data Preparation & Sanity Checks

Before analysis, I did sanity checks and data validation.

### Key Data Issues Identified

- **Duplicate Orders**

  37 duplicate order records detected

  Removed after verifying duplicate keys (order ID, timestamp, product, price)

- **Missing Channel Attribution**

  Blank and “unknown” marketing channels

  Standardized blanks → “unknown” for consistency

- **Potential tracking issues**

  Account Creation Method Gaps

  Missing values correlated with missing marketing channel data

  The tracking pipeline requires review.

- **Pricing Issues**

  Blank and zero price values found

- **Fulfillment Timeline Errors**

  ~10% of orders showed shipping dates before purchase dates. This may affect fulfillment performance analysis but does not impact revenue metrics.

---

## 7. Exploratory Analysis Highlights

**Exploratory trend analysis revealed a temporary decline in Direct and Email performance in early 2020, followed by sustained recovery later in the year. Affiliate and Social channels showed relatively stable acquisition patterns. Further cohort or attribution analysis would be required to validate underlying drivers.**

[View EDA](https://public.tableau.com/app/profile/muhtasim.mahdi/viz/GamezoneEDA/Sheet1)

<img width="1920" height="1040" alt="EDA" src="https://github.com/user-attachments/assets/80662c86-78ca-4933-b299-d83fc18025f3" />

***Further cohort or attribution analysis would be required to validate causality.***

---

## 8. Key Findings

1. **Affiliate Channel → Highest Customer Value**

- Highest average revenue per customer (~$340)

- Strong repeat purchase signal (~10.6%)

- Highest average order value (~$308)

**_Interpretation_**:
Affiliate appears to bring fewer but higher-value customers.

2. **Direct Channel → Dominant Revenue Contributor**

- ~80% of customers

- ~85% of total revenue

**_Interpretation_**:
Likely reflects brand loyalty, repeat purchasing, or attribution limitations rather than pure acquisition.

3. **Email Channel → Strong Retention**

- Strong repeat customer percentage (~8.7%)

- Moderate revenue contribution (~10%)

**_Interpretation_**:
Email demonstrates strong retention signals despite low order value and moderate revenue contribution.

[View Dashboard (Best Viewed in Full Screen)](https://public.tableau.com/app/profile/muhtasim.mahdi/viz/gamezone-marketing-channel-performance-dashboard/MarketingChannelPerformance)


<img width="1595" height="1045" alt="dashboard" src="https://github.com/user-attachments/assets/d8453aaa-d72f-4a5d-b96f-97d900b65e72" />


---

## 9. Recommendations

1. **Investigate Direct Channel Attribution (Priority 1)**

- Determine how many “Direct” users originated elsewhere

- Analyze cross-channel customer journeys

2. **Expand Affiliate Testing (Priority 2)**

- Increase controlled investment

- Monitor CLV impact

3. **Strengthen Email Lifecycle Marketing (Priority 3)**

- Retention campaigns

- Personalized re-engagement flows

- Repeat purchase optimization

---

## 10. Limitations

- ROI could not be evaluated due to the absence of marketing spend data

- Attribution inconsistencies may skew channel performance

Therefore, insights should be considered directional rather than causal.

---

## 11. Tools Used

- **_Excel / Power Query_**: Data cleaning, validation, & preparation

- **_Tableau_**: Exploratory analysis and dashboard visualization
