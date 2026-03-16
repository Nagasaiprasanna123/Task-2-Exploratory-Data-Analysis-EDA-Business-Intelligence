# Sales Data Analysis | Python & SQL

A comprehensive **Exploratory Data Analysis (EDA)** project analyzing electronics sales data across India using Python and SQL. This project demonstrates data manipulation, visualization, and SQL querying techniques on a real-world dataset.

## 📊 Project Overview

This analysis examines **200 electronics sales transactions** across **6 major Indian cities** from January to June 2024. The dataset includes 8 product types, 4 payment methods, and customer satisfaction ratings.

### Key Metrics
- **Total Revenue**: Rs. 1,08,01,600 (1.08 Crore)
- **Total Orders**: 200 transactions
- **Geographic Reach**: Chennai, Mumbai, Delhi, Bangalore, Hyderabad, Pune
- **Average Customer Rating**: 3.94/5 ⭐
- **Top Product**: Laptop (35.8% of revenue)
- **Top City**: Delhi (20.3% of revenue)

## 🎯 Quick Start

### Prerequisites
```bash
python 3.8+
pandas >= 1.3.0
matplotlib >= 3.4.0
seaborn >= 0.11.0
sqlite3 (built-in)
jupyter notebook
```

### Installation

1. Clone the repository:
```bash
git clone https://github.com/Naga-sai-prasanna-123/sales-data-analysis.git
cd sales-data-analysis
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Run the Jupyter notebook:
```bash
jupyter notebook Sales_Data_Analysis.ipynb
```

## 📁 Project Structure

```
sales-data-analysis/
├── README.md                          # Project documentation
├── requirements.txt                   # Python dependencies
├── Sales_Data_Analysis.ipynb          # Main analysis notebook
├── Sales_Data_Analysis_Report.pdf     # Generated report
├── eda_sales_dataset.csv              # Raw dataset (200 rows × 11 columns)
├── sales.db                           # SQLite database
└── visualizations/
    ├── revenue_distribution.png
    ├── revenue_by_product.png
    ├── revenue_by_city.png
    ├── payment_methods.png
    ├── correlation_heatmap.png
    └── monthly_trend.png
