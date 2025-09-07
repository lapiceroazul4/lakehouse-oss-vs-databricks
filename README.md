# lakehouse-oss-vs-databricks
Data Lakehouse implementations: Open Source vs Databricks

## Environment Variables Configuration

This project uses environment variables to securely manage all credentials and configurations.

### Initial Setup

1. **Copy the environment variables example file:**
   ```bash
   cp .env.example .env
   ```

2. **Edit the `.env` file** with your real credentials:
   ```bash
   # Example configuration in .env
   MINIO_ROOT_USER=admin
   MINIO_ROOT_PASSWORD=your_secure_password
   AZURE_STORAGE_ACCOUNT_KEY=your_actual_azure_key
   # ... more configurations
   ```

3. **Generate the secrets.toml file** (for dlt compatibility):
   ```bash
   python generate_secrets.py
   ```

### Available Environment Variables

- **MinIO**: `MINIO_ROOT_USER`, `MINIO_ROOT_PASSWORD`, `MINIO_ENDPOINT_URL`
- **Nessie**: `NESSIE_URI`, `NESSIE_ACCESS_KEY`, `NESSIE_SECRET_KEY`
- **ClickHouse**: `CLICKHOUSE_USER`, `CLICKHOUSE_PASSWORD`, `CLICKHOUSE_HOST`
- **Azure Storage**: `AZURE_STORAGE_ACCOUNT_NAME`, `AZURE_STORAGE_ACCOUNT_KEY`

### Security

- ❌ **Never** commit the `.env` file to the repository
- ✅ The `.env` file is included in `.gitignore`
- ✅ Use `.env.example` as a template for other developers

### Execution

```bash
# Start the services
docker-compose up -d

# Notebooks will automatically load environment variables
# No need to hardcode credentials
```