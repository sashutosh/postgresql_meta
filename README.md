# postgresql_meta

This repo contains postgresql queries that I have found useful for debugging, maintenance, management of postgresql database

1. List all open connections to the database.   

    * Useful to find out connection leaks of an application connecting to DB

    * **_SELECT 
    pid
    ,datname
    ,usename
    ,application_name
    ,client_hostname
    ,client_port
    ,backend_start
    ,query_start
    ,query
    ,state
FROM pg_stat_activity
WHERE state = 'active';_**

    * Reference - https://stackoverflow.com/questions/27435839/how-to-list-active-connections-on-postgresql

2. Convert epoch timestamp to date time
* **select to_timestamp(cast(epoch_ms/1000 as bigint))::date**
    * Reference - https://stackoverflow.com/questions/16609722/postgresql-how-to-convert-from-unix-epoch-to-date
