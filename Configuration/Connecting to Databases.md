[src](https://superset.apache.org/docs/configuration/databases)
# Connecting to Databases
The main step in connecting Superset to a database is to **install the proper database driver(s)** in your environment.

## Installing Database Drivers
Superset requires a **Python DB-API database driver** and a **SQLAlchemy dialect** to be installed for each database engine you want to connect to.

## [Supported Databases and Dependencies](https://superset.apache.org/docs/configuration/databases#supported-databases-and-dependencies)
### [ClickHouse](https://superset.apache.org/docs/configuration/databases#clickhouse)
```bash
pip install clickhouse-connect
```
```bash
clickhousedb://{username}:{password}@{hostname}:{port}/{database}
```
