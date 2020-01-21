# Project 1: Song Play Analysis with RDBMS
[![Project passed](https://img.shields.io/badge/project-passed-success.svg)](https://img.shields.io/badge/project-passed-success.svg)

## Summary
* [Purpose of database](#purpose-database)
* [Database schema](#database-schema)
* [Porject structure](#project-structure)
* [Data cleaning](#data-cleaning)
* [Runing procedure](#runing-procedure)

------------------------------------------
### Purpose of database
This Postgres database is to help Sparkify to optimize queries on song play analysis based on the JSON metadata about the songs and user activities on their new music streaming app. 


--------------------------------------------
### Databaase schema
Using the song and log datasets, a `star schema` is created for queries on song play analysis. 

   <img src="https://github.com/bondxue/Song-Play-Analysis-with-PostgreSQL/blob/master/images/schema.PNG" width="700">

Following tables are included:
#### Fact Table 
1. **songplays** - records in log data associated with song plays i.e. records with page `NextSong` 
    + *songplay_id (PK), start_time (FK), user_id (FK), level, song_id (FK), artist_id (FK), session_id, location, user_agent*
    <img src="https://github.com/bondxue/Song-Play-Analysis-with-PostgreSQL/blob/master/images/songplay_table.PNG" width="700">


#### Dimension Tables 
2. **users** - users in the app 
    + *user_id (PK), first_name, last_name, gender, level*
    <img src="https://github.com/bondxue/Song-Play-Analysis-with-PostgreSQL/blob/master/images/users_table.PNG" width="300">

3. **songs** - songs in music database
    + *song_id (PK), title, artist_id, year, duration*
    <img src="https://github.com/bondxue/Song-Play-Analysis-with-PostgreSQL/blob/master/images/songs_table.PNG" width="600">


4. **artists** - artists in music database
    + *artist_id (PK), name, location, lattitude, longitude*
    <img src="https://github.com/bondxue/Song-Play-Analysis-with-PostgreSQL/blob/master/images/artists_table.PNG" width="900">

5. **time** - timestamps of records in **songplays** broken down into specific units
    + *start_time (PK), hour, day, week, month, year, weekday*
    <img src="https://github.com/bondxue/Song-Play-Analysis-with-PostgreSQL/blob/master/images/time_table.PNG" width="300">

--------------------------------------------
### Project Structure 
In addition data files, this project includes the following files:
+ `test.ipynb` - This notebook is to check the database and help to know if tables are created and data are ingested correctly 
+ `create_tables.py` - This script will drop old tables (if exist) ad re-create new tables
+ `etl.py` - This script is to build ETL processes which will read JSON every file contained in /data folder, parse them, build relations though logical process and ingest data 
+ `etl.ipynb` - It is a notebook that helps to know step by step what `etl.py` does
+ `sql_queries.py` - This file contains variables with SQL statement in String formats, partitioned by CREATE, DROP, INSERT statements plus a FIND query 

--------------------------------------------
### Data Cleaning
When we create **songplays** table, we set `start_time` and `user_id` to be `NOT NULL`, which will prevent the entry of NULL values into the table for those cloumns. 

--------------------------------------------
### Running procedure

To create the `sparkifydb` database and tables, we need to run `create_tables.py` from the terminal. Then run `test.ipynb` to confirm the creation of your tables with the correct columns. Next, we need to run `etl.ipynb` from the terminal also to read all files from `song_data` and `log_data` into tables. Finally, we need to run `test.ipynb` to confirm your records were successfully inserted into each table.









