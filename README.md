# Modern Data Warehouse: E-commerce ELT Pipeline 🚀

This project demonstrates a production-grade ELT pipeline building a **Modern Data Warehouse** using **Google BigQuery** and **dbt**. It transforms raw e-commerce data (Olist Dataset) into actionable analytical models (Star Schema).

## 🛠 Tech Stack
* **Storage & Compute:** Google BigQuery (Cloud Data Warehouse)
* **Transformation:** dbt (data build tool)
* **Orchestration:** Python / Google Colab
* **Data Source:** Kaggle API (Brazilian E-commerce Dataset)

## 🏗 Architecture
The pipeline follows the **Medallion Architecture**:
1. **Raw Layer:** CSV data ingested directly into BigQuery `ecommerce_raw`.
2. **Staging Layer:** Cleaned and casted views using dbt.
3. **Marts Layer:** Denormalized fact and dimension tables optimized for BI tools (Looker/Tableau).

## 💡 Key Engineering Challenges Solved
* **Cost Optimization:** Refactored dbt models to work within the **BigQuery Sandbox (Free Tier)** by implementing custom table materialization instead of incremental merge (DML-restricted).
* **Data Integrity:** Handled schema inconsistencies and string-to-timestamp conversions using `SAFE_CAST` and robust SQL transformations.
* **Global Refactoring:** Automated the migration of project IDs and environment configurations for seamless deployment.

## 🚀 How to Run
1. Clone the repo.
2. Setup your `profiles.yml` with your GCP Project ID.
3. Run `dbt deps` to install dependencies.
4. Execute `dbt run` to build the warehouse.