```

## 🔍 Dataset Description

### File: `eda_sales_dataset.csv`
| Column | Type | Description |
|--------|------|-------------|
| Order_ID | Integer | Unique identifier (1001–1200) |
| Order_Date | Date | Date of transaction (2024) |
| Customer_Name | String | Customer name |
| City | String | City of origin |
| Product | String | Product type |
| Category | String | Category (all Electronics) |
| Quantity | Integer | Units purchased |
| Unit_Price | Integer | Price per unit (Rs.) |
| Payment_Method | String | Payment mode |
| Discount | Integer | Discount applied (Rs.) |
| Rating | Integer | Customer satisfaction (1–5) |

## 📈 Analysis Sections

### 1. **Revenue Analysis**
- Revenue distribution across orders (histogram)
- Product-wise revenue breakdown (bar chart)
- Top products: Laptop (Rs. 38.92L), Tablet (Rs. 25.56L), Phone (Rs. 24.38L)

### 2. **Geographic Analysis**
- City-wise revenue distribution
- Market penetration across 6 cities
- Revenue share by location

### 3. **Payment Methods**
- Distribution of payment modes
- UPI & Cash: 27% each (54 orders)
- Card: 24% (48 orders)
- Net Banking: 22% (44 orders)
- **Insight**: 73% digital payment adoption

### 4. **Correlation Analysis**
- Strong correlation: Revenue ↔ Unit_Price (0.86)
- Moderate correlation: Revenue ↔ Quantity (0.51)
- Weak correlation: Quantity ↔ Rating (0.02)

### 5. **Temporal Analysis**
- Monthly sales trend (Jan–Jun 2024)
- Seasonal buying patterns
- Peak performance in January (Rs. 22.1L)
- Low point in April (Rs. 11.9L)

### 6. **Customer Satisfaction**
- Average rating: 3.94/5
- Rating distribution analysis
- Correlation with purchase behavior

## 🗄️ SQL Queries

Key business queries included:

**Total Revenue:**
```sql
SELECT SUM(Quantity * Unit_Price - Discount) AS Total_Revenue
FROM sales;
-- Result: 10,80,16,00
```

**Revenue by Product:**
```sql
SELECT Product, SUM(Quantity * Unit_Price - Discount) AS Revenue
FROM sales
GROUP BY Product
ORDER BY Revenue DESC;
```

**Revenue by City:**
```sql
SELECT City, SUM(Quantity * Unit_Price - Discount) AS Revenue
FROM sales
GROUP BY City
ORDER BY Revenue DESC;
```

**Payment Method Distribution:**
```sql
SELECT Payment_Method, COUNT(*) AS Total_Orders
FROM sales
GROUP BY Payment_Method
ORDER BY Total_Orders DESC;
```

## 🔑 Key Insights

### 1. Laptop Dominance 🖥️
- **Laptops generate Rs. 38.92 Lakhs** — 35.8% of total revenue
- 52% more than the second-best product (Tablets)
- **Recommendation**: Prioritize inventory, offer EMI options, run targeted campaigns

### 2. Delhi Market Leadership 📍
- **Delhi contributes Rs. 22.07 Lakhs** — the highest across all cities
- All 6 cities relatively balanced (within 27% of each other)
- **Insight**: Good pan-India market penetration

### 3. Digital Payment Growth 📱
- **73% of customers use digital payments** (UPI + Card + Net Banking)
- UPI and Cash equally popular at 27% each
- **Opportunity**: Offer cashback incentives for UPI transactions

### 4. High-Value Products Drive Revenue 💰
- Laptops, Tablets, Phones: **81.7% of total revenue**
- Only 3 of 8 product types
- Accessories contribute <2% of revenue

### 5. Customer Satisfaction 😊
- **Average rating: 3.94/5** — above industry average
- Higher quantity purchases correlate with satisfaction
- **Goal**: Target 4.5+ rating through improved delivery and support

## 📊 Visualizations

All visualizations are generated using **Matplotlib** and **Seaborn**:

1. **Revenue Distribution Histogram** — Right-skewed, most orders Rs. 50K–Rs. 200K
2. **Revenue by Product Bar Chart** — Laptop dominance clearly visible
3. **Revenue by City Bar Chart** — Balanced distribution across 6 cities
4. **Payment Method Pie Chart** — Even split between digital and cash
5. **Correlation Heatmap** — Shows relationships between numeric variables
6. **Monthly Trend Line Chart** — Seasonal patterns visible

## 💡 Strategic Recommendations

| Recommendation | Action | Expected Impact |
|---|---|---|
| **Focus on High-Value Products** | Increase stock depth, offer EMI for Laptops/Tablets | Maximize revenue growth |
| **Expand Delhi Market** | City-specific promotions, leverage tech-savvy population in Bangalore | Boost market share |
| **Leverage Digital Payments** | Optimize UPI checkout, offer cashback | Increase adoption to 80%+ |
| **Improve Low-Value Products** | Bundle accessories with high-value items | Increase accessory revenue |
| **Boost Customer Ratings** | Post-purchase follow-ups, faster delivery | Target 4.5+ rating |

## 🛠️ Technologies Used

| Tool | Version | Purpose |
|------|---------|---------|
| Python | 3.x | Core programming language |
| Pandas | Latest | Data manipulation & analysis |
| Matplotlib | 3.10.6 | Visualization (histograms, bar charts, line plots) |
| Seaborn | Latest | Statistical visualizations |
| SQLite3 | Built-in | Database & SQL queries |
| Jupyter Notebook | Latest | Interactive analysis environment |

## 📈 Revenue Breakdown

| Product | Revenue (Rs.) | % Share | Rank |
|---------|---------------|---------|------|
| Laptop | 38,92,000 | 35.8% | #1 |
| Tablet | 25,56,000 | 23.5% | #2 |
| Phone | 24,37,500 | 22.4% | #3 |
| Monitor | 10,53,000 | 9.7% | #4 |
| Printer | 7,10,500 | 6.5% | #5 |
| Headphones | 76,500 | 0.7% | #6 |
| Keyboard | 55,100 | 0.5% | #7 |
| Mouse | 21,000 | 0.2% | #8 |

## 🌍 Geographic Distribution

| City | Revenue (Rs.) | % Share | Rank |
|------|---------------|---------|------|
| Delhi | 22,07,500 | 20.3% | #1 |
| Hyderabad | 18,40,100 | 16.9% | #2 |
| Mumbai | 18,23,700 | 16.8% | #3 |
| Chennai | 16,69,100 | 15.4% | #4 |
| Pune | 16,47,500 | 15.2% | #5 |
| Bangalore | 16,13,700 | 14.9% | #6 |

## 📝 Usage Examples

### Load and Explore Data
```python
import pandas as pd
df = pd.read_csv("eda_sales_dataset.csv")
print(df.shape)        # (200, 11)
print(df.dtypes)       # Check data types
print(df.isnull().sum()) # Check for missing values
```

### Create Revenue Column
```python
df["Revenue"] = df["Quantity"] * df["Unit_Price"] - df["Discount"]
```

### Generate Visualizations
```python
import matplotlib.pyplot as plt
import seaborn as sns

