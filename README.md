# E-commerce-Event-Driven-Data-Pipeline
Built an event-driven E-commerce ETL pipeline on Databricks (PySpark, Delta Lake) with automated ingestion, data validation, SCD Type 2 implementation.



---
##  Architecture Components

### 1. Source Layer – Amazon S3 (Databricks External Volumes)
Raw e-commerce data files (orders, customers, products, inventory, and shipping) are stored in **Amazon S3** and accessed securely through **Databricks External Volumes** for scalable and governed ingestion.


### 2. Event Trigger Layer
JSON trigger files initiate batch processing and control workflow execution in Databricks Workflows.

### 3. Ingestion Layer
PySpark-based ingestion is implemented using **dataset-specific notebooks**, where each notebook processes a single raw dataset (orders, customers, products, inventory, shipping). Raw data files are read into **Spark DataFrames** from Databricks External Volumes, followed by automated file loading and schema validation.


### 4. Staging Layer (Delta Lake)
Validated raw **Spark DataFrames** are standardized and written to **staging Delta tables using overwrite mode**, ensuring that each run maintains the latest trusted snapshot of source data.


### 5. Data Validation Layer
Performs **cross-reference validation and business rule checks on staging Delta tables** to ensure referential integrity across datasets.


### 6. SCD Type 2 Layer
Implements **Slowly Changing Dimension (Type 2)** logic to maintain historical dimension records by tracking **effective start and end dates**, managing updates through **Delta Lake MERGE operations**, and using an **is_current flag** to identify active records.

### Technology Used
- Databricks (Notebooks, Workflows, External Volumes)
- Apache Spark (PySpark)
- Delta Lake (ACID tables, MERGE operations, SCD Type 2)
- Amazon S3 (External Storage via Databricks External Volumes)

## 📁 Dataset Descriptions

- **Orders Dataset**  
  Here is the dataset used - https://github.com/Mahesh-moco/E-commerce-Event-Driven-Data-Pipeline/blob/main/data/2025_01_15/orders_2025_01_15.csv
- **Customers Dataset**  
  Here is the dataset used - https://github.com/Mahesh-moco/E-commerce-Event-Driven-Data-Pipeline/blob/main/data/2025_01_15/customers_2025_01_15.csv

- **Products Dataset**  
  Here is the dataset used - https://github.com/Mahesh-moco/E-commerce-Event-Driven-Data-Pipeline/blob/main/data/2025_01_15/products_2025_01_15.csv

- **Inventory Dataset**  
  Here is the dataset used - https://github.com/Mahesh-moco/E-commerce-Event-Driven-Data-Pipeline/blob/main/data/2025_01_15/inventory_2025_01_15.csv
- **Shipping Dataset**  
  Here is the dataset used - https://github.com/Mahesh-moco/E-commerce-Event-Driven-Data-Pipeline/blob/main/data/2025_01_15/shipping_2025_01_15.csv
