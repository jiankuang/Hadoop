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

## Three Ways of Setting Spark Properties
* Set application properties via the SparkConf Object  

  ```
  var conf = new SparkConf()
      .setMaster("local")
      .setAppName("CountingSheep")
      .set("spark.executor.memory", "1g")
  var sc = new SparkContext(conf)
  ```
* Dynamically setting Spark properties
  - Create s SparkContext with an empty conf  
    `var sc = new SparkContext(new SparkConf())`
  - Supply the configuration values during runtime  
    ```
    ./bin/spark-submit --name "My app" --master local[4] --conf spark.shuffle.spill=false 
      --conf "spark.executor.extraJavaOptions=-XX:+PrintGCDetails -XX:+PrintGCTimeStamps" myApp.jar
    ```
* Application Web UI: `http://<driver>:4040`

Run IBM BigData University Spark-Zeppelin Docker Image  
`docker run -i --name bdu_spark2 -P -p 4040:4040 -p 4041:4041 -p 8080:8080 -p 8081:8081 bigdatauniversity/spark2:latest`
