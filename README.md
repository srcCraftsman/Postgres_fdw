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
 - pg-hint-plan
 - postgis

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

### To use pg-hint-plan:

 - Use [THIS](https://postgrespro.ru/docs/enterprise/11/pg-hint-plan) official instruction.

 ### To use postgis:

 - Use [THIS](https://trac.osgeo.org/postgis/wiki/UsersWikiPostGIS24UbuntuPGSQL10Apt) official instruction.


 ### After build actions

  -  Add to /var/lib/postgresql/data/postgresql.conf the lines below:
```
    shared_preload_libraries = 'pg_cron, pg_stat_statements, pg_hint_plan'

    cron.database_name = 'postgres'
```


 - After first run the container, need to create extensions:

```
    CREATE EXTENSION pg_cron;

    LOAD 'pg_hint_plan';

    CREATE EXTENSION postgis;

    CREATE EXTENSION dblink;

    CREATE EXTENSION mysql_fdw;

    CREATE EXTENSION oracle_fdw ;

    CREATE EXTENSION postgres_fdw;

    CREATE EXTENSION tds_fdw;
```


 - The list of all possible wrapper extensions you can find [here](https://wiki.postgresql.org/wiki/Foreign_data_wrappers)