# Revenue distribution
plt.figure(figsize=(10, 6))
plt.hist(df["Revenue"], bins=20, color='steelblue')
plt.title("Revenue Distribution")
plt.xlabel("Revenue (Rs.)")
plt.ylabel("Frequency")
plt.show()

# Revenue by product
product_revenue = df.groupby("Product")["Revenue"].sum().sort_values(ascending=False)
product_revenue.plot(kind='bar', color='steelblue')
plt.title("Revenue by Product")
plt.show()
```

### Load into SQLite
```python
import sqlite3
conn = sqlite3.connect("sales.db")
df.to_sql("sales", conn, if_exists="replace", index=False)
conn.commit()
```

### SQL Query Example
```python
query = """
SELECT Product, SUM(Quantity * Unit_Price - Discount) as Revenue
FROM sales
GROUP BY Product
ORDER BY Revenue DESC
"""
result = pd.read_sql_query(query, conn)
print(result)
```

## 🐛 Troubleshooting

### Issue: Missing data or NaN values
**Solution**: Check `df.isnull().sum()` — this dataset has no missing values by design.

### Issue: SQLite database locked
**Solution**: Ensure all connections are closed (`conn.close()`)

### Issue: Visualization not displaying
**Solution**: Add `%matplotlib inline` in Jupyter or use `plt.show()`

## 📚 Learning Outcomes

By working through this project, you'll learn:
- ✅ Loading and exploring datasets with Pandas
- ✅ Data cleaning and preparation techniques
- ✅ Creating professional visualizations with Matplotlib & Seaborn
- ✅ SQL querying for business intelligence
- ✅ Statistical analysis and correlation studies
- ✅ Generating actionable business insights
- ✅ Building EDA reports

## 🤝 Contributing

Contributions are welcome! To contribute:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Make your changes
4. Commit with clear messages (`git commit -m "Add feature X"`)
5. Push to the branch (`git push origin feature/improvement`)
6. Open a Pull Request

## 📄 License

This project is licensed under the **MIT License** — see the LICENSE file for details.

## 👨‍💼 Author

**GALI NAGA SAI PRASANNA**  

## 🙏 Acknowledgments

- Dataset sourced from electronics sales records (2024)
- Analysis tools: Pandas, Matplotlib, Seaborn, SQLite
- Report generated using Jupyter Notebook

---

### Next Steps 🚀

1. **Extend the Analysis**: Add more time periods, products, or geographic regions
2. **Build a Dashboard**: Create an interactive Tableau/Power BI dashboard
3. **Predictive Modeling**: Forecast future sales using regression or time-series models
4. **Customer Segmentation**: Cluster customers based on purchase behavior
5. **A/B Testing**: Test promotions and pricing strategies

**Happy Analyzing! 📊**
