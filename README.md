# Big Data Assignment 02 – Retail Analytics Pipeline 

## What This Project Is About

This project walks through a practical big‑data workflow built with **PySpark** and **MongoDB**. Instead of treating the dataset as something perfectly clean and ready, the pipeline assumes real‑world conditions — messy records, missing values, odd transactions — and shows how to turn that raw data into something genuinely useful for analysis.

Think of it as a miniature production‑style data engineering system designed for learning, experimentation, and performance awareness.

---

## The Big Picture – How Data Moves

We follow a medallion‑style flow (Bronze → Silver → Gold):

• **Bronze Layer** → Raw but structured data
• **Silver Layer** → Cleaned and validated data
• **Gold Layer** → Analytics‑ready model stored in MongoDB

Raw data rarely behaves. Each stage improves reliability and usability.

---

## Tools & Technologies Used

• **PySpark** – Distributed processing & transformations
• **MongoDB Atlas** – NoSQL storage & analytics queries
• **Python** – Core implementation language
• **Google Colab / Local Spark** – Execution environment

---

## What Was Actually Done

### Data Loading & Exploration (Bronze Layer)

The dataset is first pulled into Spark where its structure, schema, and record counts are examined. Basic attributes such as year and month are derived to support later analysis.

Goal: Understand what we’re working with before making assumptions.

---

### Cleaning & Data Quality Checks (Silver Layer)

Several realistic problems are handled:

• Cancelled or invalid invoices removed
• Missing customer identifiers filtered
• Impossible values (negative prices / quantities) corrected or excluded
• Duplicate rows eliminated

Goal: Prevent bad data from corrupting metrics.

---

### Feature Engineering

New analytical fields are created to make the data meaningful:

• Revenue calculations
• Time‑based attributes
• Basket‑level aggregations
• Customer‑centric behavioral metrics (RFM‑style logic)

Example intuition:
Revenue isn’t stored — it must be computed.

---

### MongoDB Data Modeling (Gold Layer)

The cleaned dataset is reshaped into analytics‑friendly collections:

• Invoice / transaction facts
• Customer details
• Product information

This separation mirrors real analytical systems where events and descriptions are handled differently.

---

### Indexing & Query Efficiency

Indexes are introduced to make MongoDB queries faster and more scalable. Without indexing, analytical workloads quickly become expensive.

Focus: Performance is a design choice, not an afterthought.

---

### Analytics & Insights

Various aggregation queries are performed, including:

• Revenue trends over time
• High‑value customers
• Best‑performing products
• Country‑level comparisons

Goal: Convert processed data into interpretable information.

---

### Performance‑Aware Spark Usage

Several optimization strategies are applied:

• Repartitioning before heavy operations
• Caching reused DataFrames
• Minimizing shuffle overhead
• Efficient join patterns

Reason: Distributed systems reward careful planning.

---

## Why This Matters

This assignment is less about syntax and more about thinking like a data engineer:

✔ Raw data is unreliable
✔ Cleaning rules change business results
✔ Modeling decisions affect query cost
✔ Indexing drastically impacts speed
✔ Spark performance depends on transformation strategy

---

## How to Run

Install required libraries:

pip install pyspark pymongo

Create a Spark session and connect MongoDB when needed.

---

## Key Takeaway

A functional data pipeline is not just about moving data — it’s about improving trust, usability, and performance at every step.

---

## Author
CIT-23-02-0025
CIT-23-02-0127
CIT-23-02-0054
CIT-23-02-0130

