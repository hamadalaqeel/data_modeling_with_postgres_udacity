# Data Modeling with Postgres
Data Engineering Nanodegree, Project 1.

## Introduction
An imaginery startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

They'd like a Data Engineer to create a Postgres database with tables designed to optimize queries on song play analysis. The task is to create a star schema for Postgres and develop an ETL pipleine which will transfer the data from local files to the database.

## Database Schema Design

![Our Database looks like the following](https://github.com/hamadalaqeel/data_modeling_with_postgres_udacity/blob/master/Database%20Schema.png)


## ETL Process
What does the ETL pipeline look like in our case?

1. unning the `create_tables.py` script in a terminal creates and initializes the tables for the sparkifydb database. Another file `sql_queries.py` contains all SQL queries and is imported into `create_tables.py`.

2. Running `test.ipynb` in a Jupyter notebook confirms that the tables were successfully created with the correct columns.

3. Running the notebook `etl.ipynb` develops the ETL processes for each table and is used to prepare a python script for processing all the datasets.

4. In a terminal, the python `etl.py` script is run to process the all the datasets. The script connects to the Sparkify database, extracts and processes the log_data and song_data, and loads data into the five tables. The file `sql_queries.py` contains all SQL queries and is imported into `etl.py`.

5. Again, running `test.ipynb` confirms that the records were successfully inserted into each table.

Now all is done, our Postgres database is finally modeled and ready to be queried.
