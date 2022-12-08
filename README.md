
# The purpose of this database in the context of the startup, Sparkify, and their analytical goals.

The current project presents a database and ETL pipeline that captures user
song listening activity for Sparkify, making queries against the database
possible and effortless.

# How to run the Python scripts

There are two Python scripts that must be run (simply with `python <script name>.py`) to provision the database:
    1. `create_tables.py`: This will 
          - create or connect to an existing instance of the "sparkifydb" database, 
          - drop existing database tables,
          - and create all of the database tables.
    2. `etl.py`: This will perform the ETL process and populate the database with the song and logfile data.

# An explanation of the files in the repository

The following files and directories are present in the project repository:

* `data/` - This directory holds `log_data` and `song_data` which is loaded into the database.
* `create_tables.py` - This script creates or connects to a database instance, drops existing tables, and creates all of the database tables according to the schema.
* `etl.ipynb` - This is a Jupyter notebook for testing the ETL process.
* `etl.py` - This is the file that performs the ETL process, including processing song and log data.
* `README.md` - This file.
* `sql_queries.py` - This file contains a collection of SQL queries to create tables, insert data into tables, and query the songs table.
* `test.ipynb` - This Jupyter notebook contains a number of tests to evaluate the ETL process and the database schema.

# Database schema design and ETL pipeline

The database follows a "star" schema, in which a central fact table (songplays) is qualified by the following dimension tables: users, songs, artists, and time. These are populated during the ETL process from songs and user logs datasets. The benefit of this design is that it minimises the number of SQL JOINS that must be performed to query the database.



