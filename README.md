# 🕵️‍♂️ Credit Card Fraud Detection with Neo4j

## Overview

This project focuses on modeling and detecting credit card fraud using graph databases. Built as part of the *New Generation Data Models and DBMS* course under the guidance of Professor Marco Mesiti, the system simulates transaction data and uses **Neo4j** to model relationships between customers, terminals, and transactions, including fraudulent activities.

Rather than applying traditional machine learning approaches, this project explores the **data modeling and querying capabilities** of property graphs to uncover fraud patterns and relationships.

---

## 🧠 Features

* Synthetic data generation for:

  * Customer profiles
  * Terminal profiles
  * Transactions (legitimate and fraudulent)
* Data loading pipeline into **Neo4j** using Python
* Rich **graph-based schema** including:

  * Customer ↔ Terminal ↔ Transaction
  * Period of the Day
  * Kind of Products
  * Buying Friend relationships
  * Co-Customer network
* Advanced **Cypher queries** for pattern detection and fraud analytics
* Performance tuning with **indexes** and **batch transactions**

---

## 🗂️ Dataset

Datasets are generated using a custom `generator.py` script. Users can specify the dataset size in multiples of 50MB. Generated CSVs include:

* `customers-<n>.csv`
* `terminals-<n>.csv`
* `transactions-<n>.csv`

---

## 🔧 Technologies Used

* Python 3
* Neo4j (property graph database)
* Cypher Query Language
* pandas, `neo4j` Python driver, `urllib`, `pathlib`

---

## 📈 Graph Model

* **Nodes**: `Customer`, `Terminal`
* **Relationships**:

  * `TRANSACTION` with properties like `amount`, `datetime`, `fraud`, `period_of_the_day`, `kind_of_products`
  * `BUYING_FRIEND`: between customers with similar product purchases at the same terminal
  * `CO_CUSTOMER`: customers who share transaction terminals within k hops

---

## 🧾 Sample Queries

1. **Total spend per customer over time**
2. **Identify suspicious transactions exceeding 50% of average terminal transaction amount**
3. **Explore co-customer networks of degree *k***
4. **Detect buying friend clusters**
5. **Analyze fraud count by time of day**

---

## 🚀 Getting Started

### Prerequisites

* Neo4j Desktop or Neo4j Aura instance
* Python 3 with required modules

### Setup

1. Clone the repository:

   ```bash
   git clone https://github.com/RishavMondal/Credit-Card-Fraud-Detection-System.git
   cd Credit-Card-Fraud-Detection-System
   ```

2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Generate data:

   ```bash
   python generator.py
   ```

4. Load data into Neo4j:

   ```bash
   python loading.py
   ```

5. Run queries:

   ```bash
   python queries.py
   ```

---

## 📊 Performance Highlights

| Dataset Size | Transactions | Load Time (w/ Indexing) |
| ------------ | ------------ | ----------------------- |
| 41.7 MB      | 1,000,000    | \~65.5 seconds          |
| 85 MB        | 2,000,000    | \~133.4 seconds         |
| 129 MB       | 3,200,000    | \~202.5 seconds         |

Graph extensions and indexes significantly reduce load and query time.

---

## 👨‍💻 Author

**Rishav Mondal**
*Master's in Business Analytics, Clark University*
Contact: [LinkedIn](https://www.linkedin.com/in/rishavmondal)

---

## 📄 License

This project is for academic and research purposes. Attribution is appreciated.
