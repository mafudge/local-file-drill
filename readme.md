# Local File Drill

This project leverages a containerized version of Apache Drill https://drill.apache.org/ to query your CSV / Excel files... and MORE with SQL! Drop your files in the `data` folder then query them like they are database tables.

### What is Drill?

Apache Drill is an MPP (Massive Parallel Processing) query engine. It is designed to query a variety of data files, and big-data services such as S3, Hadoop, Hbase, Hive, Cassandra using SQL. Learn more about Drill's flavor of SQL here: https://drill.apache.org/docs/sql-reference-introduction/

### Which file types are supported?

In this setup we use it to query local CSV and Excel files with SQL. It can also read in other formats such as JSON, Parquet, Microsoft Access, and more. Supported file formats can be found here: https://drill.apache.org/docs/data-sources-and-file-formats/

Most of them are configured already in the `data.json` file provided. 

## Prerequisites

You must install Docker desktop or some other container platform to run the application. https://www.docker.com/products/docker-desktop/ 

## Instructions

1. Start drill `$ docker-compose up`
2. Point your browser at the Drill application http://localhost:8047 
3. Configure the `data` storage plugin on the drill website
    - Click **Storage**
    - Click **Create**
    - Storage name: `data`
    - Configuration: Copy the contents of `plugins/data.json`
    - Click **Create** to save.
4. You are now ready to query any file you place in the `data` folder!
5. Example: ```select * from data.`prices.xlsx`; ```

Happy Drilling!

m


### Helpful Tips

- Your CSV files need a header to query properly.
- You can query other file types, check: https://drill.apache.org/docs/data-sources-and-file-formats/
- You can query other tabs in the worksheet. See: https://drill.apache.org/docs/excel-format-plugin/

