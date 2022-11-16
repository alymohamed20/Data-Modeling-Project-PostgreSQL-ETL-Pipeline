# Project 1: Data Modeling with PostgreSQL
This Project creates a postges database `sparkifydb` for a music app, *Sparkify*. The purpose of the database is to model log and song datasets (JSON format) with a star schema optimised for queries on song play analysis.
## Schema design and ETL pipeline
The star schema has 1 fact table(songplays) and 4 dimension tables(users,songs,artists,time).CRUD queries are defined in **sql_queries.py**. **create_tables.py** uses functions `drop_tables`,`create_database` and `create_tables` to create the database sparkifydb and the required tables.

Extract the data and load it in **etl.py** to fill the **songs** and **artists** tables with data from song_data JSON file. Processed data from log_data is used to fill data for **time** and **users** tables. `select`query catch the song and artist id from **songs** and **artists** tables and combines them with the log file to fill the **songplays** fact table.

## Song play example queries

Simple queries might include number of users with each membership level.

`SELECT COUNT(level) FROM users;`

Day of the week music most frequently listened to.

`SELECT COUNT(weekday) FROM time;`

Or, hour of the day music most often listened to.

`SELECT COUNT(hour) FROM time;`