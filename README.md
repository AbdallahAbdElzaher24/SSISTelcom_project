# 📡 Telecom Data ETL Pipeline using SSIS

## 📌 Overview
This project implements a robust **End-to-End ETL Pipeline** designed to automate the ingestion and processing of large-scale **Telecom datasets**. 
The system extracts raw data from flat files, applies complex business transformations, and loads cleaned data into **SQL Server**, while maintaining a strict **Error Handling** and **Auditing** framework.

---

## ⚙️ Workflow Architecture

### 1️⃣ Control Flow (Orchestration)
- **Foreach Loop Container**: Automates the processing of multiple source files dynamically in a single execution.
- **SQL Audit & Batching**: Logs execution metadata (Start/End time, status) using `Execute SQL Tasks` (`SQL_Batch` & `SQL_Audit`).
- **File Management**: Uses `File System Tasks` to archive or move files to designated folders after successful processing.

### 2️⃣ Data Flow (Transformation)
- **Data Cleaning**: Handling null values and standardizing formats via `Derived Column` transformations.
- **Feature Engineering**: Advanced business logic to extract telecom attributes like **TAC** (Type Allocation Code) and **SNR** (Serial Number).
- **Validation**: `Lookup Transformations` (`Lookup SubID`) to verify Subscriber IDs against database master tables.
- **Monitoring**: Integration of `Row Count` components at multiple stages for real-time data throughput tracking.

---

## 🛠️ Tech Stack
- **ETL Tool**: SQL Server Integration Services (SSIS)
- **Database**: SQL Server (T-SQL)
- **Environment**: Visual Studio / SQL Server Data Tools (SSDT)
- **Storage**: OLE DB Destinations & Flat File Sources

---

## 🛡️ Error Handling & Governance
The pipeline is designed to be **fail-safe** and resilient:
- **Error Redirection**: Automatically redirects records that fail during data conversion or truncation.
- **Noisy Data Management**: A dedicated staging area (`Noisy Data Base`) for invalid records, allowing the main pipeline to continue while capturing errors for manual review.
- **Data Integrity**: Ensures 100% traceability of processed vs. rejected records through specialized error output paths.

---

## 📈 Project Status & Metrics
| Component | Status | Function |
| :--- | :--- | :--- |
| **Control Flow** | ✅ Complete | Orchestration & Auditing |
| **Data Flow** | ✅ Complete | Transformation & Cleaning |
| **Error Handling** | ✅ Optimized | Redirecting Noisy Data |
| **Logging** | ✅ Enabled | SQL-based Batch Tracking |

