# postgresql_meta

This repo contains postgresql queries tht I have found useful for debugging, maintenance, management of postgresql database

1. List all open connections to the database. 

Useful to find out connection leaks of an application connecting to DB

SELECT 
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
WHERE state = 'active';

Reference - https://stackoverflow.com/questions/27435839/how-to-list-active-connections-on-postgresql
