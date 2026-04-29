# 📦 Warehouse Operations Performance Report
### PowerBI · Supply Chain Analytics · Industry 4.0

An interactive multi-page PowerBI report analyzing warehouse operations performance, inventory management, logistics efficiency and KPI tracking.

---

## 📊 Report Overview

The report consists of **7 pages** with interactive navigation:

| Page | Content |
|------|---------|
| 🏠 Index | Interactive navigation hub with page buttons |
| 📊 Executive Overview | KPI cards + Orders distribution by category |
| 📦 Stock & Inventory | Stock levels vs reorder points + Stock by zone |
| ⚡ Picking & Efficiency | Picking time vs handling cost + Layout efficiency |
| 🚚 Shipment & Logistics | Delay analysis table + Delay distribution by cause |
| 📈 Inventory Performance | Rotation index + Unit price by category |
| 🏆 KPI Scorecard | Performance matrix + KPI flag + Evasion rate |

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| PowerBI Desktop | Dashboard development |
| Power Query | Data cleaning and transformation |
| DAX | Custom measures and KPI calculation |
| Kaggle | Source datasets |

---

## 📐 Data Model

Two datasets connected via relationship:

**Dataset 1 — Warehouse Operations**
- 500 rows · 16 columns
- Source: Kaggle — Logistics Warehouse Dataset
- Key fields: Category, Stock Level, Reorder Point, Picking Time, Order Fulfillment Rate, KPI Score

**Dataset 2 — Logistics Performance**
- 500 rows · 11 columns
- Source: Kaggle — Smart Logistics Supply Chain Dataset
- Key fields: Asset ID, Shipment Status, Waiting Time, Asset Utilization, Logistics Delay Reason

---

## 🔢 DAX Measures

```dax
-- Tasso Evasione %
-- Average order fulfillment rate across all products
Tasso Evasione % =
AVERAGE('Warehouse Operations'[Tasso Evasione Ordini])

-- Performance Flag
-- Classifies each category as Top, Media or Critica based on KPI Score
Performance Flag =
SWITCH(
    TRUE(),
    AVERAGE('Warehouse Operations'[KPI Score]) >= 535, "🟢 Top",
    AVERAGE('Warehouse Operations'[KPI Score]) >= 520, "🟡 Media",
    "🔴 Critica"
)

-- Obiettivo KPI
-- Fixed KPI target value for gauge visualization
Obiettivo KPI = 535
```

---

## 🎨 Design

- **Theme**: Custom color palette
- **Primary color**: `#1A2B4A` Navy Blue
- **Accent color**: `#E67E22` Orange
- **Positive indicator**: `#2ECC71` Green
- **Font**: Segoe UI
- **Background**: `#F5F7FA` Light Gray

---

## 📋 Key Insights

The report reveals several operational patterns across the warehouse:

**Stock Management** — All product categories maintain stock levels significantly above their reorder points, suggesting adequate inventory management but potential overstock in some zones.

**Picking Efficiency** — Apparel shows the highest handling costs despite similar picking times to other categories, indicating potential process optimization opportunities.

**Logistics Delays** — Weather and Traffic are the primary causes of logistics delays, each accounting for roughly equal share of total disruptions.

**KPI Performance** — Electronics leads with the highest KPI Score (Top performance), while Automotive and Groceries fall in the Critica range, suggesting areas for operational improvement.

---

## ⚙️ Setup

1. Download the `.pbix` file
2. Open with **PowerBI Desktop** (free download at powerbi.microsoft.com)
3. Data is embedded — no external connections needed
4. Navigate using the interactive buttons on the Index page

---

## 🏭 Industrial Context

This report simulates the type of operational reporting used in automated warehouse environments. Key metrics such as order fulfillment rate, stock rotation index and layout efficiency score are directly relevant to companies operating AGV fleets and automated logistics systems.

---

## 📄 License

MIT — feel free to use, modify and share.

---

## 👤 Author

**Matteo Daviddi**
Data Analyst & Process Automation
[LinkedIn](https://www.linkedin.com/in/matteodaviddi) · [GitHub](https://github.com/matteodaviddi)
