# E-commerce-Event-Driven-Data-Pipeline
Built an event-driven E-commerce ETL pipeline on Databricks (PySpark, Delta Lake) with automated ingestion, data validation, SCD Type 2 implementation.



---

## 🧩 3️⃣ Component-wise Architecture Explanation (Very Important)

```md
## 🧩 Architecture Components

### 1. Source Layer – Databricks Volumes
Stores raw e-commerce data files including orders, customers, products, inventory, and shipping datasets.

### 2. Event Trigger Layer
JSON trigger files initiate batch processing and control workflow execution in Databricks Workflows.

### 3. Ingestion Layer
PySpark-based ingestion notebooks perform automated file loading, schema validation, and batch metadata tracking.

### 4. Staging Layer (Delta Lake)
Raw data is standardized and stored as Delta tables to support validation and reprocessing.

### 5. Data Quality Layer
Implements cross-reference validation, business rule checks, and severity-based data quality scoring.

### 6. SCD Type 2 Layer
Maintains historical dimension data using effective start/end dates and Delta Lake MERGE operations.

### 7. Analytics & BI Layer
Provides analytics-ready fact and dimension tables for dashboards, KPIs, customer segmentation, and CLV analysis.

### 8. Monitoring & File Management
Handles file archiving, error logging, batch status tracking, and pipeline observability.
