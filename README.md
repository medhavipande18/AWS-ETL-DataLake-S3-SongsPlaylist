Description
This repository houses the ETL pipeline designed to populate the Sparkifydb AWS S3 Data Lake using Spark.
The aim of this database is to facilitate Sparkify in addressing various business inquiries related to its users, the songs they listen to, and the artists behind those songs, utilizing the available log and file data. This database offers a consistent and dependable source for storing such information.
The data sourced here will aid Sparkify in achieving several analytical objectives, such as identifying highly popular songs or peak traffic times during the day.

Dependencies
Ensure that you have the pyspark library installed. Additionally, you need to have a Spark cluster operational, either locally or on AWS EMR.

Database Design and ETL Pipeline
The STAR schema is employed for the schema design as it streamlines queries and facilitates rapid data aggregations.
Schema
Python is chosen for the ETL pipeline due to its rich libraries like pandas, which simplify data manipulation. It facilitates the extraction of files from S3 and data processing using Pyspark.
There are two primary types of data involved: song and log data. Song data comprises information about songs and artists, which are extracted and loaded into users and artists dimension tables, respectively.
Log data provides information on each user session. From the log data, we extract and load data into time and users dimension tables, along with the songplays fact table.

Running the ETL Pipeline
Execute etl.py to read the song and logs JSON files, denormalize the data into fact and dimension tables, and export these tables' output to S3 in the form of Parquet files.