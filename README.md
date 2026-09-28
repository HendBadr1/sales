# Sales Performance Dashboard

An interactive Power BI report analyzing sales performance across time, product categories, and geography, built with a main overview page and drill-through detail pages for deeper analysis.

---

## Project Contents

| File | Description |
|---|---|
| `sales_data.pbix` | Main Power BI file (data model + 4-page report). |

---

# Data Source

A single core table named:
```
Sales_Raw
```

### Key columns:
- `Order Date` — used as a full date hierarchy (Year → Quarter → Month → Day).
- `Category` / `Sub-Category` — product classification.
- `Country` / `State` / `City` — customer/order location.

### DAX Measures:
- `total_sales` — total sales value.
- `num_cust` — number of unique customers.
- `num_orders` — number of orders.
- `ava_duration` — average order/delivery duration.

---

## 📊 Report Pages

### Page 1 — Overview
| Visual | Metric |
|---|---|
| Card | `total_sales` |
| Card | `num_cust` |
| Card | `num_orders` |
| Card | `ava_duration` |
| Line Chart | `total_sales` trend over the Order Date hierarchy (Year/Quarter/Month/Day) |
| Column Chart | `total_sales` by `Category` |
| Map | `total_sales` by `State` (bubble size) |

Includes a back navigation button (used when returning from a drill-through page).

### Page 2 — Location Detail (drill-through)
| Visual | Metric |
|---|---|
| Table | `Country`, `City`, `total_sales` |

### Page 3 — Duration Detail (drill-through)
| Visual | Metric |
|---|---|
| Card | `ava_duration` |
| Line Chart | `ava_duration` trend over the Order Date hierarchy |
| Donut Chart | `total_sales` by `Category` |

### Page 4 — Category Detail
| Visual | Metric |
|---|---|
| Table | `Category`, `Sub-Category`, `total_sales` |

Includes a back navigation button.

---

## 🛠️ Tools Used

- **Power BI Desktop** — data modeling and report design.
- **Power Query** — data preparation.
- **DAX** — measures (`total_sales`, `num_cust`, `num_orders`, `ava_duration`).

---

## How to Run

1. Open `sales_data.pbix` using **Power BI Desktop** (latest version recommended).
2. If prompted, click **Refresh** from the Home tab to reload the data.
3. On Page 1, right-click a state (map) or category (column chart) to drill through to the detail pages, then use the back button to return.

---

## 📌 Notes

- The report is structured as one overview page plus focused drill-through pages, keeping the main dashboard clean while still allowing deeper geographic and category-level analysis on demand.
