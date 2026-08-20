# Vendor Performance Analysis
This project analyzes vendor performance to optimize inventory management, pricing strategies, and vendor relationships in a retail/wholesale context. Using purchase, sales, and inventory data, it identifies underperforming brands, evaluates vendor contributions, and provides data-driven recommendations to enhance profitability. The project leverages Python, SQL, and SQLite for data processing and analysis.

# BI Dashboard
<img width="1225" height="732" alt="image" src="https://github.com/user-attachments/assets/21342799-9a5c-4e5c-b8ca-41834adeef0a" />


# Project Overview
The goal was to address key business questions:
- Identify underperforming brands for promotional or pricing adjustments.
- Determine top vendors by sales and purchase contributions.
- Assess bulk purchasing impacts on unit costs.
- Evaluate inventory turnover to minimize holding costs.
- Compare profitability between high- and low-performing vendors.

# Dataset
The dataset includes CSV files with purchase, sales, and inventory data:
- **purchases.csv**: Transaction-level purchase data.
- **purchase_prices.csv**: Product pricing details.
- **vendor_invoice.csv**: Vendor billing and freight costs.
- **sales.csv**: Sales transactions.
- **begin_inventory.csv** and **end_inventory.csv**: Inventory snapshots (excluded from analysis).

# Methodology
1.**Data Ingestion**:
- Loaded CSV files into an **SQLite** database (inventory.db) using load_raw_data.py.
- Created tables named after filenames (e.g., purchases, sales).

2.**Exploratory Data Analysis (EDA)**:
- Explored table structures and relationships using SQL queries.
- Excluded begin_inventory and end_inventory as irrelevant to vendor performance.

3.**Data Aggregation**:
- Built a summary table (vendor_sales_summary) by joining purchases, purchase_prices, vendor_invoice, and sales.
- Calculated metrics: total purchase/sales quantities, gross profit, profit margin, stock turnover, and sales-to-purchase ratio.

4.**Data Cleaning**:
- Converted Volume to float, filled missing values with 0, trimmed categorical columns, and added calculated fields (e.g., GrossProfit).

5.**Analysis**:
- **Brand Performance**: Identified 198 brands with low sales but high margins.
- **Vendor Contribution**: Assessed top vendors' share of purchases.
- **Bulk Purchasing**: Analyzed unit cost reductions.
- **Inventory Turnover**: Highlighted vendors with slow-moving stock.
- **Profitability**: Compared margins between vendor groups using statistical tests.

6.**Statistical Validation**:
- Conducted a t-test to confirm significant profit margin differences.

# Key Findings
- **Underperforming Brands**: 198 brands showed low sales but high profit margins (e.g., Santa Rita Organic Svgn Bl: $9.99 sales, 66.47% margin), ideal for marketing or pricing adjustments.
- **Vendor Dependency**: Top 10 vendors accounted for 65.69% of purchases (e.g., Diageo North America: 16.30%), indicating over-reliance risks.
- **Bulk Purchasing**: Large orders reduced unit costs by ~72% (Small: $39.06, Large: $10.78), supporting bulk buying strategies.
- **Inventory Turnover**: $2.71M in unsold inventory identified, with vendors like Diageo ($722.21K) showing slow-moving stock.
- **Profitability**: Low-performing vendors had higher margins (41.55%) than top vendors (31.17%), suggesting distinct operational models.

# Recommendations
- **Promote High-Margin Brands**: Target the 198 underperforming brands with marketing or pricing tweaks to boost sales.
- **Diversify Vendors**: Reduce reliance on top 10 vendors by onboarding new suppliers.
- **Optimize Bulk Purchases**: Encourage bulk buying while managing inventory to prevent overstocking.
- **Improve Inventory Management**: Address $2.71M in unsold stock with clearance sales or adjusted purchase volumes.
- Vendor Strategies:
  - **Top Vendors**: Focus on cost efficiency or bundled promotions.
  - **Low Vendors**: Enhance marketing and distribution to leverage high margins.

# Repository Structure
- **data/:** Raw CSV files.
- **scripts/:**
  - **load_raw_data.py**: Ingests CSVs into SQLite.
  - **create_vendor_summary.py**: Generates and cleans the summary table.
  - **analysis.ipynb**: Jupyter notebook with EDA, analysis, and visualizations.
- **inventory.db**: SQLite database.
- **vendor_sales_summary.csv**: Exported summary table.
- **logs/:** Log files for ingestion and processing.

# Tools Used
- **Python**: Pandas, NumPy, Matplotlib, Seaborn, SciPy.
- **SQL**: SQLite for data storage and querying.
- **Jupyter Notebook**: For interactive analysis and visualization.

# Explore analysis in analysis.ipynb.

# Results
This project delivers actionable insights for optimizing vendor performance, reducing costs, and boosting profitability. By implementing the recommendations, the business can achieve sustainable growth and operational efficiency.
