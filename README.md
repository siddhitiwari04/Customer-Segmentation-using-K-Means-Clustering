# 🛍️ Customer Segmentation using K-Means Clustering

A data science project that segments mall customers into distinct groups based on their **age, annual income, and spending score**, using unsupervised machine learning (K-Means clustering). The insights are further brought to life through an interactive **Power BI dashboard**.

---

## 📌 Overview

Understanding customers is at the heart of every good marketing strategy. Instead of treating every customer the same, this project groups them into meaningful segments so that a business can target each group with a tailored strategy — from luxury upselling to loyalty campaigns.

The project covers the full pipeline:

1. Exploratory Data Analysis (EDA)
2. Feature-wise customer distribution analysis
3. K-Means clustering (Elbow Method for optimal *k*)
4. Cluster visualization (2D & 3D)
5. An interactive Power BI dashboard summarizing the findings

---

## 🗂️ Dataset

**File:** `Mall_Customers.csv`

| Column                     | Description                                           |
| -------------------------- | ----------------------------------------------------- |
| `CustomerID`             | Unique ID for each customer                           |
| `Gender`                 | Male / Female                                         |
| `Age`                    | Customer's age                                        |
| `Annual Income (k$)`     | Annual income in thousand dollars                     |
| `Spending Score (1-100)` | Score assigned by the mall based on spending behavior |

200 customer records in total.

---

## 🧰 Tech Stack

- **Python** — pandas, numpy, matplotlib, seaborn, scikit-learn
- **Jupyter Notebook** — analysis & modeling (`Customer_Segmentation.ipynb`)
- **Power BI** — interactive dashboard (`.pbix`)

---

## 📁 Repository Structure

```
├── Mall_Customers.csv                          # Dataset
├── Customer_Segmentation.ipynb                 # EDA + K-Means clustering notebook
├── Customer Segmentation Dashboard.pbix         # Power BI dashboard file
├── Customer Segmentation Dashboard.pdf          # Exported dashboard snapshot
└── README.md
```

---

## 📊 Power BI Dashboard

📄 **[View the full dashboard (PDF)](./Customer%20Segmentation%20Dashboard%20%E2%80%93%20Siddhi%20Tiwari_1.pdf)**


The dashboard includes KPIs (avg. income, avg. spending, avg. age), a customer distribution breakdown by segment, and an interactive income-vs-spending scatter plot colored by segment.

## 🐍 Python Visualizations & Insights

**Yes — it's worth including the notebook's visualizations in the README.** The dashboard shows the polished, end-user view, but the notebook plots show *how* the clusters were arrived at (elbow curves, raw distributions, model diagnostics). Including both gives visitors the full story: the analysis process **and** the business-ready output. Below are the key plots pulled directly from the notebook, along with brief insights.

### 1. Distribution of Age, Income & Spending Score

**Insight:** Age is right-skewed, with most customers concentrated between the early 20s and late 30s. Annual income is fairly evenly spread across $15k–$140k, with a mild concentration around $60k–$80k. Spending Score is close to a uniform/bimodal spread, suggesting the mall serves a genuinely mixed base of low, medium, and high spenders rather than one dominant type.

### 2. Gender Split

**Insight:** The customer base is skewed slightly toward **female shoppers** (~56%) compared to male (~44%), useful context when designing gender-targeted campaigns.

### 3. Age, Income & Spending by Gender (Violin Plots)

**Insight:** Age and income distributions look broadly similar across genders, but spending score shows slightly more spread among female customers — hinting that spending behavior, more than income or age, is where gender differences show up.

### 4. Age Group Distribution

**Insight:** The **26–35** age bracket is the largest customer group by a clear margin, followed by 18–25. This is the mall's core demographic and the natural focus for marketing spend.

### 5. Annual Income Distribution (Bucketed)

**Insight:** The largest income bracket falls in the mid-range, with a healthy number of customers also earning $90k+ — a strong signal for a premium/loyalty segment.

### 6. Spending Score Distribution (Bucketed)

**Insight:** Spending scores are fairly evenly distributed across low, mid, and high bands, reinforcing that customers can't be treated as a single group — segmentation genuinely adds value here.

### 7. Income vs. Spending Score (Before Clustering)

**Insight:** Even before running K-Means, five visually distinct groupings are apparent in the income-vs-spending relationship — a strong early signal that clustering will produce clean, interpretable segments.

### 8. Elbow Method — Optimal Cluster Count

**Insight:** WCSS (within-cluster sum of squares) drops sharply up to a point and then flattens — the classic "elbow." This was used to choose **k = 4** for Age vs. Spending Score and **k = 5** for Income vs. Spending Score and for the full multi-feature clustering.

### 9. K-Means: Age vs. Spending Score (k = 4)

**Insight:** Younger customers split into high- and low-spending groups, while older customers cluster more tightly around moderate spending — spending behavior varies more by age at the younger end of the range.

### 10. K-Means: Annual Income vs. Spending Score (k = 5)

**Insight:** This is the headline result of the project — five clean, business-interpretable segments emerge:

- **High income, high spending** → premium/target customers
- **High income, low spending** → price-sensitive despite affluence; upsell opportunity
- **Low income, high spending** → deal-driven, promotion-responsive
- **Low income, low spending** → cautious spenders, low priority for premium campaigns
- **Average income, average spending** → the "typical" mainstream customer

### 11. K-Means on All Features — 3D View (k = 5)

**Insight:** Combining Age, Income, and Spending Score into one 3D clustering confirms the 5-segment structure holds even with age factored in, giving a more complete customer profile per cluster than any single 2D view alone.

---

## ⚙️ How to Run

```bash
# Clone the repository
git clone <your-repo-url>
cd customer-segmentation

# Install dependencies
pip install numpy pandas matplotlib seaborn scikit-learn jupyter

# Launch the notebook
jupyter notebook Customer_Segmentation.ipynb
```

To view the dashboard, open the `.pbix` file in **Power BI Desktop**.

---

## 🔑 Key Takeaways

- Customers cleanly separate into **5 actionable segments** based on income and spending behavior.
- The **26–35 age group** and **female customers** form the largest slices of the base.
- Segments like *"high income, low spending"* and *"low income, high spending"* highlight where targeted marketing could shift behavior the most.
- The Power BI dashboard turns these clusters into a live, filterable view for business stakeholders.

---

## 👤 Author

**Siddhi Tiwari**
