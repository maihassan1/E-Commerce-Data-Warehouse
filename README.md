
# E-commerce Data Warehouse

## 📌 Project Overview
This project is a data warehouse designed for an e-commerce platform. It supports business decision-making by enabling efficient querying and reporting on customer behavior, sales trends, campaign performance, and return analysis.

## 💡 Business Processes Modeled
1. **Sales Transactions**: Tracks customer purchases including product details, quantities, discounts, and revenue.
2. **Campaign Performance**: Measures the impact of marketing campaigns on customer purchases.
3. **Product Returns**: Monitors returned products, reasons, refund amounts, and return timing.

## 📦 Fact Tables and Grain

### 1. Sales Fact Table
- **Grain**: One record per product per customer per order line on a specific date.
- **Type**: Transaction fact table.
- **Measures**: Net Revenue (Fully Additive)

### 2. Campaign Performance Fact Table
- **Grain**: One record per customer, campaign, subcategory, and date.
- **Type**: Periodic snapshot fact table.
- **Measures**: Total quantity, total sales, net sales (Fully Additive)

### 3. Returns Fact Table
- **Grain**: One record per return transaction.
- **Type**: Transaction fact table.
- **Measures**: Quantity Returned, Processing Days (Fully Additive)

## 🧩 Dimensions

| Dimension       | Type                                        |
|----------------|---------------------------------------------|
| D_Date          | Role-Playing Dimension                      |
| D_Customer      | Slowly Changing Dimension (SCD), Conformed  |
| D_PaymentMethod | Static Dimension                            |
| D_Supplier      | Slowly Changing Dimension (SCD)             |
| D_Product       | Slowly Changing Dimension (SCD), Conformed  |
| D_Return        | Junk Dimension                              |

## 🗄️ Source System
- **OLTP Source**: [OLTP-Ecommerce-Data](https://www.kaggle.com/datasets/sharangkulkarni/oltp-ecommerce-data)

## 🔁 ETL Process
- **Control Flow & Data Flow**: Implemented using SSIS.
- **Batch Process**: Scheduled to update warehouse periodically.

## 📊 Queries and Reporting
- **Queries**: Built for analyzing sales trends, campaign success, and return patterns.
- **Visualization**: Dashboards created using Power BI.

## 📈 Tools & Technologies Used
- SQL Server
- Power BI
- SSIS 

