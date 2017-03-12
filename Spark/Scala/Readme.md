# Move data between HDFS and Spark
## Reading and Saving Text Files between HDFS and Spark
```
val dataRDD = sc.textFile("/user/cloudera/sqoop_import/departments")
dataRDD.collect.foreach(println)
dataRDD.saveAsTextFile("hdfs://quickstart.cloudera:8022/user/cloudera/spark/departments")
```
## Reading and Saving Hive Files between HDFS and Spark
```
import org.apache.spark.sql.hive.HiveContext
val sqlContext = new HiveContext(sc)
val depts = sqlContext.sql("select * from departments")
```
## Reading and Saving JSON Files between HDFS and Spark
```
import org.apache.spark.sql.SQLContext
val sqlContext = new SQLContext(sc)
val departmentsJson = sqlContext.jsonFile("/user/cloudera/scalaspark/departments.json")
```

# Word Count using Spark Scala
![word-count-using-spark-scala](word-count-using-spark-scala.png)

# Joining Disparate DataSets using Scala
The purpose of this example is to calculate totalRevenuePerDay

## Read Orders and OrderItems Datasets
![1-read-orders-orderitems-data](1-read-orders-orderitems-data.png)
## revenuePerOrderPerDay
![2-revenuePerOrderPerDay](2-revenuePerOrderPerDay.png)
## totalOrdersPerDay
![3-totalOrdersPerDay](3-totalOrdersPerDay.png)
## totalRevenuePerDay
![4-totalRevenuePerDay](4-totalRevenuePerDay.png)

# HiveContext and SQLContext
HiveContext is used when there are Hive tables; if not, we can use SQLContext to register temp tables. 

## SQLContext
### Load Data into RDD
![sqlcontext-1-load-data-into-rdd](sqlcontext-1-load-data-into-rdd.png)
### Register Temp Table
![sqlcontext-2-register-temp-table](sqlcontext-2-register-temp-table.png)
