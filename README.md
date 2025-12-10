### 🛍️ Retail Data Processing & Executive Dashboard
# Alteryx Workflow + Tableau Dashboard

This project demonstrates a complete <b>end-to-end retail data pipeline</b> built in <b>Alteryx</b>, followed by an <b>executive analytics</b> dashboard in <b>Tableau</b>.
The objective is to clean, standardize, and join multiple unstructured datasets, calculate KPIs, produce a consolidated output, and visualize actionable insights for business decision-making.

# 🎯 Project Objectives

1.	Ingest and clean **3 retail datasets** (Sales, Inventory, StoreMaster) with inconsistent schemas
2.	Standardize **store/material keys**, fix casing, trim prefixes, and clean numeric/text fields
3.	Parse and normalize dates; create weekly structures; **add data quality flags**
4.	Join datasets into a consolidated **“Store–Material–Week”** grain
5.	Compute retail KPIs:

    <ul><li>Units Sold</li>
	  <li>Net Sales</li>
	  <li>ASP (Avg Selling Price)</li>
	  <li>Week-over-Week comparisons</li>
	  <li>4-week rolling averages</li>
	  <li>Weeks of Supply (WOS)</li></ul>
8.	Build a **Tableau dashboard** for executive-level insights

# 🧩 Datasets

### 1. Sales Data
  
- Daily transactions
- Mixed IDs, mixed date formats
- Returns, promotions, and null values

### 2. Inventory Data
-	Weekly snapshots
-	Text in numeric columns (e.g., “–” → 0)
-	Null inventory positions

### 3. StoreMaster
-	Store attributes
-	Inconsistent casing and formatting


# 🔧 Alteryx Workflow Highlights

-  Loaded 3 separate datasets using Input Data tools  
-  Cleaned all text fields using Data Cleansing  
-  Standardized keys (StoreID, MaterialID)  
-  Parsed and aligned dates using Formula tools  
-  Created WeekStart (Monday) & WeekEnd  
-  Fixed negative values, nulls, and missing promo flags  
-  Cleaned On_Hand, On_Order, SafetyStock (“–” → 0)  
-  Joined Sales → Inventory → StoreMaster  
-  Aggregated to weekly grain  
-  Calculated KPIs:  
  - ASP  
  - WoW changes  
  - 4-week avg sales  
  - Weeks of Supply

The final output is exported as a consolidated flat file and used in Tableau.

# 📊 Tableau Dashboard

🔗 Tableau Public Link:
https://public.tableau.com/shared/5M4M8GJN4?:display_count=n&:origin=viz_share_link

The dashboard includes:
  - Weekly Sales, Units trends & ASP
  - Week of Supply
  - Sales Trend
  - WOS
  - Store Performance


# 📝 Assumptions

Included in: docs/Assumptions.txt

1.	WeekStart = Monday
2.	Inventory SnapshotDate aligns with Monday
3.	Null Net Sales → treated as 0
4.	“–” in numeric fields → 0
5.	Missing weeks remain as intentional gaps
6.	Sales follow a Monday–Sunday structure
