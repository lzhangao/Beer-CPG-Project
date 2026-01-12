# Project Background
This project supports a small B2B craft beer company that distributes packaged product through a third-party distributor while managing sales activity internally through a CRM. Sales data was received in periodic CSV files from the distributor and existed separately from customer and deal data tracked in HubSpot and Map My Customers (MMC). As a result, leadership lacked a consistent, reliable view of product movement, account performance, and sales rep effectiveness.

The goal of this project was to design a centralized analytics workflow that connected distributor sales data with internal CRM data, standardized customer and product records, and enabled ongoing reporting while minimizing manual intervention. The solution focused on building a clean data structure, automating daily ingestion, and delivering clear performance insights to non-technical stakeholders across sales and operations.

# Data Structure Overview
![data structure diagram](data_structure_diagram.jpg)

|Orders         |type   |
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

|Meetings            |type      |
|--------------------|----------|
| Company ID         | int      |
| Company Name       | string   |
| SalesPerson Name   | string   |
| Meeting Type       | string   |
| Meeting Date       | datetime |
| Meeting notes      | string   |
| Associated Deal    | string   |
| Associated Deal ID | int      |

|Companies          |type    |
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

# Process Review
# Methods
Implemented automated CSV ingestion of distributor order data via email-triggered Azure Logic Apps. Files are written to Azure Blob Storage and processed by a SQL Server stored procedure.

Maintained a RawOrders table to preserve all inbound distributor data and a CleanOrders table applying custom business logic, schema normalization, and derived metrics.

Built a Python-based HubSpot API integration to pull current company records and properties into SQL Server on a scheduled basis.

Created SQL views to reconcile order data with CRM company records and identify mismatches and enrichment gaps.

Pushed curated company updates back to HubSpot to maintain a single source of truth across systems.

# Insights
Sales concentration: A small, consistent subset of accounts drives a disproportionate share of revenue, indicating a clear Protect/Grow account segment.

SKU mix: The original launch flavor is being outperformed by newer SKUs, suggesting shifting customer preferences.

Sales activity: Historical sales outreach showed high variability across reps. Introducing minimum activity benchmarks, combined with reduced administrative overhead, increased outreach volume by 50%+ for newer reps.

Better access to 

# Recommendations
Reduce CRM complexity- sales reps should only use HubSpot for meeting activities to eliminate need for integration and managing multiple apps. Reduce MMC licenses down to 1, saving ~$10k/year. One MMC superuser can perform all territory and mapping tasks

Set ambitious but reasonable expectations for rep activity. Incentives for meeting standards

Aggressively market newer SKUs to capitalize on shifting consumer preferences and grow those points of distribution.
