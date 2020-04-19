## Data Modeling with Postgres 

We create a data model for a music streaming application to help out analytics team (in fictional startup Sparkify) run analytics queries on users and their song activity data. 

### Objective
Using Postgres, model the data with Star schema with the fact and dimension tables and build a ETL pipeline to process data from JSON files to the analysis 'sparkifydb' database. 

### ETL process
Song data set consists of subset of files from [Million Song Dataset](http://millionsongdataset.com/) and log data set is simulated using [this event simulator](https://github.com/Interana/eventsim).
Data in JSON files are read using pandas package which then are later transformed and loaded into corresponding tables.

#### Star schema
Data from JSON files are loaded into one fact and four dimension tables in sparkifydb. Fact and dimension tables are given below. 

##### Fact table
- songplays

##### Dimension tables
- users
- songs
- artists
- time

| Files | Description |
|-------|-------------|
|create_tables.py| Script to drop and create the analysis database (sparkifydb) and the above fact and dimension tables|
|sql_queries.py| Script which contains create, drop and insert SQL statements|
|etl.ipynb| Jupyter notebook  which performs ETL for a single song ETL (used for development) |
|etl.py| Performs ETL on the dataset available in data folder |
|test.ipynb| Notebook to verify if ETL ran succesfully |

Instructions to run:

- First, create the Sparkifydb and the fact and dimension tables by executing create_tables.py file 
- Populate the fact and dimension tables by executing etl.py file 
- Verify if all tables are populated by running all cells in test.ipynb file

Run the python files by executing '>python $file_name$.py' in a terminal from the project directory. 
