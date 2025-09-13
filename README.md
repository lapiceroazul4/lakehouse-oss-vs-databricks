# lakehouse-oss-vs-databricks
Comparing Data Lakehouse implementations: **Open Source stack** vs **Databricks**.

---

## What is a Data Lakehouse?

A **Data Lakehouse** is a modern data architecture that combines the best of **data lakes** (low-cost, scalable storage for raw and semi-structured data) and **data warehouses** (structured, performant, query-optimized storage).  
The idea is to provide a **single platform** that can handle:
- Data ingestion from multiple sources (batch & streaming).
- Storage of structured, semi-structured, and unstructured data.
- ACID transactions on top of the data lake.
- Support for BI, ML, and AI workloads on the same platform.

### Open Source Lakehouse
An **Open Source Lakehouse** uses community-driven projects to build the stack 

![Databricks Lakehouse](https://i.imgur.com/SiMrMcO.png)

### Databricks Lakehouse
**Databricks** is a commercial, fully managed lakehouse platform built on top of **Delta Lake**.  

It provides:
- Fully managed storage and compute. 
- Delta Lake for ACID transactions. 
- Native integration with Spark, MLflow, DBSQL, and Unity Catalog. 
- Enterprise-grade security, compliance, and governance. - Optimizations like Photon for query performance. 

**Pros:** 
   - Simplified management (no need to worry about infrastructure). 
   - Enterprise support and SLA guarantees. 
   - Strong ecosystem for ML/AI and advanced analytics. 
   - Best-in-class performance optimizations.
 
**Cons:**
   - Vendor lock-in (proprietary extensions). 
   - Licensing costs. 
   - Less flexibility to swap components.

## Environment Variables Configuration

This project uses environment variables to securely manage all credentials and configurations.

### Initial Setup

1. **Copy the environment variables example file:**
   ```bash
   cp .env.example .env
2. Edit the .env file with your real credentials:
   ```bash
   # Example configuration in .env
   MINIO_ROOT_USER=admin
   MINIO_ROOT_PASSWORD=your_secure_password
   AZURE_STORAGE_ACCOUNT_KEY=your_actual_azure_key
   # ... more configurations
3. Generate the secrets.toml file (you can used the template as well):
   ```bash
   python generate_secrets.py
### Execution
Start the full environment using Docker Compose:
   ```bash
   docker compose up -d