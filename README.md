# CarCompany Business Intelligence Project

## Overview
This project was developed as part of the Business Intelligence for Data Science course. The primary goal was to build a comprehensive Data Warehouse (DW) for CarCompany to monitor and analyze sales data effectively. By integrating data from various sources, the DW enables CarCompany to make data-driven decisions, track key metrics, and improve operational efficiency.

## Motivation and Goals
The motivation for creating a DW within CarCompany is to centralize and streamline data, enhancing data accuracy and accessibility. This centralized repository integrates data from customer interactions, sales transactions, employee activities, product information, and authorized service providers. Through this integration, CarCompany can track sales trends, optimize inventory, monitor employee performance, and enhance customer satisfaction.

## Project Components
### 1. OLTP Schema
The OLTP schema manages day-to-day transactions and stores data across several tables, including `Order`, `Customer`, `Product`, `Employee`, `CarDealer`, and `AuthorizedService`. Relationships among these tables allow for efficient data management and traceability of orders, customers, products, employees, and dealerships.

### 2. Data Warehouse (DW) Schema
A star schema structure was chosen for the DW due to its simplicity. The schema includes:
- **Fact Table: `Fact_Sales`** – Tracks key metrics like `QuantityOrdered`, `Price`, `TotalAmount`, and calculated `Sales` (net of sales commission).
- **Dimension Tables** – Four dimension tables:
  - `Dimension_CarDealerEmployee`: Details on employees and the car dealers they represent.
  - `Dimension_ProductService`: Car and service provider information.
  - `Dimension_CustomerOrder`: Customer and order details.
  - `Dimension_Time`: Temporal data for historical analysis.

### 3. ETL Processes
The project used Pentaho Data Integration to create ETL processes for transforming OLTP data into the DW. Each dimension table underwent specific transformations to populate the DW:
- `Dimension_CarDealerEmployee` – Merging data from `Employee` and `CarDealer`.
- `Dimension_ProductService` – Combining `Product` and `AuthorizedService`.
- `Dimension_Time` – Generating and transforming date-time attributes.
- `Dimension_CustomerOrder` – Merging data from `Customer` and `Order`.
- `Fact_Sales` – Aggregating sales data, calculating total amounts, and factoring in sales commission.

### 4. MySQL View
A view was created in MySQL to display sales performance across different car brands. This view helps in quick data retrieval and insights into brand-specific sales performance.

### 5. Pentaho Report
A report was generated in Pentaho Report Designer, providing insights into the service locations associated with a specific car brand. This report supports better after-sales service management and customer satisfaction tracking.

### 4. Data and Files
- **CSV Files**: 
  - `AuthorizedService.csv`
  - `CarDealer.csv`
  - `Customer.csv`
  - `Employee.csv`
  - `Order.csv`
  - `Product.csv`
- **Report**: `Business Intelligence Project.pdf` provides a detailed analysis and documentation of the project.
- **OLTP and DW Schemas**: Files `CarCompanyOLTP_MODEL.mwb` and `CarCompany_DW.mwb` contain schema diagrams for the OLTP and DW models.

## Skills and Technologies
- **Skills**: Data Warehousing, ETL Processes, Business Intelligence, Star Schema Modeling, Reporting
- **Technologies**: MySQL, Pentaho Data Integration, Pentaho Report Designer, MySQL Workbench
