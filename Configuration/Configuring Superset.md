[src](https://superset.apache.org/docs/configuration/configuring-superset)

# Configuring Superset
## [Setting up a production metadata database](https://superset.apache.org/docs/configuration/configuring-superset#setting-up-a-production-metadata-database)
For production environments, using **SQLite is highly discouraged** due to security, scalability, and data integrity reasons.  
It's important to use only the supported database engines and consider using a different database engine on a separate host or container.

Superset supports the following database engines/versions:

Database Engine	Supported Versions  
**PostgreSQL**	10.X, 11.X, 12.X, 13.X, 14.X, 15.X, 16.X  
**MySQL**	5.7, 8.X
