# DS-2002 Mid-Term Project

#### **1. Overview**
This project demonstrates an ETL (Extract, Transform, Load) pipeline using MySQL, MongoDB, and local file system data sources to populate a dimensional data mart. The goal is to process structured and semi-structured data from multiple sources and store it in a data warehouse for analysis.
This project designs a dimensional data mart for customer order analysis in a retail business. The data mart is structured to support historical sales performance tracking, customer purchasing behavior, and inventory insights.

#### **2. Data Sources**
- **Provided Scripts**
  - AdventureWoks_MySQL(Source Database)
  - AdventureWorks_Queries_MySQL(Views for AdventureWorks)
  - Lab_02c_Create_Populate_Dim_Date(Date)
- **MySQL (AdventureWorks_DW database)**
  - Extracted `fact_sales_orders` (Fact Table)
  - Extracted `dim_customers` (Dimension Table)
  - Extracted `dim_products` (Dimension Table)
  - Extracted `dim_date` (Date Dimension)
- **MongoDB**
  - Inserted `fact_sales_orders`, `dim_customers`, and `dim_products` into MongoDB collections
  - Retrieved and verified the data from MongoDB
- **Local File System**
  - Saved `dim_products.csv` locally for further analysis


### **3. ETL Process**
#### **Step 1: Extract Data**
- Queried MySQL database to retrieve fact and dimension tables.
- Transformed data to align with the data warehouse schema.
- Saved extracted data in JSON format before inserting it into MongoDB.

#### **Step 2: Transform Data**
- Renamed columns to maintain consistency.
- Established primary and foreign key relationships.
- Mapped `order_date_key` using `dim_date` to standardize dates.

#### **Step 3: Load Data**
- Inserted JSON data into MongoDB.
- Exported the `dim_products` dimension as a CSV file.



### **4. Deployment Strategy**
- Connections to MySQL and MongoDB are handled via helper functions (`get_sql_dataframe()`, `get_mongo_dataframe()`, etc.).
- Data is exported in multiple formats for different use cases (JSON for MongoDB, CSV for local storage).
- The process follows **Lab 3 and Lab 4 methodologies**, ensuring compliance with project requirements.


### **5. Verification and Testing**
- **SQL Queries** were used to verify the integrity of foreign key mappings.
- **DataFrames** were displayed after each major step to confirm transformations.
- **MongoDB `count_documents()`** was used to confirm successful insertion.
- **CSV file validation** ensured the local file was saved and accessible.


