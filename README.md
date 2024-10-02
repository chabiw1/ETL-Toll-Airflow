# ETL Toll Data Pipeline with Apache Airflow

This project demonstrates the creation of an ETL (Extract, Transform, Load) pipeline using Python and Apache Airflow to process toll traffic data from different highway operators. Each operator has its own IT setup and file format (CSV, TSV, and fixed-width). The goal is to extract, transform, and load the data into a consistent format for further analysis.

## Industry
This project is related to the **Transportation and Logistics** industry, particularly in **Traffic Management and Toll Operations**. It focuses on optimizing traffic flow and infrastructure efficiency through the analysis of toll plaza traffic data.

Additionally, the project is associated with **Data Analytics Consulting**, as it involves solving traffic congestion issues by implementing ETL processes and analyzing data from various toll systems.

## Airflow DAG Workflow

The ETL process involves multiple steps, each handled by a Python function and orchestrated via Airflow's DAG and PythonOperator. The workflow follows these steps:

### Extracting Data

1. **CSV File:** Extracts toll vehicle data (vehicle number, vehicle type, timestamp) from a CSV file.
2. **TSV File:** Extracts toll plaza data (tollplaza ID, tollplaza code, number of axles) from a TSV file.
3. **Fixed-width File:** Extracts payment information (payment type, vehicle code) from a fixed-width file.

### Transforming Data

The extracted data from the CSV, TSV, and fixed-width files is consolidated into a single CSV file. Data transformations include standardizing fields such as converting the `Vehicle type` field to uppercase.

### Loading Data

The transformed data is saved in the staging area for further analysis and processing.

## How to Run the Project

1. **Run Airflow:**
   Start the Airflow web server and scheduler as mentioned above.

2. **View DAG in Airflow:**
   Access the Airflow web UI by visiting `http://localhost:8080`. You should see the DAG `ETL_toll_data` listed.

3. **Trigger the DAG:**
   Manually trigger the DAG to run the ETL process and monitor the tasks' execution.

## Project Files

- `workflow.py`: Defines the Airflow DAG for the ETL process.
- `vehicle-data.csv`: Sample CSV file containing vehicle data.
- `tollplaza-data.tsv`: Sample TSV file containing toll plaza data.
- `payment-data.txt`: Sample fixed-width file containing payment data.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
