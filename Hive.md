Hive is a data warehouse system built on top of Hadoop. 

# Hive DDL
* Database -> 
* Table -> 
* Partition -> A virtual column which defines how data is stored on the file system based on its values. Each table can have one or more partitions (and one or more levels of partition). 
* Buckets(or Clusters) -> In each partition, data can be divided into buckets based on the hash value of a column in the table (useful for sampling, join optimization). 

# Hive DML
* Loading data from input file (Schema on Read)  
`LOAD DATA LOCAL INPATH '/tmp/data/users.dat' OVERWRITE INTO TABLE users;`
  - The "LOCAL" indicates the source data is on the local filesystem
  - Local data is **copied** to final location
  - Otherwise file is assumed to be on HDFS and is **moved** to final location
  - Hive does not do any trasformation while loading data into tables
* Loading data into a partition requires PARTITION clause  
`LOAD DATA LOCAL INPATH '/tmp/data/usersny.dat' OVERWRITE INTO TABLE users; PARTITION (country = 'US', state = 'NY')`
  - HDFS directory is created: `/user/hive/warehouse/mydb.db/users/country=US/state=NY`
  - userny.dat file is copied to this HDFS directory
