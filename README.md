# Project Background
This project supports a small B2B craft beer company that distributes packaged product through a third-party distributor while managing sales activity internally through a CRM. Sales data was received in periodic CSV files from the distributor and existed separately from customer and deal data tracked in HubSpot and Map My Customers (MMC). As a result, leadership lacked a consistent, reliable view of product movement, account performance, and sales rep effectiveness.

The goal of this project was to design a centralized analytics workflow that connected distributor sales data with internal CRM data, standardized customer and product records, and enabled ongoing reporting while minimizing manual intervention. The solution focused on building a clean data structure, automating daily ingestion, and delivering clear performance insights to non-technical stakeholders across sales and operations.

# Data Structure Overview

| Orders Data Structure|
|---------------|--------|
| Customer Key  | int    |
| Customer Name | string |
| Address       | string |
| City          | string |
| Postal Code   | int    |
| Premise Type  | string |
| Sales Person  | string |
| Sales Date    | date   |
| Order Number  | int    |
| Item Key      | int    |
| Item Name     | string |
| Item Price    | float  |
| Item Qty      | int    |
| Cases         | float  |
| Barrels       | float  |
| Net Revenue   | float  |

| Meetings Data Structure|
|--------------------|----------|
| Company ID         | int      |
| Company Name       | string   |
| SalesPerson Name   | string   |
| Meeting Type       | string   |
| Meeting Date       | datetime |
| Meeting notes      | string   |
| Associated Deal    | string   |
| Associated Deal ID | int      |

| Companies Data Structure|
|-------------------|--------|
| Record ID         | int    |
| Customer Key      | int    |
| Customer Name     | string |
| City              | string |
| Address           | string |
| Postal Code       | int    |
| Premise Type      | string |
| SoldIn By         | string |
| Managed By        | string |
| Territory         | string |
| SoldIn Date       | date   |
| LastOrder Date    | date   |
| LastMeeting Date  | date   |
| Customer Status   | string |
| Visit Frequency   | int    |
| Total Orders      | int    |
| Order Cadence     | int    |
| Barrels Per Month | float  |
| Barrels YTD       | float  |
