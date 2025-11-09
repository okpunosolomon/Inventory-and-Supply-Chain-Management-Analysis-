# 📘 DAX Measures Documentation

**Project:** Inventory & Supply Chain Management Analysis (Power BI)
**Purpose:** Core performance metrics used to evaluate warehouse efficiency, inventory control, and supply chain effectiveness.

---

## 🧮 1. Warehouse Utilization (%)

**Formula:**

```DAX
Warehouse Utilization = 
DIVIDE(
    [Warehouse Capacity Used],
    [Total Capacity],
    0
) * 100
```

**Explanation:**
Calculates the percentage of available warehouse capacity currently in use.
A higher value indicates stronger utilization, though excessive values may suggest overcrowding or limited scalability.
Ideal utilization: **70–85%**, balancing efficiency and flexibility.

---

## 🧮 2. Days Sales of Inventory (DSI)

**Formula:**

```DAX
Days Sales of Inventory = 
DIVIDE(
    365,
    [Inventory Turnover Ratio],
    0
)
```

**Explanation:**
Represents the average number of days inventory remains in stock before being sold.
It’s a key measure of inventory liquidity and operational responsiveness.
Lower values = faster turnover and better inventory management.

---

## 🧮 3. Inventory Turnover Ratio

**Formula:**

```DAX
Inventory Turnover Ratio = 
DIVIDE(
    [Cost of Goods Sold],
    [Average Inventory],
    0
)
```

**Explanation:**
Measures how many times inventory is sold or replaced within a year.
A higher ratio indicates efficient inventory utilization and strong sales movement, while a lower one may suggest overstocking or slow-moving goods.

---

## 🧮 4. Average Lead Time (Days)

**Formula:**

```DAX
Average Lead Time = 
AVERAGE('Inventory_SupplyChain_Dataset'[Lead Time])
```

**Explanation:**
Determines the average time taken for a product order to be processed, shipped, and received.
It helps evaluate supplier reliability and process efficiency.
Consistent lead times are crucial for accurate demand forecasting and customer satisfaction.

---

## 🧮 5. Backorder Count

**Formula:**

```DAX
Backorder Count = 
COUNTROWS(
    FILTER(
        'Inventory_SupplyChain_Dataset',
        'Inventory_SupplyChain_Dataset'[Order Status] = "Pending"
    )
)
```

**Explanation:**
Counts all orders not yet fulfilled due to insufficient stock or logistical delays.
This KPI identifies process bottlenecks and helps prevent recurring shortages.

---

## 🧮 6. Transportation Cost by Region and Category

**Formula:**

```DAX
Total Transportation Cost = 
SUM('Inventory_SupplyChain_Dataset'[Transportation Cost])
```

**Explanation:**
Aggregates all transportation expenses across regions and product categories.
It’s essential for cost optimization and for identifying where logistics spending can be streamlined or reallocated.

---

## 🧮 7. Inventory Level by Region and Category

**Formula:**

```DAX
Total Inventory Level = 
SUM('Inventory_SupplyChain_Dataset'[Inventory Level])
```

**Explanation:**
Represents the current quantity of stock available.
Used alongside warehouse utilization and turnover metrics to maintain optimal stock balance across all categories and regions.

---

## 💡 Summary

These DAX measures form the analytical foundation of the **Inventory & Supply Chain Dashboard**.
Together, they deliver real-time visibility into stock flow, operational efficiency, and cost distribution, therefore empowering businesses to make evidence-based decisions and optimize their end-to-end supply chain.

---
