# 🛡️ E-Commerce Transaction & Operational Risk Analytics Pipeline

## 📊 Business Context & Objective
In e-commerce platforms, malicious chargebacks (Fraud Risk) and aggressive policy exploitation (Return Risk) act as hidden profit margin killers. This project establishes a robust data engineering and analytics pipeline using **Python (Pandas)** and **SQL (SQLite)** to audit 12,000 historical order transactions, validate third-party threat intelligence, and deploy an automated risk-mitigation rule matrix.

---

## 🔍 Key Engineering & Analytical Milestones

### 1. Relational Database Schema Architecture
* Designed and provisioned an idempotent SQLite database pipeline (`ecommerce_analytics.db`).
* Enforced structural data integrity constraints, including explicit data types and an immutable `PRIMARY KEY` on `order_id` to prevent record duplication.

### 2. Digital Channel Fraud Risk Auditing
* Evaluated transaction vulnerabilities across combinations of hardware form factors and marketing channels.
* Identified **Mobile + Paid Ads** as the platform's highest threat vector, demonstrating a **6.34% baseline fraud rate**.

### 3. Threat Intelligence Verification (`high_risk_ip`)
* Audited a binary flag from a simulated third-party IP risk network before integrating it into production logic.
* Proved that transactions from flagged IPs carried an **18.11% fraud conversion rate**—nearly **6x riskier** than standard connections.

### 4. Automated Governance Rule Engine Matrix
Constructed a multi-layered SQL conditional `CASE WHEN` engine to dynamically route checkout requests into four operational action tiers:
* 🟢 **PASS**: Low-risk profiles cleared for frictionless fulfillment (72.15% of portfolio volume).
* 🟡 **MFA_CHALLENGE**: Suspicious vectors (e.g., Paid Ads with clean IPs) stepped up to Multi-Factor Authentication to mitigate risk while minimizing good customer friction (20.02% share).
* 🔴 **IMMEDIATE_BLOCK**: Hard intercept on high-probability fraud, protecting up to **€37,862.16** in inventory capital and chargeback fines (5.22% share).
* 📋 **LOGISTICS_AUDIT**: Flags high-value `Return Risk` profiles over long distances to protect fulfillment logistics margins (2.60% share).

---

## 🛠️ Tech Stack & Environment
* **Language:** Python 3.9
* **Libraries:** Pandas, SQLite3
* **Environment:** JupyterLab Sandbox
* **SQL Concepts utilized:** Common Table Expressions (CTEs), Subqueries, Multi-conditional `CASE WHEN` logic, Precise Aggregations (`SUM`, `COUNT`, `AVG`).
