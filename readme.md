<h1 align="center">📈 README: Customer Behavior and Sales Analysis (RIWI Sport) 📊</h1>

<p align="center">
  <img alt="Python" src="https://img.shields.io/badge/Python-3.10+-blue?style=for-the-badge&logo=python&logoColor=white">
  <img alt="Pandas" src="https://img.shields.io/badge/Data%20Wrangling-Pandas%20%26%20Numpy-150458?style=for-the-badge&logo=pandas&logoColor=white">
  <img alt="Seaborn" src="https://img.shields.io/badge/Visualization-Seaborn%20%26%20Matplotlib-2d8c36?style=for-the-badge&logo=seaborn&logoColor=white">
  <img alt="PostgreSQL" src="https://img.shields.io/badge/Database-PostgreSQL-336791?style=for-the-badge&logo=postgresql&logoColor=white">
  <img alt="Status" src="https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge">
</p>

---

## 📝 Project Description

This repository contains the exploratory and strategic analysis of the RIWI Sport use case, focused on customer behavior and sales to guide business actions.

## Main Objectives

1. 🔍 Measuring Behavior (KPIs)  
The main goal is to measure business performance and customer behavior by calculating key metrics.

- Measure Spending and Performance: Determine central tendency indicators (Mean, Median, Mode) and dispersion metrics (Standard Deviation, IQR) of spending per order and per customer.  
- Business KPIs: Calculate critical metrics such as Average Order Value (AOV) per order and per customer.  
- Identify Top Performers: Determine the Top 5 categories and products generating the highest revenue to focus inventory and strategies.

2. 🗺️ Strategic Guidance (Segmentation and Insights)  
The strategic goal is to use data to inform business decisions at a segmented level.

- Segmentation: Obtain sales and performance aggregates by key dimensions such as Category and City, allowing targeted geographic and product actions.  
- Risk/Opportunity Detection: Use visualizations (Histogram, Boxplot) to identify dispersion patterns, risks (e.g., low recurrence), and pricing optimization opportunities (Outliers).  
- Actionable Insight: Draft a non-trivial insight (e.g., LTV skew) that leads to a specific strategic recommendation for the Analytics Management.

---

## 🛠️ Project Structure

```text
riwi-sport-analytics/
├── analisis_RIWI_Sport_Martha-Garcia.ipynb  # 1. Main Notebook
├── informe_RIWI_Sport.md                              # 2. Executive Report
├── RiwiSport.sql                                           # Database File (Source)
├── README.md                                               # Setup Documentation
└── env.example 
```
                                               # Optional: Secure credentials (if using python-dotenv)


The analysis is contained in the main file and follows a standard data science workflow (ETL, EDA, KPIs, Visualization) to ensure reproducibility and clarity:

- analisis_RIWI_Sport_Martha_Garcia.ipynb: Contains all Python code (SQL, Pandas, NumPy, Matplotlib/Seaborn) and strategic conclusions.

- informe_RIWI_Sport.pdf (or .md): Document with executive summary, key KPIs, and actionable recommendation.

- RiwiSport.sql: SQL file (DDL + seeds) required to build the local database.

# 🚀 Setup and Execution Guide

Follow these steps to set up the virtual environment and ensure reproducibility of the analysis.

- Step 1: Virtual Environment Setup (Recommended)

- Open your terminal and run the following commands to create and activate an isolated environment:

```bash

# 1. Crear el entorno virtual (llamado 'riwi-env')
python3 -m venv riwi-env

# 2. Activar el entorno virtual
source riwi-env/bin/activate  # Para Linux/macOS
# riwi-env\Scripts\activate   # Para Windows

```

# Step 2: Install Dependencies

Once the environment is activated, install the required libraries.

Upgrade pip: Ensure pip is up to date.

```bash
pip install --upgrade pip
```

- Install Minimum Dependencies: Install the main analysis, database, and visualization libraries.


```bash
pip install pandas numpy matplotlib seaborn sqlalchemy psycopg2-binary python-dotenv
```
# Step 3: Register Jupyter Kernel

To allow your Notebook to use the libraries installed in riwi-env, register this environment as a Jupyter kernel:

```bash
# Instalar el paquete ipykernel dentro del entorno
pip install ipykernel

# Registrar el entorno con un nombre descriptivo (ej: 'RIWI_Kernel')
python -m ipykernel install --user --name=RIWI_Kernel --display-name="RIWI Sport Analytics"
```

Una vez hecho esto, al abrir el Notebook, podrás seleccionarlo desde el menú de kernels. 


# Step 4: Database Configuration (PostgreSQL)

Before running the Notebook, ensure the riwisport database exists and is populated:

Restore DB: Use pgAdmin or the PostgreSQL command line (psql) to create a database named riwisport.

Populate Tables: Execute RiwiSport.sql against the riwisport database to create and seed the tables (customer, order, product, category, etc.).

# Step 5: Credentials Configuration

The Notebook uses an SQLAlchemy connection engine that requires credentials. Although the Notebook contains a block for defining variables directly, it is recommended to use a .env file for security.

Example .env file (in the same directory as the Notebook):

```bash

# Variables de Entorno para la Conexión a PostgreSQL
DB_USER=postgres
DB_PASSWORD=tu_contraseña_de_postgres
DB_HOST=localhost
DB_PORT=5432
DB_NAME=riwisport

```

# 🏃 Execution Instructions

- Ensure your riwisport database is running and populated.

- Open analisis_RIWI_Sport_[Your-Name].ipynb in Jupyter or VS Code.

- Check Section 0: Initial Setup — verify that the connection string credentials (DB_URI) are correct.

- Run the cells sequentially from start to finish. The first cell will validate the database connection.

- The Notebook will execute the ETL, EDA, KPI Analysis, Segmentation, and Visualization steps to generate all project metrics and charts.