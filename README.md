# 🛒 Unsupervised Learning Project
## Customer Segmentation Using Clustering

![Python](https://img.shields.io/badge/Python-3.10-blue)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.3.0-orange)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-green)
![License](https://img.shields.io/badge/License-MIT-yellow)
![Pandas](https://img.shields.io/badge/Pandas-2.0.3-150458)
![NumPy](https://img.shields.io/badge/NumPy-1.24.3-013243)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.7.2-11557C)
![Seaborn](https://img.shields.io/badge/Seaborn-0.12.2-4EAA25)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![PRs](https://img.shields.io/badge/PRs-Welcome-brightgreen)
![Made with ❤️](https://img.shields.io/badge/Made%20with-❤️-red)

---

## 📋 Table of Contents
- [Project Overview](#-project-overview)
- [Project Objectives](#-project-objectives)
- [Dataset Information](#-dataset-information)
- [Methods Used](#-methods-used)
- [Results](#-results)
- [Key Findings](#-key-findings)
- [Visualizations](#-visualizations)
- [Limitations](#-limitations)
- [Future Improvements](#-future-improvements)
- [Repository Structure](#-repository-structure)
- [How to Run](#-how-to-run)
- [Requirements](#-requirements)
- [Connect](#-connect-with-me)
- [License](#-license)

---

## 📋 Project Overview

This project applies **Unsupervised Learning** techniques to segment customers based on their purchasing behavior and demographics using the **Mall Customers Dataset**.

| Metric | Value |
|--------|-------|
| **Best Model** | Hierarchical Clustering (Ward Linkage) |
| **Silhouette Score** | 0.3424 |
| **Clusters Found** | 2 distinct customer segments |
| **Dataset Size** | 200 customers |
| **Features Used** | Age, Income, Spending Score |
| **Total Models Tested** | 9 variations (3 methods × 3 variations) |

---

## 🎯 Project Objectives

1. ✅ Identify distinct customer groups for targeted marketing
2. ✅ Understand spending patterns across different segments
3. ✅ Develop personalized strategies for each customer group
4. ✅ Improve customer retention and increase sales

### Business Impact

Customer segmentation allows businesses to:
- 📧 Send personalized offers to each segment
- 💰 Optimize marketing spend by targeting the right customers
- 😊 Improve customer satisfaction through relevant communications
- 📈 Increase customer lifetime value through better engagement

---

## 📊 Dataset Information

### Dataset Overview

| Property | Value |
|----------|-------|
| **Dataset** | Mall Customers Dataset |
| **Source** | Generated synthetic data based on real patterns |
| **Samples** | 200 customers |
| **Features** | 5 columns |
| **Missing Values** | None (0%) |
| **Data Quality** | ✅ Good |

### Feature Descriptions

| Feature | Description | Type | Range |
|---------|-------------|------|-------|
| CustomerID | Unique customer identifier | Integer | 1-200 |
| Gender | Male/Female | Categorical | - |
| Age | Customer age in years | Integer | 18-70 |
| Annual Income (k$) | Yearly income in thousands | Integer | 15-140 |
| Spending Score | Spending behavior score | Integer | 1-100 |

### Features Used for Clustering

| Feature | Category | Why Used |
|---------|----------|----------|
| Age | Demographic | Represents customer life stage |
| Annual Income | Economic | Represents purchasing power |
| Spending Score | Behavioral | Represents engagement level |

### Data Quality Assessment

| Attribute | Quality | Assessment |
|-----------|---------|------------|
| Completeness | ✅ Good | No missing values |
| Consistency | ✅ Good | All values within expected ranges |
| Accuracy | ✅ Good | Synthetic but realistic patterns |
| Relevance | ✅ Good | Features relevant to segmentation |
| Timeliness | ✅ Good | Current customer data (2026) |

---

## 🤖 Methods Used

### 1. K-Means Clustering
- **How it works:** Partitions data into K clusters based on centroids
- **Strengths:** Simple, fast, interpretable
- **Weaknesses:** Requires specifying K, sensitive to outliers
- **Variations Tested:** K=3, K=4, K=5

### 2. Hierarchical Clustering (Agglomerative)
- **How it works:** Builds a hierarchy of clusters (tree structure)
- **Strengths:** No need to specify K, dendrogram visualization
- **Weaknesses:** Computationally expensive for large datasets
- **Variations Tested:** Single linkage, Complete linkage, Ward linkage

### 3. DBSCAN (Density-Based Spatial Clustering)
- **How it works:** Groups points based on density
- **Strengths:** Finds arbitrary shapes, handles outliers
- **Weaknesses:** Sensitive to parameters
- **Variations Tested:** eps=0.3, eps=0.5, eps=0.7

### Model Variations Summary

| Method | Variation 1 | Variation 2 | Variation 3 |
|--------|-------------|-------------|-------------|
| K-Means | K=3 | K=4 | K=5 |
| Hierarchical | Single linkage | Complete linkage | Ward linkage |
| DBSCAN | eps=0.3 | eps=0.5 | eps=0.7 |

### Evaluation Metrics Used

| Metric | Range | Interpretation |
|--------|-------|----------------|
| **Silhouette Score** | -1 to 1 | Higher is better (cohesive clusters) |
| **Calinski-Harabasz** | 0 to ∞ | Higher is better (cluster separation) |
| **Davies-Bouldin** | 0 to ∞ | Lower is better (cluster similarity) |

---

## 📈 Results

### Model Comparison Table

| Model | Silhouette | Calinski-Harabasz | Davies-Bouldin | Clusters |
|-------|------------|-------------------|----------------|----------|
| **Hierarchical (ward)** | **0.3424** ✅ | **128.39** ✅ | 1.1776 | 2 |
| Hierarchical (complete) | 0.3206 | 120.05 | 1.2131 | 2 |
| K-Means (K=4) | 0.3184 | 113.43 | 1.0802 | 4 |
| K-Means (K=3) | 0.3090 | 116.17 | 1.1070 | 3 |
| K-Means (K=5) | 0.3012 | 105.42 | 1.0780 | 5 |
| Hierarchical (single) | 0.2983 | 3.27 | 0.5189 | 2 |
| DBSCAN (eps=0.7) | -0.0578 | 2.04 | 6.5495 | 2 |
| DBSCAN (eps=0.5) | 0.0000 | 0.00 | 0.0000 | 1 |
| DBSCAN (eps=0.3) | 0.0000 | 0.00 | 0.0000 | 0 |

### 🏆 Best Model: Hierarchical Clustering (Ward Linkage)

**Why Ward Linkage Was Selected:**

| Reason | Explanation |
|--------|-------------|
| ✅ Highest Silhouette | 0.3424 - Best cluster cohesion |
| ✅ Highest Calinski-Harabasz | 128.39 - Best cluster separation |
| ✅ No Need to Specify K | Automatically determines clusters |
| ✅ Most Interpretable | Dendrogram visualization |
| ✅ Compact Clusters | Ward minimizes within-cluster variance |
| ✅ Robust Performance | Less sensitive to outliers |

### Comparison with Other Models

| Comparison | Result |
|------------|--------|
| **vs K-Means** | No need to specify K, more interpretable |
| **vs Complete Linkage** | Higher silhouette (0.3424 vs 0.3206) |
| **vs DBSCAN** | DBSCAN failed to find meaningful clusters |

---

## 🔍 Key Findings

### Two Distinct Customer Segments Identified

---

### Cluster 0: High-Value Premium Customers

| Metric | Value |
|--------|-------|
| **Size** | 94 customers (47% of total) |
| **Average Age** | 45.2 years |
| **Average Income** | $79,600 |
| **Average Spending** | 69.1/100 |

**Characteristics:**
- ✅ Mature customers with higher disposable income
- ✅ Active spenders who purchase premium products
- ✅ Likely to respond to exclusive offers
- ✅ Professionals or established career individuals

**Marketing Recommendations:**

| Strategy | Action |
|----------|--------|
| **Premium Products** | Offer luxury and premium products |
| **Exclusive Loyalty** | Create VIP programs with perks |
| **Personalized Experience** | Assign personal shoppers |
| **Cross-Selling** | Suggest complementary products |
| **Communication** | Send personalized emails and previews |

---

### Cluster 1: Low-Value Customers (Needs Attention)

| Metric | Value |
|--------|-------|
| **Size** | 106 customers (53% of total) |
| **Average Age** | 41.9 years |
| **Average Income** | $42,500 |
| **Average Spending** | 31.7/100 |

**Characteristics:**
- ✅ Lower income, limited spending capacity
- ✅ Price-sensitive customers
- ✅ Potentially young or budget-conscious
- ✅ Infrequent shopping behavior

**Marketing Recommendations:**

| Strategy | Action |
|----------|--------|
| **Discounts** | Offer targeted promotions |
| **Bundle Offers** | Create value bundles |
| **Engagement** | Re-engagement campaigns |
| **Loyalty Program** | Simple, easy-to-understand program |
| **Communication** | Social media and email campaigns |

---

## 📊 Visualizations

### Model Comparison - Silhouette Score
![Model Comparison](images/04_model_comparison.png)

### Income vs Spending by Cluster
![Income vs Spending](images/05_cluster_profiles.png)

### Cluster Profiles Summary
![Cluster Profiles](images/06_conclusion.png)

---

## ⚠️ Limitations

| Limitation | Impact | Severity | Mitigation |
|------------|--------|----------|------------|
| **Small Dataset** | May not represent all populations | High | Collect more data |
| **Synthetic Data** | Not real customer behavior | High | Use real data |
| **Limited Features** | Only 3 features used | Medium | Engineer more features |
| **No Temporal Data** | Static snapshot | Medium | Add time-series data |
| **No Validation** | Not tested with business | Medium | A/B testing |
| **Single Method** | Only clustering used | Low | Try ensemble methods |

---

## 🚀 Future Improvements

### Phase 1: Data Enhancement (1-2 months)

| Task | Deliverable |
|------|-------------|
| Collect real customer data | Enhanced dataset |
| Add purchase history (12 months) | Historical data |
| Include product preferences | Category data |
| Add customer service data | Interaction history |

### Phase 2: Feature Engineering (2-3 months)

| Task | Deliverable |
|------|-------------|
| Create RFM features | RFM scores |
| Calculate Customer Lifetime Value | CLV estimates |
| Add seasonal patterns | Seasonality analysis |
| Create engagement scores | Engagement metrics |

### Phase 3: Model Enhancement (3-4 months)

| Task | Deliverable |
|------|-------------|
| Test Spectral Clustering | Additional method |
| Implement Gaussian Mixture Models | Probabilistic clustering |
| Ensemble clustering approach | Combined model |
| Test OPTICS algorithm | Alternative to DBSCAN |

### Phase 4: Validation (4-6 months)

| Task | Deliverable |
|------|-------------|
| A/B testing on segments | Campaign response data |
| Measure campaign response | Performance metrics |
| Calculate ROI for each segment | ROI analysis |
| Refine segments based on results | Improved segments |

### Phase 5: Deployment (6-12 months)

| Task | Deliverable |
|------|-------------|
| Build automated pipeline | Production system |
| Create dashboards | Monitoring dashboard |
| Integrate with marketing systems | API integration |
| Real-time segmentation | Dynamic assignment |

### Success Metrics

| Metric | Target |
|--------|--------|
| Segment stability | 90%+ stability over time |
| Campaign response rate | 20%+ increase |
| Customer lifetime value | 15%+ increase |
| Retention rate | 10%+ improvement |
| Marketing ROI | 25%+ improvement |



