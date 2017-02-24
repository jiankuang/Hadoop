# Spark Unified Stack
![Spark Stack](spark-stack.PNG)

# RDD (Resilient Distributed Datasets)

# Spark Application Programming 
## Spark Context 
## Linking with Spark
### Linking with Spark - Scala
* Must have a compatible Scala version to write applications.
  - e.g. Spark 1.1.1 uses Scala 2.10
* To Write a Spark application, you need to add a Maven dependency on Spark. 

### Linking with Spark - Python
* Import some Spark classes: `from pyspark import SparkContext`

### Linking with Spark - Java 
* Add dependencies
* Import classes

## Initialzing Spark 
### Initializing Spark - Scala
### Initializing Spark - Python
### Initializing Spark - Java

# Spark Configuration
## Main Components of Spark Cluster
* Driver
* Cluster Manger
  - Standalone
  - Apache Mesos
  - Hadoop YARN
* Worker Nodes

## Main Locations for Spark Configuration
* SparkConf Object
* Environment variables: `conf/spark-env.sh`
* Logging: `log4j.properties`
