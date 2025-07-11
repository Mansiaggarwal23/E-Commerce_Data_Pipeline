# 🛒 E-Commerce Data Pipeline

This project demonstrates a complete data engineering pipeline for an e-commerce business, integrating **Apache Airflow**, **DBT**, and **Snowflake** to automate the flow of data from raw CSVs to analytical models. It includes data orchestration, transformation, monitoring, and a foundation for business insights.

---

## 📦 Project Components

### 🔹 1. Airflow (Orchestration)
Located in the `airflow_project/` directory:
- DAGs for monitoring order delays
- Custom Python utilities for order checks
- Email alerting (configurable)
- Scheduling and pipeline automation

### 🔹 2. DBT (Transformation)
Located in `dbt_ecommerce/`:
- Source staging for orders, customers, and shipments
- Data modeling with transformation logic
- Final marts (e.g., `order_status.sql`)
- Snapshots, tests, macros, and seeds setup for expansion

### 🔹 3. Dummy Data Creation
In `dummy_data_creation/`:
- Jupyter notebook and CSVs for creating synthetic e-commerce data (`customers.csv`, `orders.csv`, `shipments.csv`)

---

## 🔧 Technologies Used

- **Apache Airflow** – workflow orchestration
- **Python** – utility scripts and data handling
- **DBT** – SQL-based data transformation
- **Snowflake** – target data warehouse
- **Jupyter Notebook** – for data creation
- **Git & GitHub** – version control

---

## 🚀 How to Run This Project

### 1. Clone the Repository
```bash
git clone https://github.com/Mansiaggarwal23/E-Commerce_Data_Pipeline.git
cd E-Commerce_Data_Pipeline
````

### 2. Set Up Virtual Environment

```bash
python -m venv airflow_venv
source airflow_venv/bin/activate   # On Windows: airflow_venv\Scripts\activate
pip install -r requirements.txt    # Make sure you have one or install manually
```

### 3. Configure Airflow

* Update `airflow.cfg` if needed
* Place your **Snowflake credentials** in `airflow_project/dags/utils/config/snowflake_config.yaml` (this file is excluded from Git)

### 4. Run Airflow

```bash
airflow db init
airflow webserver --port 8080
airflow scheduler
```

Visit `http://localhost:8080` to view and trigger DAGs.

### 5. Setup DBT

```bash
cd dbt_ecommerce/ecommerce/
dbt deps
dbt seed
dbt run
dbt test
```

Make sure your `~/.dbt/profiles.yml` is configured with your Snowflake credentials.

---

## 📈 Example Use Case

* Monitor delayed orders via Airflow DAG
* Transform raw order, customer, and shipment data
* Generate a mart table showing order statuses
* Alert the ops team via email if delays occur

---

## 🔗 Useful Links

* [Apache Airflow](https://airflow.apache.org/)
* [DBT Documentation](https://docs.getdbt.com/)
* [Snowflake Docs](https://docs.snowflake.com/)

