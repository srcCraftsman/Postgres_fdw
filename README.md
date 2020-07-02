# Postgres docker image with data wrappers and other extensions

### Realized extensions::

 - tds_fdw(connect to MsSQL)
 - mysql_fdw
 - oracle_fdw
 - pg_cron
 - SQLite
 - Firebird
 - MonetDB
 - Cassandra
 - MongoDB
 - Redis

### TODO:

 - Correct variable substitution for pg_cron
 - More lightweight images with only one wrapper type

### Wrappers repositories with instructions how to use it:

 - [MsSQL](https://github.com/tds-fdw/tds_fdw)
 - [MySQL](https://github.com/EnterpriseDB/mysql_fdw)
 - [Oracle](https://github.com/laurenz/oracle_fdw)

### To use pg_cron:

 - Use [THIS](https://github.com/citusdata/pg_cron) instruction from repository.

 - Remember, that by default DB for pgcron is "postgres"

 - The list of all possible wrapper extensions you can find [here](https://wiki.postgresql.org/wiki/Foreign_data_wrappers)