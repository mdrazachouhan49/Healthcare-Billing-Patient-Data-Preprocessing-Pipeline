# 🏥 Healthcare Billing & Patient Data Preprocessing Pipeline

![Python](https://img.shields.io/badge/Python-3.13-blue?style=for-the-badge&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

##  Project Overview
This project implements a robust **ETL (Extract, Transform, Load)** process designed to clean, merge, and analyze healthcare datasets. The primary objective is to consolidate **Patient Demographics** and **Billing Information** to derive actionable insights regarding hospital revenue and insurance coverage.

Using **Pandas** and **NumPy**, this notebook simulates a real-world data engineering task: handling missing values, removing administrative noise, managing duplicates, and performing complex joins to prepare data for downstream analysis.

##  Key Features & Methodology
The `Basic_Stats_2.ipynb` notebook executes the following technical workflow:

1.  **Data Ingestion & Inspection**: 
    - Automated loading of CSV datasets (`Patient_Data.csv`, `Billing_Data.csv`).
    - Schema validation and memory usage analysis using `df.info()`.
2.  **Dimensionality Reduction**:
    - Removal of non-analytical features (e.g., `ReceptionistID`, `CheckInTime`) to optimize memory and focus on analytical relevance.
3.  **Data Cleaning & Quality Assurance**:
    - **Deduplication**: Identification and removal of duplicate patient records.
    - **Imputation**: Handling missing `BillAmount` values using **Mean Imputation** techniques to preserve statistical distribution.
4.  **Feature Engineering**:
    - Creation of calculated fields such as `FinalAmount` (post-insurance adjustments).
    - Synthetic column generation (`InsuranceCovered`).
5.  **Data Aggregation**:
    - Group-by operations to calculate total revenue per Medical Department (Cardiology, Orthopedics, etc.).
6.  **Data Merging**:
    - Performing **Inner Joins** to align patient identifiers with financial records.

## Tech Stack
* **Language:** Python 3.x
* **Libraries:** * `pandas`: Core data manipulation and aggregation.
    * `numpy`: Numerical operations.

##  Data Schema
The project processes two primary data structures:

| Dataset | Key Columns | Description |
| :--- | :--- | :--- |
| **Patient Data** | `PatientID`, `Name`, `Department`, `Doctor` | Core demographic and clinical assignment data. |
| **Billing Data** | `PatientID`, `BillAmount` | Financial records linked by PatientID. |

##  Results & Insights
The pipeline successfully processes the raw data to output:
1.  **Cleaned Master Dataset:** A merged view of patients and their final billing status.
2.  **Department-wise Revenue Analysis:**

| Department | Total Revenue Generated |
| :--- | :--- |
| **Cardiology** | $16,200.0 |
| **Orthopedics** | $7,500.0 |
| **Dermatology** | $0.0 (Data Gaps/Probono) |
| **Neurology** | $0.0 (Data Gaps/Probono) |

## Installation & Usage
To run this analysis locally:

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/yourusername/healthcare-etl-pipeline.git](https://github.com/yourusername/healthcare-etl-pipeline.git)
    ```
2.  **Install dependencies:**
    ```bash
    pip install pandas numpy
    ```
3.  **Run the Notebook:**
    Launch Jupyter Notebook and open `Basic_Stats_2.ipynb`. Ensure `Patient_Data.csv` and `Billing_Data.csv` are in the root directory.

## Contribution
Contributions are welcome! Please fork the repository and submit a pull request for any enhancements in data visualization or additional feature engineering.

---
*Author: Md Raza Chouhan*
