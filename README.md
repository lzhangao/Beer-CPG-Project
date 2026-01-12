# Project Background
This project supports a small B2B craft beer company that distributes packaged product through third-party distributors while managing sales activity internally through a CRM. Sales data was received in periodic CSV files from distributors and existed separately from customer and deal data tracked in HubSpot. As a result, leadership lacked a consistent, reliable view of product movement, account performance, and sales rep effectiveness.

The goal of this project was to design a centralized analytics workflow that connected distributor sales data with internal CRM data, standardized customer and product records, and enabled ongoing reporting without manual intervention. The solution focused on building a clean data structure, automating daily ingestion, and delivering clear performance insights to non-technical stakeholders across sales and operations.

# Data Structure Overview
![Orders Data Structure](https://github.com/lzhangao/Beer-CPG-Project/blob/e5822b433967fd0878640461c184a950aff2e408/orders_ds.jpg)

| Customer Key  | int    |
|---------------|--------|
| Customer Name | string |
| City          | string |
| Address       | string |
| Postal Code   | int    |
| Premise Type  | string |
| Sales Person  | string |
| Sales Date    | date   |
| Item Key      | int    |
| Item Name     | string |
| Order Number  | int    |
| Item Price    | float  |
| Item Qty      | int    |
| Cases         | float  |
| Barrels       | float  |
| Net Revenue   | float  |
