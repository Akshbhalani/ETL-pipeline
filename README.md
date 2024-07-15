# Overview

This project implements a comprehensive ETL (Extract, Transform, Load) pipeline utilizing a variety of technologies and services to ensure data is efficiently moved, transformed, and stored for analytical purposes. The primary steps involve extracting data from a PostgreSQL database, securely storing it in AWS S3, transforming the data into dimensional and fact tables, and finally loading it into AWS Redshift for advanced analytics and visualization using Power BI.

# Project Workflow

### 1. Data Extraction
+ **Technology Used :** PostgreSQL, Python, psycopg2
+ **Description :** The initial step involves extracting data from a PostgreSQL database. Using the 'psycopg2' library, data is read into a Python environment for further processing.
+ **Code file :** upload_file_in_s3.ipynb

### 2. Secure Storage in S3
+ **Technology Used :** AWS S3, Python, boto3, StringIO
+ **Description :** Once the data is extracted from PostgreSQL, it is stored in AWS S3. This ensures that the original data is kept in a secure and scalable storage solution.
+ **Code file :** upload_file_in_s3.ipynb

### 3. Data Transformation
+ **Technology Used :** Python, pandas
+ **Description :** The extracted data is then read from S3 and transformed into four dimensional tables and one fact table. These tables are structured to optimize query performance and analytical capabilities.
+ **Code file :** s3 to python read.ipynb

### 4. Storing Transformed Data in S3
+ **Technology Used :** AWS S3, Python, boto3, StringIO
+ **Description :** The transformed data is stored back into AWS S3, ensuring it is readily available for the next stage of the ETL process.
+ **Code file :** s3 to python read.ipynb

### 5. Data Loading into Redshift
+ **Technology Used :** AWS Redshift, Python, psycopg2
+ **Description :** The final step of the ETL pipeline involves loading the transformed data from S3 into AWS Redshift. Using the 'COPY' command, data is efficiently transferred to Redshift, facilitating large-scale data analysis.
+ **Code file :** python_to_redshift.ipynb

### 6. Data Visualization with Power BI
+ **Technology Used :** AWS Redshift, Power BI
+ **Description :** Connect Power BI Desktop to AWS Redshift to load the data for visualization. This enables the creation of interactive and insightful visualizations based on the transformed data stored in Redshift.
+ **BI file :** Sales Data BI Analysis.bi

### Important Libraries Used

**psycopg2**
+ 'psycopg2' is a PostgreSQL adapter for Python. It allows Python code to execute PostgreSQL commands in a database session.
+ In this project, 'psycopg2' is used to extract data from PostgreSQL and to load data into AWS Redshift.

**Boto3**
+ 'Boto3' is the Amazon Web Services (AWS) SDK for Python, which allows Python developers to write software that makes use of services like Amazon S3, Amazon EC2, and Amazon DynamoDB.
+ In this project, 'Boto3' is used to interact with AWS S3 to upload and download data.

**StringIO**
+ The StringIO module is used to handle strings as file objects. This is particularly useful for reading and writing data to in-memory strings.
+ In the context of this project, 'StringIO' can be used to efficiently manage CSV data in memory before uploading it to AWS S3 or other processes.

## COPY Command in Redshift
+ The COPY command is a highly efficient way to load data into an Amazon Redshift table from various sources, such as Amazon S3, Amazon DynamoDB. The command parses the incoming data and inserts it into the specified table. This command is particularly useful for bulk loading large datasets into Redshift quickly and efficiently.
