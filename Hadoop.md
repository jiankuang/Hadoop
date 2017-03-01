# Hadoop 
IBM Hadoop course

## Architecture
cluster -> rack -> node

## HDFS
* Not POSIX compliant
* File blocks: default 64MB, recommend 128MB

### HDFS Command
`hdfs dfs -ls`

#### POSIX-like commands
cat, chgrp, chmod, chown, cp, du, ls, mkdir, mv, rm, stat, tail

#### HDFS - specific commands
* copyFromLocal / put, copyToLocal / get 
* getMerge: gets all files and merges and sorts them to only one file on local filesystem
* setRep: sets the replication factor of a file (files)

## MapReduce
* only one namenode per cluster
* only one JobTracker per cluster

## Hadoop 2.2 Architecture (YARN)

## Moving Data into Hadoop
* Data at rest: use `cp`, `copyFromLocal` or `put` commands
* Data in motion
* Data from a web server
* Data from a data warehouse

### Sqoop
* Transfers data between Hadoop and relational databases
  - Users JDBC
  - Must copy the JDBC driver JAR files for any relational databases to $SQOOP_HOME/lib
* Users the database to describe the schema of the data
* Uses MapReduce to import and export the data
  - Import process creates a Java class
  - The source code of the class is provided to you
  - You can configure the number of Mappers used. 
  
#### A Sqoop JDBC connection string must include
* the name of the database 
* the hostname of the database server
* the port that the database server is listening on
* the name of the JDBC driver to use 

#### When importing data via Sqoop, the imported data can include
* a collection of data from multiple tables via a join operation, as specified by a SQL query
* specific rows and columns from a specific table
* all of the data from a specific table
 
#### Sqoop Exports
* Exports a set of files from HDFS to a relation database system
  - Table must already exist
  - Records are parsed based upon user's specifications
* Default mode is insert
* Update mode 
  - Generates update statements: `--update-key`
  - Replaces existing rows in the table
  - Does not generate an upsert: missing rows are not inserted, not detected as an error. 
* Call mode: makes a stored procedure call for each record


