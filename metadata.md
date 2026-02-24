# Data Dictionary

You have access to **3 core tables** in the database. Understanding the relationship between these tables is crucial for your analysis.

---

## 1. Transactions Table (`ebay_transactions`)

Granular record of every item sold in Q4.

| Column          | Type      | Description                                                     |
|-----------------|-----------|-----------------------------------------------------------------|
| transaction_id  | INT       | Unique identifier for each transaction.                        |
| customer_id     | INT       | Links to `ebay_customers`.                                      |
| product_id      | INT       | Links to `ebay_products`.                                       |
| total_revenue   | DECIMAL   | The final sale price (GMV) of the transaction.                  |
| quantity        | INT       | Number of units sold in this transaction.                       |
| date            | TIMESTAMP | Exact date and time of purchase.                                |

---

## 2. Products Table (`ebay_products`)

Catalog of items and their base costs.

| Column        | Type    | Description                                                      |
|--------------|---------|------------------------------------------------------------------|
| product_id   | INT     | Unique product identifier.                                       |
| product_name | TEXT    | Public name of the product.                                      |
| category     | TEXT    | High-level grouping (e.g., Electronics, Fashion).                |
| cost_price   | DECIMAL | The cost to eBay/Seller (COGS). Used for margin calculation.     |

---

## 3. Customers Table (`ebay_customers`)

Demographic information on buyers.

| Column      | Type | Description                                                              |
|------------|------|--------------------------------------------------------------------------|
| customer_id | INT  | Unique customer identifier.                                              |
| name        | TEXT | Full name of the customer.                                               |
| segment     | TEXT | Market segment (e.g., Consumer, Corporate, Home Office).                |

---