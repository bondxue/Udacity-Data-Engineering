# Udacity-Data-Engineering
Projects and resources developed in the [DEND Nanodegree](https://www.udacity.com/course/data-engineer-nanodegree--nd027) from Udacity.

## Project 1: [Relational Databases - Data Modeling with PostgreSQL](https://github.com/bondxue/Udacity-Data-Engineering/tree/master/Data-Modeling-with-PostgreSQL)

Developed a relational database using PostgreSQL to model user activity data for a music streaming app. Skills include:

+ Created a relational database using PostgreSQL
+ Developed a Star Schema database using optimized definitions of Fact and Dimension tables. Normalization of tables.
+ Built out an ETL pipeline to optimize queries in order to understand what songs users listen to.

Proficiencies include: Python, PostgreSql, Star Schema, ETL pipelines, Normalization

## Project 2: [NoSQL Databases - Data Modeling with Apache Cassandra](https://github.com/bondxue/Udacity-Data-Engineering/tree/master/Data-Modeling-with-Cassandra)

Designed a NoSQL database using Apache Cassandra based on the original schema outlined in project one. Skills include:

+ Created a nosql database using Apache Cassandra (both locally and with docker containers)
+ Developed denormalized tables optimized for a specific set queries and business needs

Proficiencies used: Python, Apache Cassandra, Denormalization

## Project 3: [Data Warehouse - Amazon Redshift](https://github.com/bondxue/Udacity-Data-Engineering/tree/master/Data-Warehouse-with-AWS)

In this part, I am helping the music streaming startup, Sparkify, to move their song database onto the cloud. Their data is stored in S3:

+ one is  in a directory of JSON logs on user activity on the app
+ the other is in a directory with JSON metadata on the songs in their app

I am tasked with <u>building an ETL pipeline that extracts their data from **S3**, stages them in **Redshift**, and transforms data into a set of **dimensional tables**</u> for the analytics team to continue finding insights in what songs their users are listening to. 

## Project 4: [Data Lake - Spark](https://github.com/bondxue/Udacity-Data-Engineering/tree/master/Data-Lake-with-Spark)
Scaled up the current ETL pipeline by moving the data warehouse to a data lake. Skills include:

+ Create an EMR Hadoop Cluster
+ Further develop the ETL Pipeline copying datasets from S3 buckets, data processing using Spark and writing to S3 buckets 
+ using efficient partitioning and parquet formatting.
+ Fast-tracking the data lake buildout using (serverless) AWS Lambda and cataloging tables with AWS Glue Crawler.

Technologies used: Spark, S3, EMR, Athena, Amazon Glue, Parquet.
