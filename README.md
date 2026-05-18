# Fifth_Project_Devlab

# 🛒 End-to-End KPI Framework for E-Commerce Operations

A data analysis project that builds a four-KPI performance framework on the **Olist Brazilian E-Commerce** public dataset (2016–2018). It merges five relational tables, computes business-critical KPIs, profiles sellers and product categories, and surfaces actionable operational insights.

---

## 📊 Key Results

| KPI | Value |
|---|---|
| Total Revenue | ~13.6 M BRL |
| Average Order Value (AOV) | ~140.7 BRL |
| Avg Delivery Time | ~12.1 days |
| Avg Review Score | ~4.09 / 5 |
| Delivery–Review Correlation | r ≈ −0.43 |
| Top-10 seller revenue share | ~12.7% |

---

## 📁 Dataset

**Source:** [Olist Brazilian E-Commerce Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) (Kaggle)

Five CSV files are required, placed in an `olist_data/` directory:

| File | Key Columns |
|---|---|
| `olist_orders_dataset.csv` | order_id, order_status, timestamps |
| `olist_order_items_dataset.csv` | order_id, product_id, seller_id, price |
| `olist_products_dataset.csv` | product_id, product_category_name |
| `olist_order_reviews_dataset.csv` | order_id, review_score |
| `product_category_name_translation.csv` | category PT → EN |

---

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- Jupyter Notebook 

### Data Setup

1. Download the dataset from [Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce).
2. Place all five CSV files inside an `olist_data/` folder at the project root.
3. If your data lives elsewhere, update the `DATA_DIR` variable in Cell 1 of the notebook.


## 🗂️ Notebook Structure

| Section | Description |
|---|---|
| **1 · Load Raw Tables** | Reads all five CSVs with correct dtypes and date parsing |
| **2 · Multi-Table Merge** | Step-by-step join pipeline; derives delivery time, delay, revenue, and order month |
| **3 · Core KPIs** | Overall totals: revenue, AOV, avg delivery, avg review score |
| **4 · KPIs by Category** | Per-category breakdown with top/bottom 5 rankings |
| **5 · Monthly KPI Summary** | Time-series view of all four KPIs |
| **6 · Seller Performance** | Revenue share, order volume, and review quality per seller |
| **7 · Correlation Analysis** | Pearson r between delivery time, delivery delay, and review score |
| **8 · Flag Problematic Categories** | Identifies categories above avg delivery AND below avg review |
| **9 · Visualizations** | Six publication-ready charts (saved as PNG) |
| **10 · Operational Insights** | Five prioritised business recommendations |

---

## 📈 Charts Produced

| File | Description |
|---|---|
| `fig1_monthly_revenue.png` | Revenue trend line, 2016–2018 |
| `fig2_category_revenue.png` | Top 5 vs Bottom 5 categories by revenue |
| `fig3_review_vs_delivery.png` | Bubble chart: review score vs delivery time per category |
| `fig4_seller_performance.png` | Seller revenue distribution + volume vs review score |
| `fig5_monthly_kpi_dashboard.png` | 2×2 dashboard: revenue, AOV, review, delivery over time |
| `fig6_category_kpi_heatmap.png` | Normalised KPI heatmap for top 20 categories |

---

## 💡 Key Insights

1. **Delivery delay drives poor reviews (r ≈ −0.43).** Reducing avg delivery time from 12 to 9 days could push the review score above 4.3. Focus on last-mile logistics in high-delay regions.

2. **Revenue is concentrated.** The top 10 sellers hold ~12.7% of GMV. A tiered seller programme (Gold/Silver/Bronze) with fulfilment coaching can lift mid-tier performance.

3. **Flagged categories need dedicated SLAs.** Categories with above-average delivery time *and* below-average review score are eroding satisfaction. Category-specific SLAs visible in seller dashboards can address this.

4. **AOV variance signals cross-sell opportunities.** High-revenue categories with below-average AOV (e.g. housewares, toys) operate in small baskets. Bundling and free-shipping thresholds could lift AOV by 15–20%.

5. **Q4 seasonality requires early preparation.** Revenue spikes sharply in Q4. Pre-positioning inventory before October and negotiating carrier capacity leads to ~30% lower delivery delays during peak.

---

## 🛠️ Tech Stack

- **pandas** — data loading, merging, and aggregation
- **NumPy** — numerical operations
- **Matplotlib** — all charts and the KPI dashboard
- **Seaborn** — themed styling and the category heatmap

---
