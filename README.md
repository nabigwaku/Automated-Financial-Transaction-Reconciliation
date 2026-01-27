# Automated Financial Transaction Reconciliation  
**Python • Jupyter Notebooks • Tableau**

## Project Overview

In fintech and financial operations, thousands of transactions flow daily between banks, payment providers, and internal accounting systems. While these systems are supposed to agree, in reality they often don’t due to timing delays, missing references, duplicates, or partial settlements.

This project demonstrates an **end-to-end automated reconciliation workflow** that matches bank statement transactions against internal ledger records, highlights discrepancies, and produces **business-ready reports and dashboards** for daily operations.

The goal is not just to match numbers, but to reflect how reconciliation actually works in real fintech environments — balancing automation, analyst judgment, and clear business reporting.


## Business Problem

Manual reconciliation processes are common, but they come with real challenges:

- They are time-consuming and repetitive  
- They don’t scale as transaction volumes grow  
- They make it hard to spot patterns and root causes  
- They delay financial reporting and increase operational risk  

### Objective

Build a **repeatable reconciliation process** that:

- Automates daily transaction matching  
- Clearly flags and classifies discrepancies  
- Produces operational KPIs that business teams can easily consume  


## Data Sources

This project uses two core datasets:

- **Bank Statement Transactions**  
  *External source of truth representing what the bank processed*

- **Ledger Transactions**  
  *Internal system records used for accounting and reporting*

**Dataset used:**  
Kaggle – *Bank Reconciliation Statement* dataset

The data simulates common real-world reconciliation challenges, including:
- Timing differences between systems  
- Amount mismatches and rounding issues  
- Missing or inconsistent transaction references  
- Duplicate or partially posted transactions  


## Analytical Approach

The project follows a structured, real-world reconciliation workflow.

### 1. Exploratory Data Analysis (EDA)

Before attempting any matching, the data is explored to understand:

- Daily transaction volumes  
- Amount distributions  
- Missing or duplicated records  
- General transaction behavior over time  

**Why this matters:**  
Reconciliation logic built without understanding the data often leads to false matches and noisy exceptions.


### 2. Data Cleaning & Standardization

To reduce false discrepancies, the data is standardized by:

- Normalizing transaction dates  
- Rounding and aligning transaction amounts  
- Cleaning and standardizing transaction reference fields  
- Removing formatting inconsistencies  

**Outcome:**  
Clean, consistent datasets that can be reliably compared.

### 3. Feature Engineering

Additional features are created to support flexible matching, including:

- Absolute transaction amounts  
- Date differences (in days)  
- Amount differences  
- Normalized reference strings  
- Text similarity scores for fuzzy reference matching  

**Why this matters:**  
Real reconciliation rarely relies on exact matches alone. These features allow tolerance-based and realistic matching strategies.

### 4. Reconciliation Logic

Transactions are matched using **progressive reconciliation rules** commonly used in financial operations:

- **Exact Match**
  - Same amount  
  - Same transaction date  
  - High reference similarity  

- **Tolerance Match**
  - Small acceptable amount differences  
  - Date differences within a defined window  
  - Partial or fuzzy reference matches  

Transactions that do not meet any matching criteria are classified as **exceptions** and flagged for investigation.


### 5. KPIs & Business Reporting

The reconciliation results are summarized into operational metrics, including:

- Reconciliation Rate (%)  
- Matched vs Unmatched Transactions  
- Exception volumes for daily review  

All outputs are structured to feed directly into **Tableau dashboards** for business consumption.


## Results & Business Impact

This project delivers:

- Automated identification of matched and unmatched transactions  
- Clear, investigation-ready exception reports  
- Improved visibility into reconciliation performance  
- A scalable framework that can grow with transaction volumes  

### Business Value

- Reduced manual reconciliation effort  
- Improved accuracy and consistency  
- Faster daily and month-end reconciliation cycles  
- Better audit readiness and operational transparency  


## Tools & Technologies

- **Python** – pandas, numpy, rapidfuzz  
- **Jupyter Notebooks** – analysis and documentation  
- **Tableau** – business dashboards and reporting  
- **Git** – version control and project organization  

## 📁 Project Structure

```text
bank-transaction-reconciliation/
├── data/
│   ├── raw/
│   └── processed/
├── notebooks/
├── outputs/
├── tableau/
└── README.md
