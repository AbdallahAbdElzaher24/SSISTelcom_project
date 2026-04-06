📡 Telecom Data Integration: End-to-End SSIS ETL Pipeline
📖 Overview
This project demonstrates a high-performance ETL (Extract, Transform, Load) pipeline designed to handle large-scale Telecom datasets. Developed using SQL Server Integration Services (SSIS), the pipeline automates the journey of raw data from flat files into a structured SQL Server environment, ensuring data quality through advanced transformations and a resilient error-handling framework.
🏗️ Architecture & Workflow
1. Control Flow (Orchestration)
The pipeline is designed for scalability and automation:

Dynamic File Processing: A Foreach Loop Container iterates through multiple source files, allowing for batch processing without manual intervention.

Operational Auditing: Custom Execute SQL Tasks (SQL_Batch and SQL_Audit) log every execution step, providing a full audit trail of the data ingestion process.

Automated File Lifecycle: Post-processing is handled by File System Tasks, which automatically move or archive files based on execution success.

2. Data Flow (Transformation Logic)
The core logic focuses on data integrity and business intelligence:

Data Cleansing: Handles null values and inconsistencies using Derived Column transformations.

Feature Engineering: Extracts critical telecom attributes such as TAC (Type Allocation Code) and SNR (Serial Number) during flight.

Verification: Implements Lookup Transformations to validate Subscriber IDs against reference tables.

Throughput Monitoring: Multiple Row Count components track records at every stage to ensure zero data loss.

3. Error Handling & Governance
To maintain pipeline stability, a "Fail-Safe" mechanism was implemented:

Error Redirection: Any records failing data conversion or truncation are caught and redirected.

Noisy Data Management: Invalid records are stored in a dedicated Noisy Data Base for asynchronous troubleshooting, preventing the entire batch from failing.

🛠️ Tech Stack
ETL Tool: SQL Server Integration Services (SSIS)

Database: SQL Server (T-SQL)

Development: Visual Studio (SSDT)

Source Data: Flat Files (CSV/Text)

📂 Project Highlights
Efficiency: Automated ingestion of 10,000+ records via dynamic loops.

Quality: 100% data validation using lookup and null-handling logic.

Reliability: Robust error-handling framework for "noisy" datasets.
